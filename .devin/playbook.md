# Playbook: Onboard New Component Helm Charts

## Trigger
Run this playbook when onboarding a new microservice/component that needs Helm charts.

## Inputs Required
- `APP_NAME`: Name of the new application (e.g., `order-service`)
- `TARGET_REPO`: GitHub repo where the Helm charts should be added (e.g., `malli1234/order-service`)
- `IMAGE_REPO`: Container image repository (e.g., `docker.io/malli1234/order-service`)
- `SERVICE_PORT`: Port the app listens on (e.g., `8080`)
- `NAMESPACE_DEV` / `NAMESPACE_STAGING` / `NAMESPACE_PROD`: Kubernetes namespaces per env
- `REPLICAS_DEV` / `REPLICAS_STAGING` / `REPLICAS_PROD`: Replica counts per env
- Any other key values from `template-keys.json`

## Steps

1. Clone the template repo `malli1234/hello-world-maven_1` and the target repo `TARGET_REPO`.
2. Copy the entire `helm/` directory from the template repo into the target repo.
3. Read `helm/template-keys.json` to get the list of all placeholder keys.
4. For every file in the copied `helm/` directory (including Chart.yaml, all values files, all template files, and _helpers.tpl), perform a find-and-replace for each `__KEY__` placeholder with the corresponding application-specific value provided in the inputs.
5. Remove `helm/template-keys.json` from the target repo (it's only needed as a reference).
6. Validate the Helm chart by running `helm lint helm/` in the target repo.
7. Create a new branch named `feat/add-helm-charts-<APP_NAME>`.
8. Commit all changes with message `feat: add Helm charts for <APP_NAME> across all environments`.
9. Push the branch and raise a PR to the target repo's main/master branch with:
   - Title: `feat: Add Helm charts for <APP_NAME>`
   - Body: List all the replaced keys and their values for reviewability.
