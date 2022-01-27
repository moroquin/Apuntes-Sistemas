To build with dependencies just need to add in the pom.xm

```XML
<build>
	<plugins>
		<plugin>
			<artifactId>maven-assembly-plugin</artifactId>
			<configuration>
				<descriptorRefs>
					<descriptorRef>jar-with-dependencies</descriptorRef>
				</descriptorRefs>
			</configuration>
		</plugin>
	</plugins>
</build>
```

And in order to generate the jar file with dependencies, execute in bash

```bash
	mvn compile ; mvn package ; mvn install assembly:assembly p
```



To execute the jar file just execute 

```bash
java -cp target/cats-project-1.0-SNAPSHOT-jar-with-dependencies.jar com.moroquin.App
```


Sometimes it is necesary to add some properties in order to avoid error for the compilation  in the pom.xml

```XML
<properties>
	<maven.compiler.source>17</maven.compiler.source>
	<maven.compiler.target>17</maven.compiler.target>
</properties>
```

