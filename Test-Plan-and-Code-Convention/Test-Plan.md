[[_TOC_]]
# Test Plan

## Quality Assurance Strategy

To start the quality assurance process, each developer will write tests before or while they are developing the feature being tested. These tests may include integration tests, unit tests, acceptance tests, and end to end tests. Allowing these tests to fail in the beginning will guide the development process for these features. Ideally, as the feature becomes closer to being finished, the tests will begin to pass, and once all the tests pass, the feature is finished.

## Test Strategy

For testing individual modules we aim to use unit tests. These tests should verify that the modules are behaving correctly when not being influenced by other modules. Integration testing will be used to check the behavior of modules interacting with other modules. These tests are important for our system since we chose layered architecture, so we can use integration testing to check the behavior of layers interacting with other layers. Acceptance tests will be what we aim to make our system pass. They will test that our system properly follows the functional requirements that we set out to make. 

We aim to create at least one test for each main method of a module. When these tests pass, each of the main features that the module encompasses should be in working order. This means that it may be time for a merge to master.

### Merge Request Procedure

Before merging to master, a pull request must be carried out to make sure that you are up to date with the main branch. After the pull has been carried out, run the tests again to make sure that nothing contained in the code has broken the features that are to be merged with master. At this point, a merge request can be created. When creating a merge request, make sure an explanation of what you're merging is provided. Tag another developer to look over your code in the merge request, ideally someone who can understand the feature you are working on.

### Code Readability

We have chosen a coding convention that gives our software great readability (refer to Coding Conventions). Whenever a developer is finished writing code, a lint will be run through the code to make sure it is readable and matches our coding convention standards. When going back into legacy code to look for bugs/make changes, readable code is a must.

### Paired Programming

Paired programming can be leveraged in order to write cleaner and more understandable code, with fewer bugs. Ideally, we will make use of paired programming when creating very important modules.

#### We aim to write code with the following **Techincal Quality Attributes**:

- Correctness:
    - Should reduce the bugs per line of code through testing and eventually have less than 1 bug per 1 lines of code.

- Reliability
    - Should reduce the bugs per hour/ per time of using
    - Ensure there is no warning or error pops up when the program is running.

- Capability
    - Ensure all must-have requirements are met and 85% of should-have requirements are met.

- Maintainability
    - Ensure all could-have features could be added easily and efficiently in the future. They should be added as add-on classes to the original architecture. The original program should not need to be changed heavily.
    - Ensure low-coupling and high-cohesion.

- Performance
    - Ensure the program does not waste memory. Memory blocks should be allocated whenever needed and freed whenever no longer needed.
    - Ensure all non-functional requirements are met.

#### We aim to create our system in a way that satisfies the following **User Quality Attributes**:

- Usability
    - Try to maximize user's satisfaction. After we finished the program, we can let several friends or classmates to test our program and give us rating and feedback. Then we can improve our program according to their feedbacks.

- insatiability
    - Ensure the program is easy to install and update on either windows or mac os flatform. The installation should be completed by a single installation program without typing anything in the terminal or running any other third-party supporting software.

- documentation
    - Ensure the documentation are sufficient, clear, and concise.

- availability
    - Ensure the program is available at any time. When the internet connection is lost, an off-line mode should work instead. As long as the user has an internet connection, the connection to the database should be good 95% of the time.

#### Automatic Tests
1. Test files should be named as "test_" + the name of the file being tested. All test functions should be named as "test_" + "short_description_of_test"
2. Test files should be in the same folder as the file being tested (for integration tests, this should be the file that the test is interfacing with). Make a new file if none exists, otherwise use an existing file. If the file becomes so long as to be unwieldly, create another file with a short description appended (ie "test_authentication" + "_super_admin.py")
3. To share common procedures, mock objects, etc, test files should be extended from the test_base_class file. If no common assets are required, this is not necessary. If it's likely that you will be creating common assets, add to the base class.
4. pytest marks should be created for tests calling the API with "@pytest.mark.api" such that they can be skipped
5. A mock of the api should be linked in the test_base_class such that it is available to all tests without recreating

