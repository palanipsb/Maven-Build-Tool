# Apache Maven

## Maven Overview
    Maven is a build tool
    Dependency management tool
    Project management tool
    Standardized approach to building software
    command line tool
    IDE integration

### Build Tool
        Creates deployable artifacts from source code
        Automated/repeatable builds
        Deploing artifacts on servers
        IDE independence
        Integration with other build tools
### Dependency management (Central Repository)
        Download project dependencies from centralized repositories
        Automatically resolve the libraries required by project dependencies
        Dependency scoping
### Project Management
        Artifact versioning
        Change logs
        Documentation
        Javadocs
        Reports
### Standardized approach
        Uniformity across projects through patterns
        Convention over configuration
        Consistent path for all projects
        Philosophy of Maven

## Maven Landscape
### Project Object Model (POM)
        Describes, configures and customizes a Maven Project
        Mvane reads the pom.xml file to build a project
        Defines the address for the project artifact using a coordinate system
        Specifies project information, plugins, goals, dependencies and profiles
### Repositories
        Holds build artifacts and dependencies of varying types
        Local repositories (local cache)
        Remote repositories
        Local repository takes precedence during dependency resolution
### Plugins and Goals
        Plugin is a collection of goals (ex: compiler plugin)
        Goals perfoem the action in Maven builds
        All work is doine via plugins and goals
        Called independently or as part of lifecycle phase
### Lifecycle and Phases
        It is a sequence of named phases
        Phases are executed sequenctially
        3 lifecycles: clean, default, site
        Executing a phase executes all previous phases

## Maven Technical Overview
### How does the Maven work

![alt text](<images/How Does the Maven work.png>)
        
## pom.xml Specification       

        pom ==> Project Object Model
        
        <project>       # It specifies the XML schema, also make sure that our XML adheres to correct structure and version defined by maven.
        
        <parent>        # (Super POM) Used to define the Parent project, Current project inherit the configurations from the specified parent project.
                        # Which in turn Super POM.
                        # If this <parent> field is not specified, maven by-default inherit the configurations from "Super Pom".
                        # This is the link of maven Super POM: https://maven.apache.org/ref/3.0.4/maven-model-builder/super-pom.html
        
        <groupId>       # Unique identifier of your project
        <artifactId>
        <version>

        <properties>    # Define key-value pair for configuration. Can be referenced through out the pom file.

        <repositories>  # This is from where Maven look for project dependencies and download the artifacts (jar)

        <dependencies>  # This is where we declare the dependencies that our project relies on.

        <build>         # It is the actual maven project to build application

## Maven Build lifecycle phases
        - If you want to run "package" phase, all its previous phase will get executed first.
        - And if you want to run sepcific goal of a particular phase, then all the goals of previous phases + current phase will get run.
        - Each phases can have multiple goals (Goal ==> Task)

### Phases of Maven Lifecycle
![alt text](<images/Phases Maven Lifecycle.png>)

### Maven Build Lifecycle
![alt text](<images/Maven Build Lifecycle.png>)

### Maven Default Lifecycle
![alt text](<images/Maven Default Lifecycle.png>)

### Maven - Sample Phase and Goal (Validate)

```xml

<plugin>
        <groupId>org.maven.plugins</groupId>
        <artifactId>maven-checstyle-plugin</artifactId>
        <version>3.1.2</version>
        <executions>
                <id>validate-checkstyle</id>
                <phase>validate</phase>
                <goals>
                        <goal>check</goal>
                </goals>
        </executions>
        <configuration>
                <configLocation>myCodeStyle.xml</configLocation>
        </configLocation>
</plugin>

```

### Ant Sample Phase and Goal (Compile)

```xml

<project>
        <target name="compile">
                <javac destdir="{our destination directory}">
                        <src>
                                <pathelement location="src/main/java"/>                        
                        </src>
                </javac>
        </target>

</project>

```

        - When we compare Ant and Maven, we clearly understood that Maven need only What to do command, however for Ant, What to do command and How to do command needed.

### Frequently used Phases:
        validate        # validate the project is correct and all necessary information is available
        compile         # compile the source code of the project
        test            # test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
        package         # take the compiled code and package it in its distributable format, such as a JAR.
        verify          # run any checks on results of integration tests to ensure quality criteria are met
        install         # install the package into the local repository, for use as a dependency in other projects locally (~/.m2/repository)
        deploy          # done in the build environment, copies the final package to the remote repository for sharing with other developers and projects.