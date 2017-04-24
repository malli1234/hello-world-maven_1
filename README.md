This is maven based simple hello- world project

How to create this project


First download maven

Then run below command to create maven project in your local

mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Then add below entries in pom.xml to add your class in manifest so when you run this jar it will execute this class and give the output


<build>

    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <configuration>
          <archive>
    <manifest>
	<mainClass>com.mycompany.app.App</mainClass>
    </manifest>
          </archive>
        </configuration>
      </plugin>
    </plugins>
  </build>








TO ADD THIS TO GIT REPO:

========================

first create new repo in git hub with out readme or gitgonroe

once project is created go to your folder on your local

and then create README.md file in project dir

------------------------------

echo "This is maven based simple hello- world project" >> README.md




use the below commands to add this new project to git hub

git init

git add .


git commit -m "first commit"

git remote add origin https://github.com/malli1234/repo.git

git push -u origin master




OTHER IMPOTANT GIT COMMANDS
===========================

config --global user.name "malli1234"

config --global user.email vadlamudimalli@gmail.com


git clone https://github.com/malli1234/hello-world.git       (will clone master branch named with hello-world)

git clone -b dst_osm_1.17.0 https://github.com/malli1234/hello-world.git dst_osm_1.17.0  (will clone dst_osm_1.17.0 branch (only) of hello-world repo)


git add .

git checkout .     (if you add any changes and then want to revert, it will wipe out your changes on your local)


git status


git commit -m "second edit"     (to stage the changes on your local)

git reset HEAD .                (to revert staged saved changes)  


git push



once it is pushed to git hub go to git hub and you can pull the request to merge to master repo from your branch



if any changes made in git hub and want to get the update to your local

========================================================================

git pull origin