#### When you think you are done
When you think it's time to merge your branch into master, follow the procedure:
1. Complete your acceptance test procedures and record your results (test ID, pass/fail, date, your name). Make sure they pass.
2. Run all tests that are in your branch. Make sure they pass. Commit your code if you have not done so.
   - git status, git add -A (for all, or add specific files), git commit -m "completed work on x feature, all tests passing", git push
3. Merge master into your branch. Run all tests, make sure they pass.
   - git checkout master, git pull, git checkout your_branch, git merge master, (fix any merge conflicts), git push
4. Submit a merge request for your branch
5. Send a @everyone message in discord, and find someone to complete your merge request.

#### When completing a merge request
Note: this is only regarding testing, should also look at other stuff for merge request.
1. If you are working on a different branch, commit your code first.
2. Checkout the branch (git checkout their_branch, git pull)
3. Run all of the tests on the branch.
4. If the tests pass, accept the merge request. If the tests do not pass: Notify the previous coder. Take a moment to look for obvious problems, or instructions missing to install packages. If you fix it, document problems like missing packages in readme file, and document your fix on the merge request.

#### Logging Test Results
We are using pytest to handle running tests, and it does not record passes. In order to log results, we will use:

https://pypi.org/project/pytest-json-report/

Running pytest to run our tests also generates a log (this is set in pytest.ini, and configured in conftest.py). A file called .report.json will be generated upon running pytest, which contains the test's logs. The log contains a success field that checks if the test was run at the root, if there were any warnings, and if everything passed.

## Test Outline
### Unit Testing

We will carry out unit testing to test each module, class, or component. Unit testing of a certain class is done by the developer while writing the class.

We will use two strategies in order to carry out unit testing:

1. Black Box Testing:

We will use black-box testing to test the data and the UI layer. Classes in the data layer contain many functions which are defined by the third-party database. We cannot see the code inside those functions so we’d better test the performance of them through black-box testing. It’s also hard to test modules in the UI layer by generating test cases directly from the code being tested, so we will make use of black-box testing for the UI layer as well.

We will have different strategies for different types of parameters:
  - Numeric parameters: zero, positive, negative, integer, floating-point
  - String parameters: non-empty strings, empty strings
  - List parameters: non-empty, empty, some entries are unqualified

2. White Box Testing:

We will use white-box testing to test the logic layer. The classes in the logic layer will be made up of lots of 'if' and 'while' statements. We do want to cover all the boundary situations of those 'if' and 'while' statements, so we choose white-box testing to test the logic layer.

In white-box testing, we need to force the execution of 
  - certain lines of code
  - certain paths through the code
  - certain blocks of the code

Due to the complexity of the program, it may be impossible to attempt to test all the lines/paths/blocks.
We plan to test paths which have higher priority and write a comment to list the tests that have passed, tested but not passed, or have not been tested yet.

For both black-box and white-box testing, to solve the problem of an infinite number of unit test cases, we reduce the number of testing of equivalent classes. If a class has been fully tested, then the test of a similar class could be set to have a lower priority.

### Integration Testing

We do integration testing between two or multiple components that interacts with each other. integration testing is done by the tester after all the single components which are included in the integration testing, have passed the corresponding unit testing.

We do integration testing in two levels. The first level would be testing between components within a layer. The second level would be testing between two adjacent layers. We begin the second level integration testing after the first level integration testings within the two layers have all passed. 

### End-to-End Testing

we do end-to-end testing to make sure everything works well together.
we only do end-to-end testing when we have a certain confidence in all unit testing and integration testing.

## Testing Plan

Here is a testing plan that will encompass our software's functional requirements. These are acceptance tests.

In order for us to consider our software as 'finished', each of these tests must pass.

