## 2.1. Testing in Context of Software Development Lifecycles

A software development lifecycle (SDLC) model is an abstract, high-level representation of the software development process. A SDLC model defines how different development phases and types of activities performed within this process relate to each other, both logically and chronologically. Examples of SDLC models include: sequential models (e.g., waterfall model, V-model), iterative models (e.g., spiral model), and incremental models.

Software development processes can be also described by more detailed models, e.g., various software development methods and agile practices. Examples include: acceptance test-driven development (ATDD), behavior-driven development (BDD), domain-driven design (DDD), extreme programming (XP), feature-driven development (FDD), Kanban, Lean IT, Scrum, test-driven development (TDD).

### 2.1.1. Impact of Software Development Lifecycle on Testing

Testing must be integrated into the software lifecycle to succeed. The choice of SDLC impacts on:

* Scope and timing of test activities (e.g., test levels and test types)
* Level of detail of test documentation
* Choice of test techniques and test practices
* Extent of test automation

In sequential models, in initial phases testers typically participate in requirement reviews and test design. The product in the executable form is usually delivered in the late phases, so typically dynamic testing cannot be performed early in the lifecycle.

In some iterative and incremental models, it is assumed that each iteration ends up with a working product increment. This implies that in each iteration testing, both static and dynamic, may be performed at all test levels. Frequent delivery of increments requires fast feedback and extensive regression testing.

Agile development methods assume that change may occur throughout the project. Therefore, lightweight work product documentation and extensive test automation to make regression testing easier to handle are favored in Agile projects. Also, most of the manual testing tends to be done using experience-based techniques (see Section 4.4) that do not require extensive prior planning.

### 2.1.2. Software Development Lifecycles and Good Testing Practices

Good testing practices independent of the chosen SDLC model, include the following:

* For every software development activity, there is a corresponding test activity, so that the quality control can cover all the aspects
* Each test level (see chapter 2.2.1) has test objectives specific to the appropriate SDLC phase or type of activities, so that testing can check the test object to the fullest extent possible
* Test analysis and design for a given test level begin during the corresponding development phase of the SDLC, so that testing can adhere to the early testing principle (see section 1.3)
* Testers are involved in reviewing work products as soon as drafts of these documents are available, so that the shift-left approach is followed (see section 2.1.5)

### 2.1.3. Testing as a Driver for Software Development

Test-driven development (TDD), acceptance test-driven development (ATDD), and behavior-driven development (BDD) are similar development approaches, where tests are defined as a means of directing development. Each of these approaches implements the testing principle of "Early testing saves time and money" (see section 1.3) and follows a shift-left approach (see section 2.1.5), since the tests are defined before the code is written. They support an iterative approach to development. Those approaches are characterized as follows:

Test-Driven Development (TDD):

* TDD directs the coding through test cases (instead of extensive software design)
* Tests are written first, then the code is written to satisfy the tests, and then the tests and code are refactored

Acceptance Test-Driven Development (see section 4.5.3):

* Derive tests from acceptance criteria as part of the design process (Gärtner 2011)
* Tests are written even before the part of the application is developed to satisfy the tests

Behavior-Driven Development (BDD):

* Express the desired behavior of an application by test cases written in a simple form of natural language, that is easy to understand by stakeholders – usually using the given/when/then format. (Chelimsky 2010)
* Test cases are then compiled and translated in (automatically) executable tests

For all the above approaches, tests may persist as automated tests to ensure the code quality in future adaptions / refactoring.

### 2.1.4 DevOps and Testing

DevOps is an organizational transformation aiming to create synergy by getting development, testing and operations to work together to achieve a set of common goals. DevOps requires a cultural shift within an organization to bridge the gaps between development, testing and operations while treating their functions with equal value. DevOps promotes team autonomy, fast feedback, integrated toolchains, and technical practices like continuous integration (CI) or continuous delivery. This allows the teams to build, test and release high-quality code faster through a DevOps delivery pipeline (Kim 2016).

From the testing perspective, the benefits of DevOps are:

