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

The onboarding documentation was quite extensive but building the project was complex and demanding, the project has a lot of dependencies and compiling the project takes a very long time. It is also very difficult to run individual tests and running all the tests is also very time consuming and demanding of the system.

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

* **getUser()**, returning data stored in the user field.
* **getApplicationID()**, returning data stored in the appId field.
* **getServiceID()**, returning data stored in the serviceId field.
* **getServiceData()**, returning data stored in the serviceData field.
* **getContainer()**, returning data stored in the container field.

### Requirement 4: Inheritance 

The class inherits from AbstractEvent<AuxServicesEventType>, to keep functionality.

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

The first constructor is for appEvents and the second one for containerEvents. The third one is also for appEvents but has two additional arguments, user and serviceData. The last constructor has both ApplicationId and container, but this is never used in the project. When the refactoring is carried out we will have two classes with the follwing structure:

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

## Test logs

Overall results with link to a copy of the logs (before/after refactoring).

The refactoring itself is documented by the git log.

## Effort spent

For each team member, how much time was spent in

1. plenary discussions/meetings;

2. discussions within parts of the group;

3. reading documentation;

4. configuration;

5. analyzing code/output;

6. writing documentation;

7. writing code;

8. running code?

## Overall experience

What are your main take-aways from this project? What did you learn?

Is there something special you want to mention here?