#### Scenario 00: User creates an account

| ID: | AT 00.1 |
| ------: | ------ |
| **Use Case** | first super admin account is created |
| **Primary Actors** | super-admin user |
| **Preconditions** | firebase user with email "test@test.ca" and password "Pass123!" exists, the name "new school" is not taken for schools  |
| | Connected to the internet |
| **Procedure** |  |
| 1. | test@test.ca logs into authentication with password Pass123! |
| 2. | profile menu is selected from main menu, create school under the school bar is selected |
| 3. | the name "new school" is inputed and sent to firebase |
| **Expected Result** | |
| 1. | super admin is notified that the school was successfully created |


| ID: | AT 00.2 |
| ------: | ------ |
| **Use Case** | School is made with an already existing name |
| **Primary Actors** | Super-admin user |
| **Preconditions** | Firebase user with email "test@test.ca" and password "Pass123!" exists, the name "new school" is not taken for schools  |
| | Connected to the internet |
| **Procedure** |  |
| 1. | test@test.ca logs into authentication with password Pass123! |
| 2. | profile menu is selected from main menu, create school under the school bar is selected |
| 3. | the name "new school" is inputed and sent to firebase |
| **Expected Result** | |
| 1. | super admin is notified that they have successfully created a new school |

| ID: | AT 00.3 |
| ------: | ------ |
| **Use Case** | super admin is created for an existing school by an existing super admin for the school |
| **Primary Actors** | super-admin user |
| **Preconditions** | creator is an existing super admin for a school |
| | Connected to the internet |
| **Procedure** |  |
| 1. | existing super admin chooses create new user in User management menu |
| 2. | new super admin is selected, and the submit button is pressed |
| **Expected Result** | |
| 2. | the new super admin is notified that they have been given super admin permissions |
| 1. | new super admin user in firebase under the original super admin's school |


| ID: | AT 00.4 |
| ------: | ------ |
| **Use Case** | standard user creates an account for the first time without valid credentials |
| **Primary Actors** | standard user |
| **Preconditions** | test@test.ca is owned by an existing user |
| | user was sent an invite to test@test.ca by a school 'new school' |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, 'new school' as school, presses submit |
| **Expected Result** | |
| 1. | user is notified that email already exists |

#### Scenario 01: User logs in

| ID: | AT 01.1 |
| ------: | ------ |
| **Use Case** | user logs in to the system with correct credentials |
| **Primary Actors** | all users |
| **Preconditions** | test@test.ca and Pass123 already exist |
| | user is connected to the internet |
| | user was sent an invite to test@test.ca by a school 'new school' |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, enters 'new school' into school presses submit |
| **Expected Result** | |
| 1. | user with test@test.ca is connected and authenticated to firebase authentication |
| 2. | user is admitted to the main menu page |

| ID: | AT 01.2 |
| ------: | ------ |
| **Use Case** | user logs in without valid credentials |
| **Primary Actors** | standard user |
| **Preconditions** | test@test.ca and pass123 do not match |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| **Expected Result** | |
| 1. | user is notified that they entered invalid credentials |

| ID: | AT 01.3 |
| ------: | ------ |
| **Use Case** | user logs in not connected to the internet |
| **Primary Actors** | standard user |
| **Preconditions** | user is not connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| **Expected Result** | |
| 1. | user is warned that they are not connected to the internet |

#### Scenario 02: User takes a typing challenge

| ID: | AT 02.1 |
| ------: | ------ |
| **Use Case** | user finishes a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | logged in user finishes typing challenge |
| 2. | results are calculated and showed on users screen |
| 3. | results from the test are sent to firebase |
| **Expected Result** | |
| 1. | new test results added in firebase under user with the email test@test.ca |

| ID: | AT 02.2 |
| ------: | ------ |
| **Use Case** | user starts a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | user selects typing challenge menu and selects the type, presses start |
| 2. | a typing challenge is requested by user with the email test@test.ca |
| **Expected Result** | |
| 1. | typing challenge is displayed on the users GUI |

