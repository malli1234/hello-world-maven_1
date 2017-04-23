﻿This is maven based simple hello- world project

How to create this project


First download maven

Then run below command to create maven project in your local

mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false


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
