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

![alt text](<How Does the Maven work.png>)

