# Report for assignment 4

## Project

Name: Hadoop YARN

URL: https://github.com/apache/hadoop

The fundamental idea of YARN is to split up the functionalities of resource management and job scheduling/monitoring into separate daemons. The idea is to have a global ResourceManager (RM) and per-application ApplicationMaster (AM).

## Architectural overview (optional, as one item for P+)

## Selected issue(s)

Title: Refactor AuxServicesEvent into a AuxServicesAppEvent and AuxServicesContainerEvent.

URL: https://issues.apache.org/jira/browse/YARN-1169

The issue is to refactor the AuxServicesEvent class into two separate classes; AuxServicesAppEvent and AuxServicesContainerEvent. Currently the two cases are disjoint and are only managed through making the container value null for application events, and making the container null for container events.

## Onboarding experience

The onboarding documentation was quite extensive but building the project was complex and demanding, the project has a lot of dependencies and compiling the project takes a very long time. The recommended way of getting a build environment setup is to use docker, which adds to the number of tools that is required to build and develop the project, and it also adds some overhead, especially on OS X, as docker then runs the containers in a virtual machine with a high performance impact.
It is also very difficult to run individual tests and running all the tests is also very time consuming and demanding of the system. 


## Requirements affected by functionality being refactored

### Requirement 1: Datafields

The requirements for AuxServicesEvent are to store data surrounding an auxiliary services event. This stored data should be the following:

* **eventType**, which is one of the following; APPLICATION_INIT, APPLICATION_STOP, CONTAINER_INIT, CONTAINER_STOP, an instance of the AuxServicesEventType class.
* **user**, which is a string used to identify a user.
* **appId**, which is an instance of the ApplicationID.
* **serviceId**, which is a string used to identify the service.
* **serviceData**, which is a ByteBuffer.
* **container**, which is an instance of the container class.

### Requirement 2: Constructors

The required constructors for the class are the following:

* A constructor taking an eventType and an appId.
* A constructor taking an eventType and a container.
* A constructor taking eventType, user, appId, serviceId and serviceData.

### Requirement 3: Get methods

The required methods to access data in the class are the following:

 
| Identifier  | getUser() | 
|---|---|
| Requirement description  | Return the data stored in the objects user field. |  
| Rationale | In order to use the data structure provided by the class the data must be easily accessible. |  
| Need | Basic |  
| Priority | High |
| Source | Hadoop YARN |
| Verifiability | The function returns the correct data. |
| Risk | None |
| Dependency |  None |
| Difficulty | Low |

| Identifier  | getApplicationID() | 
|---|---|
| Requirement description  | Return the data stored in the objects appId field.  |  
| Rationale | In order to use the data structure provided by the class the data must be easily accessible. |  
| Need | Basic |  
| Priority | High |
| Source | Hadoop YARN |
| Verifiability | The function returns the correct data. |
| Risk | None |
| Dependency |  None |
| Difficulty | Low |


| Identifier  | getServiceID() | 
|---|---|
| Requirement description  | Return the data stored in the objects serviceId field.  |  
| Rationale | In order to use the data structure provided by the class the data must be easily accessible. |  
| Need | Basic |  
| Priority | High |
| Source | Hadoop YARN |
| Verifiability | The function returns the correct data. |
| Risk | None |
| Dependency |  None |
| Difficulty | Low |


| Identifier  | getServiceData() | 
|---|---|
| Requirement description  | Return the data stored in the objects serviceData field. |  
| Rationale | In order to use the data structure provided by the class the data must be easily accessible. |  
| Need | Basic |  
| Priority | High |
| Source | Hadoop YARN |
| Verifiability | The function returns the correct data. |
| Risk | None |
| Dependency |  None |
| Difficulty | Low |


| Identifier  | getContainer() | 
|---|---|
| Requirement description  | Return the data stored in the objects container field. |  
| Rationale | In order to use the data structure provided by the class the data must be easily accessible. |  
| Need | Basic |  
| Priority | High |
| Source | Hadoop YARN |
| Verifiability | The function returns the correct data. |
| Risk | None |
| Dependency |  None |
| Difficulty | Low |

### Requirement 4: Inheritance 

The class inherits from AbstractEvent<AuxServicesEventType>, to keep functionality.

### Requirement 5: Class dependencies

The classes that depend on AuxServicesEvent must keep their functionality. These are ApplicationImpl.java, ContainerImpl.java, as well as the test classes TestApplication.java and TestContainer.java.


### Project plan for testing requirements and refactor the code