* Fast feedback on the code quality, and whether changes adversely affect existing code
* CI creates a shift-left in testing (see section 2.1.5) by encouraging developers to submit high quality code accompanied by component tests
* DevOps facilitates establishing stable test environments
* Automation through a delivery pipeline reduces the need for repetitive manual testing
* The risk of regression is minimized due to the scale and range of automated regression tests

DevOps is not without its risks and challenges, which include:

* The DevOps delivery pipeline must be defined and established
* CI tools have to be introduced and maintained
* Test automation requires additional resources and may be difficult to establish and maintain

### 2.1.5. hift-Left Approach

The testing principle "Early testing saves time and money" (see section 1.3) is sometimes referred to as "shift-left" because it is an approach where testing is performed earlier in the life cycle. Shift-left normally suggests that testing should be done earlier (e.g., not waiting for code to be implemented or for components to be integrated), but it does not mean that testing later in the life cycle should be neglected.

There are some good practices that illustrate how to achieve a "shift-left" in testing, which include:

* Review the specification from the perspective of testing. These specification review activities often find potential defects, such as ambiguities, incompleteness, and inconsistencies
* Write tests before the code is written and have the code run against a test harness during implementation
* Perform CI and continuous delivery as it comes with fast feedback and automated component tests to accompany source code when it is submitted to the code repository
* Perform static analysis of source code prior to dynamic testing, or as part of an automated process
* Perform non-functional testing at the component testing level, where possible. This is a form of shift-left as these non-functional test types tend to be performed later in the SDLC when a complete system and a representative test environment are available.

A shift-left approach might result in extra training/effort/costs earlier in the process.

### 2.1.6. Retrospectives and Process Improvement

Retrospectives (also known as "lessons learned meetings" or evaluations) might be held when needed, often at the end of a project, release milestone or iteration. In these meetings the participants (not only testers, but also e.g., developers, architects, product owner, business analysts) discuss:

* what was successful,
* what was not successful and could be improved, and
* how to incorporate the improvements and retain the successes in the future.

The results should be recorded and might be part of e.g., the test completion report (see section 5.3.2). It is important that follow-up activities occur. Retrospectives are critical to the successful self-organization of the development teams and the continuous improvement.

Typical benefits for testing include:

* Increased test effectiveness / productivity
* Increased test case quality
* Team satisfaction
* Improved requirements quality
* Better cooperation of development and testing

The timing and organization of the retrospectives depend on the particular SDLC model being followed.

## 2.2. Test Levels and Test Types

Test levels are groups of test activities that are organized and managed together. Each test level is an instance of the test process, performed in relation to software at a given stage of development, from individual components to complete systems or, where applicable, systems of systems.

Test levels are related to other activities within the SDLC. In sequential SDLC models, the test levels are often defined such that the exit criteria of one level are part of the entry criteria for the next level. In some iterative models, this rule may not apply. Development activities may span through multiple test levels. Test levels may overlap.

Test types are groups of test activities related to specific characteristics and those test activities can be performed at every test level.

### 2.2.1. Test Levels

In this syllabus, the following five test levels are described.

* **Component testing** (also known as unit testing) focuses on testing components in isolation. It often requires specific support, such as test harnesses or unit testing frameworks. Component testing is normally performed by developers in their development environments.
* **Component integration testing** (also known as unit integration testing) focuses on testing the interfaces and interactions between integrated components. Component integration testing is heavily dependent on the integration strategy.
* **System testing** focuses on the overall behavior and capabilities of an entire system or product, often including functional testing of end-to-end tasks and the non-functional testing of quality characteristics. For some non-functional quality characteristics, it is preferred to test them on a complete system in a representative test environment (e.g., performance efficiency, security or usability). Using simulations is also possible. System testing is normally performed by the independent test team and relies heavily on specifications.
* **System integration testing** focuses on testing the interfaces and interactions between integrated systems or external services. System integration testing requires suitable test environments preferably similar to the operational environment.
* **Acceptance testing** focuses on validation and on demonstrating readiness for deployment, which means that the system fulfills the user's business needs. Ideally, acceptance testing should be performed by the end users. The main forms of acceptance testing are: user acceptance testing (UAT), operational acceptance testing (OAT), contractual/regulatory acceptance testing, alpha and beta testing.

