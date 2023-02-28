# Start Up

1. Maven install
2. Create maven project `mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false` (replace group id, artifact id)
   
   For this example do it as follow.
   `mvn archetype:generate -DgroupId=com.devtee.microservice -DartifactId=devtee-microservice -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false`
3. Delete src folder.
4. Modify pom.
	1. Update website URL.
	2. Add dependency management.
	   ```xml
	   <dependencyManagement>
		   <dependencies>
			   <dependency>
				   <groupId>org.springframework.boot</groupId>
				   <artifactId>spring-boot-dependencies</artifactId>
				   <version>${spring.boot.dependencies.version}</version>
				   <scope>import</scope>
				   <type>pom</type>
			   </dependency>
		   </dependencies>
	   </dependencyManagement>
	   ```
	   3. Add common dependencies.
	      ```xml
	      <dependencies>
		      <dependency>
			      <groupId>org.projectlombok</groupId>
			      <artifactId>lombok</artifactId>
		      </dependency>
		      <dependency>
			      <groupId>org.springframework.boot</groupId>
			      <artifactId>spring-boot-starter-test</artifactId>
		      </dependency>
	      </dependencies>
```
	4. Replace plugins with follow.
	   ```xml
	   <plugins>
		   <plugin>
			   <groupId>org.springframework.boot</groupId>
			   <artifactId>spring-boot-maven-plugin</artifactId>
			   <version>${spring.boot.maven.plugin.version}</version>
		   </plugin>
	   </plugins>
```
	5. Update maven properties.
	   ```xml
	   <properties>
		   <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		   <maven.compiler.source>19</maven.compiler.source>
		   <maven.compiler.target>19</maven.compiler.target>
		   <spring.boot.dependencies.version>3.0.3</spring.boot.dependencies.version>
		   <spring.boot.maven.plugin.version>3.0.3</spring.boot.maven.plugin.version>
	   </properties>
```
