# Report for assignment 4

## Project

Name: Hadoop

URL: https://github.com/apache/hadoop

One or two sentences describing it

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

[Link to patch in a format that is acceptable to the project.](https://github.com/jcroona/se19-project4-report/blob/master/YARN-1169.patch)

## Test logs

Overall results with link to a copy of the logs (before/after refactoring).

[Link to test logs (before/after refactoring)](https://github.com/jcroona/se19-project4-report/blob/master/testlog.md)

The refactoring itself is documented by the git log.

The refactor is carried out on the branch: `refactor-AuxServicesEvent`

## Effort spent

For each team member, how much time was spent in

1. plenary discussions/meetings; 8h 

2. discussions within parts of the group; 6h

3. reading documentation; 5h

4. configuration; 3h

5. analyzing code/output; 1h

6. writing documentation; 4h

7. writing code; 3h

8. running code? 1h

## Overall experience

One of the main take-aways from the project is that tasks in such large projects could be more difficult than it seems. There could be a lot of dependencies that you don’t know about and it takes more time than expected. Since we chose a new project for this assignment we got some more experience from working with large scale open-source projects. 