Test levels are characterized by the following non-exhaustive list of attributes:

* Test object
* Test objectives
* Test basis
* Defects and failures
* Approach and responsibilities

### 2.2.2. Test Types

The following test types are addressed:

**Functional testing** involves tests that evaluate the functions that a component or system should perform. Functional requirements may be described in work products such as requirements specifications, user stories, use cases,functional specifications, or they may be undocumented. The functions are "what" the test object should do.

**Non-functional testing** evaluates attributes other than functional characteristics of systems and software. The ISO/IEC 25010 standard provides the following classification of the non-functional software product quality characteristics:

* Performance efficiency
* Compatibility
* Usability
* Reliability
* Security
* Maintainability
* Portability

Non-functional testing is the testing of "how well the system behaves". Non-functional testing can and often should start as early as possible. The late discovery of non-functional defects can pose a serious threat to the success of a project. Non-functional testing sometimes needs a very specific test environment, such as a usability lab for usability testing.

Similar to functional testing, different test techniques can be used to derive test conditions and test cases for non-functional testing.

**White-box testing** derives tests from the system's internal structure or implementation, contrary to functional and non-functional testing, where tests are derived from the requirements specifications. Internal structure may include code, architecture, work flows, and data flows within the system (see section 4.3). White-box test design, implementation and execution requires special skills or knowledge, such as the process of building code, how data is stored, and how to use coverage tools and to correctly interpret their results.

All the three above mentioned test types can be applied to all test levels, although the focus will be different at each level. Every test type can also be applied using static testing. The testing quadrants show the test types and test levels from different perspectives (see section 5.1.7).

### 2.2.3. Confirmation Testing and Regression Testing

Changes are typically made to a component or system to either enhance it by adding a new feature or to fix it by removing a defect. Testing should confirm that the changes have correctly implemented the functionality or corrected the defect.

**Confirmation testing** is to confirm that the original defect has been successfully fixed. Depending on the risk, one can test the fixed version of the software in several ways, including:

* withall the test cases that previously have failed due to the defect, or
* addingnew tests to cover any changes that were needed to fix the defect

However, when time or money is short, confirmation testing might be restricted to simply exercising the steps that should reproduce the failure caused by the defect and checking that the failure does not occur.

**Regression testing** is to confirm that no adverse consequences have been caused by a change, including a fix that has already been confirmation tested. These adverse consequences could affect the same component where the change was made, other components in the same system, or even other connected systems. Regression testing may not be restricted to the test object itself but can also be related to the environment.

Confirmation and regression testing are needed on all test levels if defects are fixed and changes aremade on these test levels.

Regression test suites are run many times and generally evolve with each iteration or release, so regression testing is a strong candidate for automation. Automation of these tests should start early in the project (see chapter 6). Where automated builds and CI are used, such as in DevOps (see section 2.1.4), it is good practice to also include automated regression testing. Depending on the situation, this may include regression tests on different levels.

## 2.3. Maintenance Testing

Testing the changes to a system in production includes both evaluating the success of the change implementation and the checking for possible regressions in parts of the system that remain unchanged (which is usually most of the system). Maintenance can involve planned releases / deployments and unplanned releases / deployments (hot fixes).

The scope of maintenance testing typically depends on:

* The degree of risk of the change
* The size of the existing system
* The size of the change

The triggers for maintenance can be classified as follows:

* Modifications, such as planned enhancements (i.e., release-based), corrective changes or hot fixes
* Upgrades or migrations of the operational environment, such as from one platform to another, which can require tests associated with the new environment as well as of the changed software, or tests of data conversion when data from another application is migrated into the system being maintained
* Retirement, such as when an application reaches the end of its life. When a system is retired, this can require testing of data archiving if long data-retention periods are required. Testing of restoring and retrieving procedures after archiving may also be needed.