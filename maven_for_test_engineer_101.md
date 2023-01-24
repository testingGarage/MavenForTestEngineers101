# Maven for a Software Test Engineer -- 101

## $ whoami
- **Ravisuriya Eswara**
	- Student of Software Testing
	- Software Test Engineer
		- Email: *ravisuriya1 at gmail dot com*
		- LinkedIn: *https://linkedin.com/in/ravisuriya*
		- Twitter: *https://twitter.com/testingGarage*
		- Blog: *https://testingGarage.blogspot.com*
		- GitHub: *https://github.com/testingGarage*
		- YouTube: *https://youtube.com/@testingGarage*

I'm Open To Work
[#openToWork](https://www.linkedin.com/in/ravisuriya/)

# Let us build ...

> **Who is a Software Test Engineer?**


> **What is 101?**

 - It means, **Basic Information**
	 - The first "1" denotes the studying year
	 - The "0" denotes the specific topic
		 - 0 being generic
	- The last "1" denotes the first lesson
	
 - And, a web page says it also means, *Laugh Out Loud*

source: www

## Context and Audience
- This is 101, which also means laugh out loud
	- > not just ask questions; you can laugh in this talk
- Why this talk and title?
	- Those typical questions we encounter consistently
		- Which questions?
- How you have to see this talk?
	- It is compiled for a Software Test Engineer
		- To get started with Maven
		- To know and be aware of using Maven better
- What is in this talk?
	- > Focusing on the basics that we should know about the Maven
- Highly helpful to those who have not used Maven
	- > Super helpful to those who know and use Maven
	- Why?
		- At the end!



# 1.  What is Apache Maven?
- An Open Source Project
	- >Beyond a build tool
- Used for building and managing any Java-based project
- And, most of us use it in automation :) 
	- Why?
	- How?
	- We copy paste the POM of someone else or of some other project having similar context
		- And, later we build the project
	- Yet, do I know the fundamentals of it?

# 2. More about Maven
- Maven, is a Yiddish word
	- >an expert, or
	- >accumulator of knowledge
- Maven builds a project using
	- its POM (Project Object Model)
		- pom.xml
			- do you remember this?
	- set of plugins
- It sticks to design philosophy -- convention over configuration
	- > https://en.wikipedia.org/wiki/Convention_over_configuration
	- > https://roost.ai/blog/the-influence-of-maven-principle-on-modern-application-architecture
- It is built on top of Java
	- It works on any OS that runs a JVM
- It was formerly part of the Jakarta Project
	- which created and maintained Open Source Software for the Java Platform
	- today, Maven is hosted by Apache Software Foundation
- And, the creator of Maven
	- **Jason van Zyl**
		- https://twitter.com/jvanzyl
		- https://github.com/jvanzyl
		- https://www.crunchbase.com/person/jason-van-zyl

*Thank you, Jason van Zyl, for Maven* 🙏🏽🙂
*Thank you committers, maintainers and community of Maven for giving us the usable Maven* 🙂🙏🏽



# 3. In This Talk
- We will use Windows OS and its context to explore Maven
- Understand POM
	- POM
		- pom.xml structure and what it is
	- Super POM
	- Effective POM
- We will have a short demo of Maven commands


# 4. Maven Archetype
- Archetype is a Maven project template
	- It  provides a way to quickly jumpstart your work
- For example:
	- maven-archetype-simple
	- maven-archetype-quickstart
	- maven-archetype-webapp
	- com.atlassian.maven.archetypes:jira-plugin-archetype

# 5. POM
- It is **Project Object Model**
	- the fundamental unit of work in Maven
- POM files maintain parent-child relationship between them
	- files and not a file?
	- > Super POM
	- > Project POM

### A simple POM
```xml
<project>
	<modelVersion>4.0.0</modelVersion>
	<groupId>io.testing.garage</groupId>  
	<artifactId>SeleniumWebDriverTestNG</artifactId>  
	<version>1.0.0</version>
</project>
```


# 5.1 Super POM
- It is Maven's default POM
- All POMs extend the Super POM
	- unless explicitly set
- In Windows OS, I see the Super POM here
	- \maven\apache-maven-3.5.4\lib\maven-model-builder-3.5.4.jar\org\apache\maven\model\pom-4.0.0.xml
		- ***Note**: I'm using Maven 3.5.4 during this demo*