1. Start by adding additional test cases to cover the requirements.
2. Assert that the required functionality exists in this current state.
3. Start refactoring by adding two new classes.
4. Assert that all the function calls are correct according to the new classes.
5. Adapt tests to the new classes.
6. Run tests and see that all requirements are fulfilled.

#### More details about the refactoring

The class has currently four different constructor:
1. `public AuxServicesEvent(AuxServicesEventType eventType, ApplicationId appId)`
2. `public AuxServicesEvent(AuxServicesEventType eventType, Container container)`
3. `public AuxServicesEvent(AuxServicesEventType eventType, String user, ApplicationId appId, String serviceId, ByteBuffer serviceData)`
4. `public AuxServicesEvent(AuxServicesEventType eventType, String user, ApplicationId appId, String serviceId, ByteBuffer serviceData, Container container)`

The first constructor is for appEvents and the second one for containerEvents. The third one is also for appEvents but has three additional arguments: `user`, `serviceId` and `serviceData`. The last constructor has both ApplicationId and container, but this is never used in the project. When the refactoring is carried out we will have two classes with the follwing structure:

* AuxServicesAppEvent.java 

1. `public AuxServicesEvent(AuxServicesEventType eventType, ApplicationId appId)`

2. `public AuxServicesEvent(AuxServicesEventType eventType, String user, ApplicationId appId, String serviceId, ByteBuffer serviceData)`

* AuxServicesContainerEvent.java

1. `public AuxServicesEvent(AuxServicesEventType eventType, Container container)`


## Existing test cases relating to refactored code

The test cases tests configuration-based services and manifest-based services. The majority of tests use mock objects that try cases with different jar-files, class paths and some dependencies and overlaps. 
The functionality of the events are mainly tested by initializing, starting and stopping. Some invalid input is tested (i.e bad username), but all properties that can have null values are not fully covered. AuxServiceEvent has four different constructors but only two of them are tested. To fully cover the requirements tests will be needed that cover all of the constructors and all get methods.


## The refactoring carried out

(Link to) a UML diagram and its description

[UML diagram before](https://github.com/jcroona/se19-project4-report/blob/master/UML_before.png)

[UML diagram after](https://github.com/jcroona/se19-project4-report/blob/master/UML_after.png)

[Link to patch in a format that is acceptable to the project.](https://github.com/jcroona/se19-project4-report/blob/master/YARN-1169.patch)

## Test logs

Overall results with link to a copy of the logs (before/after refactoring).

[Link to test logs (before/after refactoring)](https://github.com/jcroona/se19-project4-report/blob/master/testlog.md)

The refactoring itself is documented by the git log.

The refactor is carried out on the branch: `refactor-AuxServicesEvent`
[Link to branch refactor-AuxServicesEvent](https://github.com/jcroona/hadoop/tree/refactor-AuxServicesEvent)

## Effort spent

For each team member, how much time was spent in

1. plenary discussions/meetings; 6h 

2. discussions within parts of the group; 3h

3. reading documentation; 5h

4. configuration; 4h

5. analyzing code/output; 4h

6. writing documentation; 4h

7. writing code; 4h

8. running code? 1h

#### Time spent on choosing a project:
We spent several hours on choosing a project to work with. 

One project that we looked at was geode. We estimate that around 2 hours (as a group) only looking at refactor issues with geode. This included reading documentation/code and trying to figure out if the issues were feasible - as well as actually figuring out how to building the project and running the tests. One issue that we actually considered doing was the issue: ["AsyncEventServiceImpl needs refactored"](https://issues.apache.org/jira/browse/USERGRID-1107). We actually started writing some plans for refactoring the code based on this issue, but then realized that were some uncertainties regarding error handling that was too complex for us to solve, so we dropped the issue. We also spent a lot of time looking at other projects than geode as well.

In addition to this, when we eventually chose our project (hadoop yarn) figuring out how to build the project and run the tests took a few hours. For instance, none of us had any experience with maven or docker which made the building take more time than expected. Running individual tests inside a single module also took some time figuring out. This was partly due to unclear documentation (in our opinion).

We estimate that it took around 8-9 hours to find our issue and figure out how to build it and run the tests, to start working with the refactor itself.



## Overall experience

One of the main take-aways from the project is that tasks in such large projects could be more difficult than it seems. There could be a lot of dependencies that you don’t know about and it takes more time than expected. Since we chose a new project for this assignment we got some more experience from working with large scale open-source projects. 