#### Scenario 03: user views their typing history

| ID: | AT 03.1 |
| ------: | ------ |
| **Use Case** | user views their typing history page |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | user selects typing history page |
| 2. | request is sent to firebase for user typing data |
| **Expected Result** | |
| 2. | data is displayed on the user's typing history page through tables and graphs |

#### Scenario 04: Admin manages a classroom

| ID: | AT 04.1 |
| ------: | ------ |
| **Use Case** | admin adds an existing user to their classroom |
| **Primary Actors** | admin |
| **Preconditions** | test@test.ca is an existing user in the admin's school |
| | admin is connected to the internet |
| **Procedure** |  |
| 1. | from the manage classrooms screen, admins clicks add new user, test@test.ca is sent |
| 2. | user with email test@test.ca is invited to classroom |
| **Expected Result** | |
| 1. | in firebase, test@test.ca will be placed under the classroom under the admin's school |
| 2. | user with email test@test.ca will be notified that they were added to a classroom |

| ID: | AT 04.2 |
| ------: | ------ |
| **Use Case** | admin adds a non existing user to their classroom |
| **Primary Actors** | admin |
| **Preconditions** | test@test.ca does not exist in the admin's school |
| | user is connected to the internet|
| **Procedure** |  |
| 1. |  from the manage classrooms screen, admins clicks add new user, test@test.ca is sent |
| **Expected Result** | |
| 2. | admin is notified that they entered an invalid user email |

| ID: | AT 04.3 |
| ------: | ------ |
| **Use Case** | admin creates a classroom |
| **Primary Actors** | admin |
| **Preconditions** | user is connected to the internet|
| | 'new classroom' is not a classroom |
| **Procedure** |  |
| 1. | admin selects manage classroom and types in 'new classroom' |
| 2. | presses submit |
| **Expected Result** | |
| 1. | new classroom is created in the admins school |
| 2. | admin is given prompt displaying "You have successfully created a new classroom" |

| ID: | AT 04.4 |
| ------: | ------ |
| **Use Case** | admin creates a classroom with a name that is already taken |
| **Primary Actors** | admin |
| **Preconditions** | user is connected to the internet |
| | 'new classroom' is already a classroom in the admin's school |
| **Procedure** |  |
| 1. | admin selects manage classroom and types in 'new classroom' |
| 2. | presses submit |
| **Expected Result** | |
| 1. | admin is sent a message that the already classroom exists |

| ID: | AT 04.5 |
| ------: | ------ |
| **Use Case** | admin deletes an existing classroom |
| **Primary Actors** | admin |
| **Preconditions** | 'new classroom' is a classroom that the admin manages |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | admin goes to the classroom management page and clicks on an existing classroom |
| 2. | clicks delete |
| **Expected Result** | |
| 1. | classroom is removed from firebase, students in it are not removed from school, but removed from classroom |
| 2. | admin gets a notification saying that the classroom has been deleted |


#### Scenario 05: Admin assigns typing challenge

| ID: | AT 05.1 |
| ------: | ------ |
| **Use Case** | admin assigns typing challenge to existing classroom |
| **Primary Actors** | admin |
| **Preconditions** | classroom 'new classroom' exists |
| | admin is connected to the internet |
| **Procedure** |  |
| 1. | admin goes to the classroom management page |
| 2. | admin clicks on 'new classroom' selects test, presses submit |
| **Expected Result** | |
| 1. | in firebase, a new test will be registered under each user of the classroom with no results |
| 2. | each of the users in the classroom will receive a new notification about the new typing challenge from their classroom |

//TODO

#### Scenario 06: Admin views a classroom report