- Refer to a Super POM that I picked from the above said JAR file
	- https://github.com/testingGarage/maven-101

## 5.1.1 Abstract View of Super POM file
![Abstract View of Super POM file with key configuration elements by Prabath](https://user-images.githubusercontent.com/9585769/213533209-68058011-eb81-47e2-8ee4-e9adc1c38721.png "Abstract View of Super POM file with key configuration elements by Prabath")

## 6. Analyzing a POM file
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<project xmlns="http://maven.apache.org/POM/4.0.0"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">  
    <modelVersion>4.0.0</modelVersion>  
  
    <groupId>io.testing.garage</groupId>  
    <artifactId>SeleniumWebDriverTestNG</artifactId>  
    <version>1.0.0</version>  
  
    <properties>  
        <maven.compiler.source>8</maven.compiler.source>  
        <maven.compiler.target>8</maven.compiler.target>  
    </properties>  
  
    <dependencies>  
          <dependency>  
            <groupId>org.seleniumhq.selenium</groupId>  
            <artifactId>selenium-java</artifactId>  
            <version>4.3.0</version>  
            <scope>test</scope>  
        </dependency>  
  
        <dependency>  
            <groupId>org.testng</groupId>  
            <artifactId>testng</artifactId>  
            <version>6.14.3</version>  
            <scope>test</scope>  
        </dependency>  
  
        <dependency>  
            <groupId>org.slf4j</groupId>  
            <artifactId>slf4j-api</artifactId>  
            <version>1.7.36</version>  
        </dependency>  
  
        <dependency>  
            <groupId>ch.qos.logback</groupId>  
            <artifactId>logback-classic</artifactId>  
            <version>1.1.7</version>  
        </dependency>  
  
        <dependency>  
            <groupId>org.assertj</groupId>  
            <artifactId>assertj-core</artifactId>  
            <version>3.23.1</version>  
            <scope>test</scope>  
        </dependency>  
  
        <dependency>  
            <groupId>io.github.bonigarcia</groupId>  
            <artifactId>webdrivermanager</artifactId>  
            <version>5.2.3</version>  
        </dependency>  
    </dependencies>  
  
</project>
```
# 7. Dependency Scopes
Two types of dependencies in Maven
- Direct
- Transitive

I made this mnemonic to quickly recollect the scopes for a dependency
-	**SIT CPR**
	-	I give this assistive example to my mentees so it is easy to recollect the dependency scopes
		-	***S**tart **I**immediately **T**he **CPR** to this person*
		-	Or, ***SIT** we will watch the **CPR** demo*

![Maven Dependency Scopes](https://user-images.githubusercontent.com/9585769/213812607-f21f8ab8-bf63-4211-b0a6-825948818a77.png "Maven Dependency Scopes")

# 8. Classpath and Buildpath

## 8.1 Classpath

- In Maven's context, it is the dependencies classpath
- It is used for running the application
- This path includes the needed libraries to run the application
	- In our case, **to run the automation code**

For example, the dependencies classpath on my machine at the time demo can be found at:
> *C:\Users\userName\.m2\repository*

The below command helps to display the classpath:
> mvn dependency:build-classpath

## 8.2 Build Path

- In Maven's context, it is the path that points to JAVA_HOME
- It is used to build the application
	- In our case, **to build the automation project**
- The buildpath destination includes
	- Project code
	- The Java libraries required to compile the project

# 9. Managing POM Dependencies
- POM Inheritance
	- The Parent POM define all the common dependencies used by its child
	- It is defined under the section dependencyManagement
- Dependency Grouping
	- All the common dependencies are grouped into one single POM file
		- The packaging type will be pom

This is a 102 topic to discuss.  But, why wait? Explore these two ways of managing POM dependencies on understanding the topics covered in 101.

# 10. Transitive Dependencies
- It automatically identifies the dependency of the project dependencies
	- It gets all these dependencies into the build path of the project
## Demo
- We will pick one POM file and look at the Transitive Dependencies


# 11. Maven Plugins

- A Maven plugin is a collection of goals
	- Each goal is responsible for performing a specific action
- Maven at the core it is a plugin execution framework
	- All work is done by plugins
- Types of Plugin
	- Build Plugins
		- It will be executed during the build
		- These plugins are configured in the <build\/> element from the POM
	- Reporting Plugins
		- It will be executed during the site generation
		- These plugins are configured in the <reporting\/> element from the POM

## 11.1 Types of Maven Plugins

![](https://user-images.githubusercontent.com/9585769/213537004-460f0b14-f490-4a5c-9609-a2e4a2d4263a.png "Maven Plugins Type")


# 12. Build Lifecycles
## 12.1 Maven Build Lifecycle
The build lifecycle means, the process of building and distributing an artifact from a project is well defined.  The lifecycle defines the order of execution to produce the artifact.  

The lifecycle has well defined phases.
Each phase has goal defined to it by Maven Plugins.

## 12.2 Three Built-in Build Lifecycles
- default
	- handles the project deployment
- clean
	- handles the project cleaning
- site
	- handles the creation of project's website



## 12.3 Standard Lifecycles in Maven

![Standard Maven Lifecycles](https://user-images.githubusercontent.com/9585769/213705942-e4b9ce3c-79ff-4db9-9838-0a7217ef579a.png "Standard Maven Lifecycles")
## 12.4 Examples of Lifecycle, Phase, & Goal
## 12.4.1. Clean Lifecycle
- few "clean" lifecycle commands
	- > mvn clean
	- > mvn clean test
	- > mvn clean test install


|Phase  |plugin:goal  |
|--|--|
|clean|clean:clean  |  


## 12.4.2. Default Lifecycle
- a "default" lfiecyle command
	- > mvn test

| Phase |plugin:goal  |
|--|--|
|compile|compiler:compile|
| test |surefire:test  |
|install|install:install|

## 12.5 Mnemonic -- LPG

Now, we know that a Maven build has lifecycle
- Each lifecycle has phases
- Each phase is a sequence of goals
	- Each goal is responsible for a specific task

To make it simple for my mentees, I came up with this mnemonic LPG.
- LPG
	- >**Lifecyle -> Phases -> Goals**
- example: ***mvn clean test install***

# 13. Maven Commands and Execution

Maven commands are confusing when we begin!  That's okay!  

It is simple when we practice by understanding the concepts.
- Maven commands are a mix of
	-	Build lifecycles
	-	Build phase
	-	Build goals

All of these are plugins! Hence, the Maven is a framework with collection of plugins.

## 13.1 Maven Command Structure

- > **mvn [options] [<phase(s)>] [<goal(s)>]**


## 13.2 What Maven command holds?
The Maven command has two elements
-	mvn
-	a lifecycle
-	One or more build phases/goals  
 

For example, let us pick the command
- > ***mvn clean test install***
	- The "mvn" command executes Maven
	- The build lifecycle "clean"
	- The phase and goal "test" and install

## Maven Commands

The most often commands that I use in context with Software Testing and Automation for execution and debugging.

| Maven Command| Description  |
|--|--|
| mvn -version |*To know the installed Maven version*  |
|mvn -h|*To see the help information*|
|mvn help:system|*To view all environment variables & system properties*|
|mvn clean install -Dmaven.surefire.debug |*To run Maven in the debugging mode*|
|mvn clean install -x| *To enable debug level logging*|
|mvn dependency:tree|*To build dependency tree; when problem with dependencies, this helps to find from where the dependencies are coming from*|
|mvn help:active-profiles|*To list all the active profiles in the project*|
|mvn help:effective-pom|*To look at the default settings from super POM and configurations defined in the project's POM*|
|mvn help:effective-settings|*To display the settings which configures Maven execution in various ways*|
|mvn dependency:build-classpath|*To list all the JAR files and directories in the build classpath*|
|mvn dependency:analyze|*To analyze dependencies of project and determine which are: used and declared; used and undeclared; unused and declared*|
|mvn \<phase>|*To execute a phase of a lifecycle; example: **mvn test***|
|mvn help:describe -Dcmd=\<commandName>|*To know about the phase and goal; example: **mvn help:describe -Dcmd=clean***|
|mvn help:describe -Dplugin=\<pluginName>|*To look at the details of goals defined inside the plugin; example: **mvn help:describe -Dplugin=clean***|
|mvn \<phase>:\<plugin>|*To execute the goal of plugin; example: **mvn surefire:test***|



# 14. Document Version
> 1.0

# 15. References

1.  [https://maven.apache.org/index.html](https://maven.apache.org/index.html)
2.  [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)
3.  [https://maven.apache.org/install.html](https://maven.apache.org/install.html)
4.  [https://maven.apache.org/configure.html](https://maven.apache.org/configure.html)
5.  [https://maven.apache.org/community.html](https://maven.apache.org/community.html)
6.  [https://maven.apache.org/guides/introduction/introduction-to-the-pom.html](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
7.  [https://maven.apache.org/guides/mini/guide-naming-conventions.html](https://maven.apache.org/guides/mini/guide-naming-conventions.html)
8.  [https://maven.apache.org/guides/introduction/introduction-to-archetypes.html](https://maven.apache.org/guides/introduction/introduction-to-archetypes.html)
9.  [https://maven.apache.org/guides/mini/guide-creating-archetypes.html](https://maven.apache.org/guides/mini/guide-creating-archetypes.html)
10.  [https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)
11.  [https://howtodoinjava.com/maven/maven-dependency-scopes/](https://howtodoinjava.com/maven/maven-dependency-scopes/)
12.  [https://howtodoinjava.com/maven/maven-parent-child-pom-example/](https://howtodoinjava.com/maven/maven-parent-child-pom-example/)
13.  [https://www.baeldung.com/maven](https://www.baeldung.com/maven)
14.  [https://www.baeldung.com/maven-super-simplest-effective-pom](https://www.baeldung.com/maven-super-simplest-effective-pom)
15.  [https://www.baeldung.com/maven-plugin-override-parent](https://www.baeldung.com/maven-plugin-override-parent)
16.  [https://maven.apache.org/shared/maven-archiver/examples/classpath.html](https://maven.apache.org/shared/maven-archiver/examples/classpath.html)
17.  [https://guntherrotsch.github.io/blog_2020/maven-classpath.html](https://guntherrotsch.github.io/blog_2020/maven-classpath.html)
18.  [https://github.com/rest-assured/rest-assured/blob/master/pom.xml](https://github.com/rest-assured/rest-assured/blob/master/pom.xml)
19.  [https://stackoverflow.com/questions/16205778/what-are-maven-goals-and-phases-and-what-is-their-difference](https://stackoverflow.com/questions/16205778/what-are-maven-goals-and-phases-and-what-is-their-difference)
20.  [https://www.baeldung.com/maven-goals-phases](https://www.baeldung.com/maven-goals-phases)
21.  [https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Lifecycle_Reference](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Lifecycle_Reference)
22.  [https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Build_Lifecycle_Basics](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Build_Lifecycle_Basics)
23.  [https://en.wikipedia.org/wiki/Apache_Maven#Build_lifecycles](https://en.wikipedia.org/wiki/Apache_Maven#Build_lifecycles)
24.  [https://medium.com/@yetanothersoftwareengineer/maven-lifecycle-phases-plugins-and-goals-25d8e33fa22](https://medium.com/@yetanothersoftwareengineer/maven-lifecycle-phases-plugins-and-goals-25d8e33fa22)
25.  [https://stackoverflow.com/questions/26607834/maven-lifecycle-vs-phase-vs-plugin-vs-goal](https://stackoverflow.com/questions/26607834/maven-lifecycle-vs-phase-vs-plugin-vs-goal)
26.  [https://stackoverflow.com/questions/16205778/what-are-maven-goals-and-phases-and-what-is-their-difference](https://stackoverflow.com/questions/16205778/what-are-maven-goals-and-phases-and-what-is-their-difference)
27.  [https://maven.apache.org/plugins/](https://maven.apache.org/plugins/)
28.  Mastering Apache Maven 3 - Prabath Siriwardena
29.  [https://testinggarage.blogspot.com/search/label/Automation](https://testinggarage.blogspot.com/search/label/Automation)
30.  [https://testinggarage.blogspot.com/search/label/Testing](https://testinggarage.blogspot.com/search/label/Testing)
31.  [https://testingGarage.blogspot.com/search/label/Maven](https://testingGarage.blogspot.com/search/label/Maven)
32. https://stackoverflow.com/questions/26607834/maven-lifecycle-vs-phase-vs-plugin-vs-goal
33. https://www.codekru.com/maven/all-about-maven-build-lifecycle
34. https://gist.github.com/testingGarage/f6ebc3ec82293bc36ae7a2f882164d5b
35. https://gist.github.com/testingGarage/ea4586b0f8e40a5dd8b640e544c22c4a
36. https://www.baeldung.com/maven-goals-phases
37. https://stackoverflow.com/questions/11556170/how-to-invoke-maven-default-lifecycle
