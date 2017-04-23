This is maven based simple hello- world project

How to create this project


First download maven

Then run below command to create maven project in your local

mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Then add below entries to add your class in manifest so when you run this jar it will execute this class and give the output


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

once project is created go that folder

echo "This is maven based simple hello- world project" >> README.md

then READEME.md will be created in your dir


use the below commands

git init

git add .


git commit -m "first commit"

git remote add origin https://github.com/malli1234/repo.git

git push -u origin master