| ID: | AT 06.1 |
| ------: | ------ |
| **Use Case** | admin views a classroom report from an existing classroom |
| **Primary Actors** | admin |
| **Preconditions** | classroom called 'new classroom exists, and the admin manages it|
| | admin is connected to the internet |
| **Procedure** |  |
| 1. | admin clicks on the classroom management page, clicks on the classroom called 'new classroom' in the classroom list |
| 2. | admin clicks view report |
| **Expected Result** | |
| 1. | admin is sent a graph of dates on x axis, average class wpm on y axis |

| ID: | AT 06.2 |
| ------: | ------ |
| **Use Case** | admin makes specific adjustments to classroom report |
| **Primary Actors** | admin |
| **Preconditions** | admin is connected to the internet |
| **Procedure** |  |
| 1. | from report page, admin selecets % accuracy instead of average wpm |
| 2. | next, admin changes the date range |
| **Expected Result** | |
| 1. | admin collects new data from local environmnet (it was loaded when the admin clicked view report) |
| 2. | the data is displayed on the admins screen |

#### Scenario 07: User takes an assigned typing challenge

| ID: | AT 07.1 |
| ------: | ------ |
| **Use Case** | user takes an assigned typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | User clicks on assigned challenge and selects a challenge to be taken |
| 2. | request is sent to firebase for challenge data to user with email test@test.ca |
| **Expected Result** | |
| 1. | challenge data appears on users screen, user can begin the challenge |


| ID: | AT 07.2 |
| ------: | ------ |
| **Use Case** | User finishes a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | user finishes an assigned typing challenge |
| **Expected Result** | |
| 1. | new typing challenge entry sent to firebase under user test@test.ca, under the classroom they are participating in |
| 2. | user is sent back to assigned typing challenges screen |

#### Scenario 08: Super admin can create and manage admins

| ID: | AT 08.1 |
| ------: | ------ |
| **Use Case** | super admin attemps to create an admin from a user that doesnt exist |
| **Primary Actors** | super admin |
| | standard user |
| **Preconditions** | user test@test.ca does not exist in the super admins school |
| | super admin is connected to the internet |
| **Procedure** |  |
| 1. | Super admin selects new admin on the manage users screen |
| 2. | super admin types in test@test.ca |
| **Expected Result** | |
| 1. | the admin is given prompt notifiying that the user does not exist in the school |

| ID: | AT 08.2 |
| ------: | ------ |
| **Use Case** | super admin creates a new admin from an existing user |
| **Primary Actors** | super admin |
| | standard user |
| **Preconditions** | user with test@test.ca exists |
| | super admin is connected to the internet |
| **Procedure** |  |
| 1. | super admin selects new admin on the manage users screen |
| 2. | super admin types in test@test.ca |
| 3. | super admin presses submit |
| **Expected Result** | |
| 1. | admin is notified the new admin was created |
| 2. | in firebase, a new entry is created under admins under the super admin's school |

| ID: | AT 08.3 |
| ------: | ------ |
| **Use Case** | super admin changes an admin to an admin |
| **Primary Actors** | super admin |
| | admin |
| **Preconditions** | admin with test@test.ca exists |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | super admin selects manage users from the dashboard |
| 2. | super admin selects the user test@test.ca from the list of admins |
| 3. | super admin changes level and presses submit |
| **Expected Result** | |
| 1. | in firebase, user test@test.ca is removed from the admin list under the super admin's school |
| 2. | the super admin is given a prompt that notifies about the successful change |

| ID: | AT 08.4 |
| ------: | ------ |
| **Use Case** | super admin removes a user from their school |
| **Primary Actors** | super admin |
| | standard user |
| **Preconditions** | user with email test@test.ca exists |
| | super admin is connected to the internet |
| **Procedure** |  |
| 1. | super admin selects manage users from the dashboard |
| 2. | super admin selects user search and types test@test.ca |
| 3. | super admin selects user and presses delete |
| **Expected Result** | |
| 1. | in firebase, user test@test.ca is removed from the user's school |
| 2. | the super admin is given a prompt that notifies about the successful deletion |
