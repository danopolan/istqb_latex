## 1.1 What is Testing?

Software systems are an integral part of our daily life. Most people have had experience with softwarethat did not work as expected. Software that does not work correctly can lead to many problems,including loss of money, time or business reputation, and, in extreme cases, even injury or death. Software testing assesses software quality and helps reducing the risk of software failure in operation.  

Software testing is a set of activities to discover defects and evaluate the quality of software artifacts. These artifacts, when being tested, are known as test objects. A common misconception about testing is that it only consists of executing tests (i.e., running the software and checking the test results). However, software testing also includes other activities and must be aligned with the software development lifecycle (see chapter 2).  

Another common misconception about testing is that testing focuses entirely on verifying the test object. Whilst testing involves verification, i.e., checking whether the system meets specified requirements, it also involves validation, which means checking whether the system meets users’ and other stakeholders’ needs in its operational environment.  

Testing may be dynamic or static. Dynamic testing involves the execution of software, while static testing does not. Static testing includes reviews (see chapter 3) and static analysis. Dynamic testing uses different types of test techniques and test approaches to derive test cases (see chapter 4).  

Testing is not only a technical activity. It also needs to be properly planned, managed, estimated,monitored and controlled (see chapter 5).  

Testers use tools (see chapter 6), but it is important to remember that testing is largely an intellectualactivity, requiring the testers to have specialized knowledge, use analytical skills and apply criticalthinking and systems thinking (Myers 2011, Roman 2018).  

The ISO/IEC/IEEE 29119-1 standard provides further information about software testing concepts.  

### 1.1.1. Test Objectives

The typical test objectives are:

* Evaluating work products such as requirements, user stories, designs, and code
* Causing failures and finding defects
* Ensuring required coverage of a test object
* Reducing the level of risk of inadequate software quality
* Verifying whether specified requirements have been fulfilled
* Verifying that a test object complies with contractual, legal, and regulatory requirements
* Providing information to stakeholders to allow them to make informed decisions
* Building confidence in the quality of the test object
* Validating whether the test object is complete and works as expected by the stakeholders

Objectives of testing can vary, depending upon the context, which includes the work product being tested, the test level, risks, the software development lifecycle (SDLC) being followed, and factors related to the business context, e.g., corporate structure, competitive considerations, or time to market.  

### 1.1.2.Testing and Debugging

Testing and debugging are separate activities. Testing can trigger failures that are caused by defects in the software (dynamic testing) or can directly find defects in the test object (static testing).

When dynamic testing (see chapter 4) triggers a failure, debugging is concerned with finding causes of this failure (defects), analyzing these causes, and eliminating them. The typical debugging process in this case involves:

* Reproduction of a failure
* Diagnosis (finding the root cause)
* Fixing the cause

Subsequent confirmation testing checks whether the fixes resolved the problem. Preferably, confirmation testing is done by the same person who performed the initial test. Subsequent regression testing can also be performed, to check whether the fixes are causing failures in other parts of the test object (see section 2.2.3 for more information on confirmation testing and regression testing).

When static testing identifies a defect, debugging is concerned with removing it. There is no need for reproduction or diagnosis, since static testing directly finds defects, and cannot cause  failures (see chapter 3).

## 1.2. Why is Testing Necessary?

Testing, as a form of quality control, helps in achieving the agreed upon goals within the set scope, time, quality, and budget constraints. Testing’s contribution to success should not be restricted to the test team activities. Any stakeholder can use their testing skills to bring the project closer to success. Testing components, systems, and associated documentation helps to identify defects in software.  

### 1.2.1. Testing's Contributions to Success

Testing provides a cost-effective means of detecting defects. These defects can then be removed (by debugging – a non-testing activity), so testing indirectly contributes to higher quality test objects.  

Testing provides a means of directly evaluating the quality of a test object at various stages in the SDLC. These measures are used as part of a larger project management activity, contributing to decisions to move to the next stage of the SDLC, such as the release decision.  

Testing provides users with indirect representation on the development project. Testers ensure that their understanding of users’ needs are considered throughout the development lifecycle. The alternative is to involve a representative set of users as part of the development project, which is not usually possible due to the high costs and lack of availability of suitable users.  

Testing may also be required to meet contractual or legal requirements, or to comply with regulatory standards.  

### 1.2.2. Testing and Quality Assurance (QA)

While people often use the terms "testing" and "quality assurance" (QA) interchangeably, testing and QA are not the same. Testing is a form of quality control (QC). QA is typically focused on establishing, introducing, monitoring, improving, and adhering to the quality-related processes. When proper processes are carried out correctly, this contributes to defect prevention, and improves confidence that appropriate levels of quality in the work products will be achieved. QA, when applied to software development and software maintenance, should also be applied to software testing, which is part of each of these activities. In addition, the use of root cause analysis to detect the causes of defects, and the application of the findings of retrospective meetings to improve processes, are also important for effective QA.

A larger concept, quality management (QM), ties together QA and QC. QM includes all activities that direct and control an organization with regard to quality. QM includes both QA and testing.

### 1.2.3. Root Causes, Errors, Defects, and Failures

Human beings make errors (mistakes), which produce defects (faults, bugs), which in turn may result in failures. Humans make mistakes for various reasons, such as time pressure, complexity of code, infrastructure or interactions, or simply because they are tired or lack adequate training.

The defects can be in documents, such as a requirements specification or a test script, in source code, or in a supporting artifact, such as a build file. Defects in artifacts produced earlier in the lifecycle, such as the requirements, if undetected, often lead to defective artifacts later in the lifecycle, such as the code. If a defect in code is executed, the system may fail to do what it should do (or do something it shouldn't), causing a failure. Some defects will always result in a failure if executed, while others will only result in a failure in specific circumstances, and some may never result in a failure.

Errors and defects are not the only cause of failures. Failures can also be caused by environmental conditions, such as when radiation or electromagnetic field cause defects in firmware.

A root cause is a fundamental reason for the occurrence of a problem. Root cause may be a situation or error that leads to a defect. Root causes are identified through root cause analysis, which is typically performed when a failure occurs, and it is believed that further similar failures can be prevented or their frequency reduced by addressing the root cause, such as by removing it.


## 1.3. Testing Principles

A number of testing principles offering general guidelines common to all testing have been suggested over the past 60 years. This syllabus describes seven such principles.

**1. Testing shows the presence, not the absence of defects**. Testing can show that defects are present in the test object but cannot prove that there are no defects (Buxton 1970). Testing reduces the probability of undiscovered defects remaining in the test object, but, even if no defects are found, testing cannot prove test object correctness.

**2. Exhaustive testing is impossible**. Testing everything is not feasible except in trivial cases (Manna 1978). Rather than attempting to test exhaustively, test techniques (see chapter 4), test case prioritization (see section 5.1.5), and risk-based testing (see section 5.2), should be used to focus test efforts.

**3. Early testing saves time and money**. Defects that are removed early in the process will not cause subsequent defects in derived work products. The total cost of quality will be reduced since fewer failures will occur later in the lifecycle (Boehm 1981). To find defects early, both static testing (see chapter 3) and dynamic test activities (see chapter 4) should be started as early as possible.

**4. Defects cluster together**. A small number of system components usually contain most of the defects discovered or are responsible for most of the operational failures (Enders 1975). This phenomenon is an illustration of the Pareto principle. Predicted defect clusters, and actual defect clusters observed during testing or in operation, are an important input for risk-based testing (see section 5.2).

**5. Tests wear out**. If the same tests are repeated many times, they stop being effective in detecting new defects (Beizer 1990). To overcome this, existing tests and test data may need changing, and new tests may need to be written. However, in some cases, repeating the same tests can have the beneficial outcome, e.g., in automated regression testing (see section 2.2.3).

**6. Testing is context dependent**. There is no single universally applicable approach to testing. Testing is done differently in different contexts (Kaner 2011).

**7. Absence-of-errors fallacy**. It is a fallacy (i.e., a mistaken belief) to expect that software verification will ensure the success of a system. Thoroughly testing all the specified requirements and fixing all the defects found could still produce a system that does not fulfill the users' needs and expectations, that does not help in achieving the customer's business goals and that is inferior compared to other competing systems. In addition to verification, validation should also be carried out (Boehm 1981).

## 1.4. Test Activities, Test Work Products and Test Roles

Testing is context dependent, but, at a high level, there are common sets of test activities without which testing is less likely to achieve its objectives. These sets of test activities form a test process. The test process can be tailored for a given situation based on various factors. Which test activities are included in this test process, how they are implemented, and when they occur are normally decided as part of the test planning for the specific situation (see chapter 5).

The following sections describe general aspects of this test process in terms of test activities and tasks, the impact of context, test work products, traceability between the test basis and test work products, and testing roles.

The ISO/IEC/IEEE 29119-2 standard has further information about test processes.

### 1.4.1. Test Activities and Tasks

A test process usually consists of the main groups of activities described below. Although many of these activities may appear to follow a logical sequence, they are often implemented iteratively or in parallel. Tailoring of these test activities within the context of the system and the project is usually required.

**Test planning** includes defining the test objectives and the test approach for meeting them within the constraints imposed by the context. Test planning is further explained in section 5.1.

**Test monitoring and control.** Test monitoring involves the on-going checking of all activities and the comparison of actual progress against the test plan. Test control involves taking the actions necessary to meet the objectives of the test plan. Test monitoring and control are further explained in section 5.3.

**Test analysis** includes analyzing the test basis to identify testable features and to define and prioritize associated test conditions, together with the related risks and risk levels (see section 5.2). Test basis and test objects are also evaluated to identify defects they may contain and to assess their testability. Test analysis is often supported by the use of test techniques (see chapter 4). Test analysis answers the question "what to test?" in terms of measurable coverage criteria.

**Test design** includes elaborating the test conditions into test cases and other testware (e.g., test charters). This activity often involves the identification of coverage items, which serve as a guide to specify test case inputs. Test techniques (see chapter 4) can be used to support this activity. Test design also includes test data identification, designing the test environment and identifying any other required infrastructure and tools. Test design answers the question "how to test?".

**Test implementation** includes creating or acquiring the testware necessary for test execution (e.g., test data). Test cases are organized into test procedures. Automated test scripts are created. Test procedures are prioritized and arranged within a test execution schedule for efficient test execution (see section 5.1.5). Test environment is built and verified to be set up correctly.

**Test execution** includes running the test procedures in accordance with the test execution schedule. Test execution may be manual or automatic. Test execution can take the form of continuous testing or pair testing sessions. Actual test results are compared with expected results. Anomalies are analyzed to identify their likely causes. Test execution outcome is logged. Defects are reported based on the failures observed (see section 5.5).

**Test completion** activities occur at project milestones (e.g., release, end of iteration, test level completion). Change requests or product backlog items for any unresolved defects are created. Any testware that may be useful in the future is identified and archived or handed over to the appropriate teams. The test environment is shut down to an agreed state. The completed test activities are analyzed to identify lessons learned and identify improvements for future iterations, releases, or projects (see section 2.1.6). A test completion report is created and communicated to stakeholders.

### 1.4.2. Test Process in Context

Testing is not performed in isolation. Testing is subservient to the development processes carried out within a specific organization. Testing is also sponsored by stakeholders and its final goal is to help fulfill the stakeholders' business needs. Therefore, the way the testing is carried out will depend on a number of contextual factors including:

* Stakeholders (needs, expectations, requirements, willingness to cooperate, etc.)
* Team members (skills, knowledge, level of experience, availability, training needs, etc.)
* Business domain (type of software, identified risks, market needs, specific legal regulations, etc.)
* Technical factors (product architecture, technology used, etc.)
* Project constraints (scope, time, budget, resources, etc.)
* Organizational factors (organizational structure, existing policies, practices used, etc.)
* SDLC (engineering techniques, development methods, etc.)
* Tools (availability, difficulty of use, etc.)

These factors will have an impact on many test-related issues, including: test strategy, test techniques used, degree of test automation, required level of test coverage in relation to requirements and identified risks, level of detail of test documentation, reporting etc.

### 1.4.3. Test Work Products

Test work products are created as outputs from the test activities described in section 1.4.1. There is a significant variation in the work products and their naming across organizations, regarding the way they are organized and managed. The following list of work products is by no means exhaustive.

**Test planning work products** include: test strategy (usually in larger projects), test plan, risk register, and exit criteria (see section 5.1). Risk register and exit criteria are often a part of the test plan.

**Test monitoring and control work products** include: test progress reports (see section 5.3.2), documentation of control directives (see section 5.3) and risk information (see section 5.2).

**Test analysis work products** include: (prioritized) test conditions, acceptance criteria (see section 4.5.2), and defect reports regarding defects in the test basis (if not fixed directly).

**Test design work products** include: test cases, coverage items, test data requirements and test environment design.

**Test implementation work products** include: test procedures, automated test scripts, test suites, test data, test execution schedule, and test environment elements. Examples of test environment elements include: stubs, drivers, simulators, and service virtualizations.

**Test execution work products** include: test logs, documentation of the status of individual test cases, defect reports (see section 5.5.1), and documentation about which test objects, test tools, and testware were involved in the testing.

**Test completion work products** include: test completion report (see section 5.3.2), action items for improvement of subsequent projects or iterations, and change requests (e.g., as product backlog items).

### 1.4.4. Traceability between the Test Basis and Test Work Products

In order to implement effective test monitoring and control, it is important to establish and maintain traceability throughout the test process between the test basis elements, test work products associated with these elements (e.g., test conditions, risks, test cases), test results, and detected defects.

Accurate traceability supports test coverage evaluation, so it is very useful if the test basis has measurable coverage criteria defined. The coverage criteria can function as key performance indicators to drive the activities that demonstrate the achievement of test objectives (see section 1.1.1). For example, by using the traceability from:

* Test cases to requirements, the requirements coverage by test cases can be verified
* Test case results to risks, the level of residual risk in a test object can be evaluated.

In addition to the evaluation of coverage, good traceability allows to determine the impact of changes, facilitates the auditing of testing, and supports the achievement of IT governance criteria. Good traceability also improves the understandability of test progress reports and test completion reports by including the status of test basis elements. This can also make the communication of technical aspects of testing to stakeholders easier, in terms that they can understand. Good traceability provides information used to assess product quality, process capability, and project progress against business goals.

### 1.4.5. Roles in Testing

In this syllabus, two principal roles in testing are covered: a test management role and a testing role. The activities and tasks assigned to these two roles depend on factors such as the project and product context, the skills of the people in the roles, and the organization.

The test management role takes overall responsibility for the test process, test team and leadership of the test activities. The test management tasks mainly concentrate on test planning, test monitoring and control and test completion activities. The testing role takes overall responsibility for the engineering (technical) aspect of testing. The testing tasks mainly concentrate on test analysis, test design, test implementation and test execution activities.

The way in which the test management role is carried out varies depending on the context. For example, in Agile software development, some of the test management tasks may be handled by the Agile team. Tasks that span multiple teams or the entire organization may be performed by test managers outside of the development team.

Different people may take over these roles at different times. For example, the test management role can be performed by a team leader, by a test manager, by a development manager, etc. It is also possible that one person can take both the testing and test management roles at the same time.


## 1.5. Essential Skills and Good Practices

Skill is the ability to do something well that comes from one's knowledge, practice and aptitude. Good testers should possess some essential skills to do their job efficiently and effectively. Good testers should also be the effective team players and perform testing on different levels of independence.

### 1.5.1 Generic Skills Required for Testing

While being generic, the following skills are particularly relevant for testers:

* Thoroughness, carefulness, curiosity, attention to details, being methodical (to identify different types of defects, especially the ones that are difficult to find)
* Good communication skills, active listening, being a team player (to interact effectively with all stakeholders, to convey information to others, to be understood, to report and discuss defects)
* Analytical thinking, critical thinking, creativity (to increase effectiveness of testing)
* Technical knowledge (to increase efficiency of testing, e.g., by using test tools)
* Knowledge of estimation techniques (to estimate the test effort more accurately)
* Domain knowledge (to be able to understand and to communicate with end users)

Testers are often the bearers of bad news. It is a common human trait to blame the bearer of bad news. This makes communication skills crucial for testers. Communicating testing results may be perceived as criticism of the product and of its author. Confirmation bias can make it difficult to accept information that disagrees with currently held beliefs. Some people may perceive testing as a destructive activity, even though it contributes greatly to project progress and product quality. To try to improve this view, information about defects and failures should be communicated in a constructive way.

Defining the right set of test objectives (see section 1.1.1) can have important psychological implications as most people tend to align their plans and behaviors with the set objectives.

### 1.5.2 Whole Team Approach

One of the important testing skills is being a team player, having the ability to work effectively in a team context and to contribute positively to the team goal. The whole team approach builds upon this skill.

The whole team approach involves everyone with the necessary knowledge and skills to ensure project success by making quality everyone's responsibility. The team members share the same workspace, as co-location facilitates communication and interaction. The whole team approach improves team dynamics, enhances communication and collaboration within the team, and creates synergy by allowing the various skill sets within the team to be leveraged for the benefit of the project.

Testers work closely with other team members to ensure that the desired quality levels are achieved. This includes collaborating with business representatives to help them create suitable acceptance tests and working with developers to agree on the testing strategy and decide on test automation approaches. Testers can thus transfer and extend testing knowledge to other team members and influence the development of the product.

Depending on the context, the whole team approach may be not sufficient requiring a higher level of testing independence (e.g., safety-critical systems).

### 1.5.3 Independence of Testing

A certain degree of independence makes the tester more effective at finding defects due to differences between the author's and the tester's cognitive biases. Independence is not, however, a replacement for familiarity, and developers can efficiently find many defects in their own code.

Work products can be tested by its author (no independence), by the author's peer from the same team (some independence), by the testers external to the author's team, but within the organization (high independence), or by the testers external to the organization (very high independence). For most projects, it is usually best to carry out testing with multiple levels of independence (e.g., developers performing component and component integration testing, test team performing system and system integration testing, and business representatives performing acceptance testing).

The main benefit of test independence is that independent testers are likely to recognize different kinds of failures compared to developers because of their different backgrounds, technical perspectives, and biases. Moreover, an independent tester can verify, challenge, or disprove assumptions made by stakeholders during specification and implementation of the system.

However, there are also some drawbacks. Independent testers may be isolated from the development team, which may lead to a lack of collaboration, communication problems, or an adversarial relationship with the development team. Developers may lose a sense of responsibility for quality. Independent testers may be seen as a bottleneck or be blamed for delays in release.

