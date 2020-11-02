# Milestone 3: Test Plan - Research and Rough Draft


## Quality Assurance Strategy

To start the quality assurance process, each developer will write tests before or while they are developing the feature being tested. Allowing these tests to fail in the beginning will guide the development process for these features. Ideally, as the feature becomes closer to being finished, the tests will begin to pass, and once all the tests pass, the feature is finished.

We aim to create at least one test for each main feature of a module. When these tests pass, each of the main features that the module encompasses should be in working order. This means that it may be time for a merge to master.

### Merge Request Procedure

Before merging to master, a pull request must be carried out to make sure that you are up to date with the main branch. After the pull has been carried out, run the tests again to make sure that nothing contained in the code has broken the features that are to be merged with master. At this point, a merge request can be created. When creating a merge request, make sure an explanation of what you're merging is provided. Tag another developer to look over your code in the merge request, ideally someone who can understand the feature you are working on.

### Code Readability

We have chosen a coding convention that gives our software great readability (refer to Coding Conventions). Whenever a developer is finished writing code, a lint will be run through the code to make sure it is readable and matches our coding convention standards. When going back into legacy code to look for bugs/make changes, readable code is a must.

### Paired Programming

Paired programming can be leveraged in order to write cleaner and more understandable code, with fewer bugs. Ideally, we will make use of paired programming when creating very important modules.


## Test Outline

### Unit Testing

We do unit testing to test each single class or component. Unit testing of a certain class are done by the developer while writing the class.

we use two strategies to do unit testing:

1. Black Box Testing:

We use black box testing to test data and UI layer. Classes in the data layer contain many functions which are defined by the third-party database. We cannot see what’s code inside those methods so we’d better test the performance of them by black box testing. It’s also hard to test classes in the UI layer by generating test cases directly from the code being tested, so we choose black testing for UI layer as well.

we have different strategies for different type of parameters:
  - Numeric parameters: zero, positive, negative, integer, floating point
  - String parameters: non-empty strings, empty strings
  - List parameters: non-empty, empty, some entries are unqualified

2. white box testing:

We use white box testing to test logic layer. Logic layer contains most of the logic and arithmetic operations in our whole system, which are easy to be tested by generating test cases based on the code.

in white box testing, we need to force execution of 
  - certain lines of code
  - certain paths through the code
  - certain blocks of the code

Due to the complexity of the program, it may be impossible to attempt to test all the lines/paths/blocks.
We plan to test paths which have the higher priority and write a comment to list the tests that has passed, tested but not passed, or have not been tested yet.

For both black box and white box testing, to solve the problem of infinite number of unit test cases, we reduce the number of testing of equivalent classes. If a class has been fully tested, them the test of a similar class could be set as lower priority.

#### Handle an exception in python:

try:
       (try something that can give an assertion)

except (specific assertion)
       (what to do when you see the assertion)
except:
       (how to handle any other assertion)
else:
       print("Nothing went wrong.")
finally:
       (always runs even when assertion occurs)

#### Raise an exception in python:

raise Exception("raise an exception")

#### Assert statement

assert x == "something"

If the condition is false, assert an exception.


### Integration Testing

we do integration testing between two or multiple components which interacts with each other. integration testing are done by tester after all the single components which are included in the integration testing, have passed the corresponding unit testing.

We do integration testing in two levels. The first level would be testing between components within a layer. The second level would be testing between two adjacent layers. We begin the second level integration testing after the first level integration testings within the two layers have all passed. 

### End-to-End Testing

we do system test to make sure everything works well together.
we only do system test when we have certain confidence in all unit testing and integration testing.

### Testing Plan

Here is a testing plan that will encompass our software's functional requirements. These are acceptance tests.

In order for us to consider our software as 'finished', each of these tests must pass.

#### Scenario 00: User creates an account

| ID: | AT 00.1 |
| ------: | ------ |
| **Use Case** | First super admin account is created |
| **Primary Actors** | super-admin user |
| **Preconditions** | Firebase user with email "test@test.ca" and password "Pass123!" exists, the name "new school" is not taken for schools  |
| | Connected to the internet |
| **Procedure** |  |
| 1. | test@test.ca logs into authentication with password Pass123! |
| 2. | profile menu is selected from main menu, create school under the school bar is selected |
| 3. | the name "new school" is inputed and sent to firebase |
| **Expected Result** | |
| 1. | New school is created in firebase |


| ID: | AT 00.2 |
| ------: | ------ |
| **Use Case** | school is made with taken name |
| **Primary Actors** | super-admin user |
| **Preconditions** | Firebase user with email "test@test.ca" and password "Pass123!" exists, the name "new school" is not taken for schools  |
| | Connected to the internet |
| **Procedure** |  |
| 1. | test@test.ca logs into authentication with password Pass123! |
| 2. | profile menu is selected from main menu, create school under the school bar is selected |
| 3. | the name "new school" is inputed and sent to firebase |
| **Expected Result** | |
| 1. | New school is created in firebase |

| ID: | AT 00.3 |
| ------: | ------ |
| **Use Case** | Super admin is created for an existing school by an existing super admin for the school |
| **Primary Actors** | super-admin user |
| **Preconditions** | creator is an existing super admin for a school |
| | Connected to the internet |
| **Procedure** |  |
| 1. | existing super admin chooses create new user in User management menu |
| 2. | new super admin is selected, and the submit button is pressed |
| 3. | a new account is created with valid credentials, and with the school of the original super admin |
| **Expected Result** | |
| 1. | new super admin user in firebase |

| ID: | AT 00.4 |
| ------: | ------ |
| **Use Case** | standard user creates an account for the first time with no school |
| **Primary Actors** | standard user |
| **Preconditions** | test*test.ca and Pass123 do not exist for an existing user |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| 2. | user is admitted to the main menu page |
| **Expected Result** | |
| 1. | new standard user is saved in firebase, without any school |

| ID: | AT 00.5 |
| ------: | ------ |
| **Use Case** | standard user creates an account for the first time without valid credentials |
| **Primary Actors** | standard user |
| **Preconditions** | test*test.ca is owned by an existing user |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| 2. | user is notified that email already exists |
| **Expected Result** | |
| 1. | new user is not saved in firebase |

#### Scenario 01: User logs in

| ID: | AT 01.1 |
| ------: | ------ |
| **Use Case** | user logs in to the system with correct credentials |
| **Primary Actors** | all users |
| **Preconditions** | test*test.ca and Pass123 already exist |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| 2. | user is admitted to the main menu page |
| **Expected Result** | |
| 1. | user with test@test.ca is connected and authenticated to firebase authentication |

| ID: | AT 01.2 |
| ------: | ------ |
| **Use Case** | user logs in without valid credentials |
| **Primary Actors** | standard user |
| **Preconditions** | test*test.ca and pass123 do not match |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| 2. | user is notified that they entered invalid credentials |
| **Expected Result** | |
| 1. | no change in firebase |

| ID: | AT 01.3 |
| ------: | ------ |
| **Use Case** | user logs in not connected to the internet |
| **Primary Actors** | standard user |
| **Preconditions** | user is not connected to the internet |
| **Procedure** |  |
| 1. | new user gets to authentication page and enters test@test.ca and Pass123, presses submit |
| 2. | user is warned that they are not connected to the internet |
| **Expected Result** | |
| 1. | no change in firebase database |

#### Scenario 02: User takes a typing challenge

| ID: | AT 02.1 |
| ------: | ------ |
| **Use Case** | user finishes a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test*test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | logged in user finishes typing challenge |
| 2. | results are calculated and showed on users screen |
| 3. | results from the test are sent to firebase |
| **Expected Result** | |
| 1. | new test results added in firebase under user test@test.ca |

| ID: | AT 02.2 |
| ------: | ------ |
| **Use Case** | user starts a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | user selects typing challenge menu and selects the type, presses start |
| 2. | a typing challenge is requested by test@test.ca |
| **Expected Result** | |
| 1. | firebase sends a typing challenge to test@test.ca |

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
| 3. | data is displayed on typing history page through tables and graphs |
| **Expected Result** | |
| 1. | no change in firebase |

#### Scenario 04: Admin manages a classroom

| ID: | AT 04.1 |
| ------: | ------ |
| **Use Case** | admin adds an existing user to their classroom |
| **Primary Actors** | admin |
| **Preconditions** | test*test.ca is an existing user in the admin's school |
| | admin is connected to the internet |
| **Procedure** |  |
| 1. | from the manage classrooms screen, admins clicks add new user, test@test.ca is sent |
| 2. | user with email test@test.ca is invited to classroom |
| **Expected Result** | |
| 1. | in firebase, test@test.ca will be placed under the classroom under the admin's school |

| ID: | AT 04.2 |
| ------: | ------ |
| **Use Case** | admin adds a non existing user to their classroom |
| **Primary Actors** | admin |
| **Preconditions** | test*test.ca does not exist in the admin's school |
| | user is connected to the internet|
| **Procedure** |  |
| 1. |  from the manage classrooms screen, admins clicks add new user, test@test.ca is sent |
| 2. | admin is notified that they entered an invalid user email |
| **Expected Result** | |
| 1. | no change to firebase |

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
| 1. | nothing is changed in firebase, admin is sent a message that the classroom exists |

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
| 1. | no change in firebase |
| 2. | admin collects new data from local environmnet (it was loaded when the admin clicked view report) |
| 3. | the data is displayed on the admins screen |

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
| 3. | challenge data appears on users screen, user begins the challenge |
| **Expected Result** | |
| 1. | no change in firebase |

| ID: | AT 07.2 |
| ------: | ------ |
| **Use Case** | User finishes a typing challenge |
| **Primary Actors** | standard user |
| **Preconditions** | user logged in with test@test.ca |
| | user is connected to the internet |
| **Procedure** |  |
| 1. | user finishes an assigned typing challenge |
| 2. | user is sent back to assigned typing challenges screen |
| **Expected Result** | |
| 1. | new typing challenge entry sent to firebase under user test@test.ca, under the classroom they are participating in |

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
| 1. | no change in firebase |
| 2. | the admin is given prompt notifiying that the user does not exist in the school |

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

## Quality Assurance suggestions





### General Strategy
- use Unit tests for individual functions and modules to verify that they work correctly
- use Integration tests to verify that the interaction between components functions as expected
- use Acceptance tests to verify that a feature or task functions as expected
- all types of tests should look at normal conditions, exception/error conditions, and edge cases
- a test plan should be written before writing project code, outlining:
  - acceptance tests: at a high level, what should the user be able to accomplish with the feature, following which steps? Which steps can potentially lead to errors? Are there boundaries that have to be accounted for?
  - 
- test code may be written before code, during code, or after code, according to the developer's choice. However, tests must be completed and passing before code is merged into the master branch. It is recommended to 

### Formal Method
Due to the slow and complex progress of doing formal methods, we only use it in a small part of our program:

Use mathematical models to verify the correctness of accuracy and wpm in challenge results. We calculate the answer on paper and then compare it with the answer that the program shows.

### Inspection Method

We will regularly come back to the requirements and system architecture which we set up before and check if we are following them.

### Technical Quality Attributes

- Correctness
The program should avoid the happening of bugs
    - ensure the info displayed is correct (wpm, accuracy, ...)
    - ensure the info displayed is up-to-date (time elapsed, user's history, user management ...)

- Reliability
The program should reduce the bugs per hour/ per use
    - ensure there is no warning or error when the program is running
    - ensure all wrong characters in user input are highlighted and none of correct characters is highlighted
    - ensure the key in virtual keyboard is highlighted when being pressed and not highlighted when not being pressed

- Capability
    - ensure all must-have requirements are met and 85% of should-have requirements are met

- Maintainability
    - ensure all could-have features could be added easily and efficiently in the future. They should be added as add-on classes to the original program. The original program does not need to be changed heavily
    - ensure low-coupling and high-cohesion

- Performance
    - ensure the program does not waste memory. Memory blocks should be allocated whenever needed and freed whenever no longer needed.
    - ensure all non-functional requirements are met

### User Quality Attributes

- Usability
    - try to maximize user's satisfaction. After we finished the program, we can let several friends or classmates to test our program and give us rating and feedback. Then we can improve our program according to their feedbacks.

- insatiability
    - ensure the program is easy to install and update on either windows or mac os flatform. The installation should be completed by a single installation program without typing anything  in the terminal or any other third-party supporting software.

- documentation
    - ensure the documentation are sufficient, clear and concise

- availability
    - ensure the program is available at anytime. When the internet connection is lost, an off-line mode should work instead. As long as the user has internet connection, the connection to the database should be good 95% of the time.

### Procedure of generating test cases

1. identify the test cases
2. determine how to set up the test cases: hard-coding, pytest, mock test and so on
3. determine the expected result
4. write an in-line documentation for the test which need include
	- have test case ID in ascending order
	- test senario
	- test steps
	- test input
	- expected output
	- actual result
	- pass/fail	
5. code the test

### Test Plan Example
For feature "User logs in".

Before coding or test plan, an issue will have been created in GitLab, a developer or developers assigned to the issue, and a branch created from the issue. Hypothetically, this is issue # 18, and the branch name will be "18_user_logs_in"

#### Acceptance Tests
Before coding, acceptance tests should be created to outline the expected behaviour of the feature.

Including success/correct usage:

| ID: | AT 18.1 |
| ------: | ------ |
| **Use Case** | Standard User logs in (success) |
| **Primary Actors** | Standard User |
| **Preconditions** | Firebase user with email "test@test.ca" and password "Pass123!" exists |
| | The test user belongs to School "X School" as standard user, and to no other schools |
| **Procedure** |  |
| 1. | After launching software, enters valid email, password, and school combination (test@test.ca, Pass123!, X School) into the input fields |
| 2. | Clicks the submit button |
| **Expected Result** | |
| 1. | The user is directed to a dashboard screen, with the message "Welcome Test User" displayed |

Error Handling:

| ID: | AT 18.2 |
| ------: | ------ |
| **Use Case** | Standard User logs in (no API connection) |
| **Primary Actors** | Standard User |
| **Preconditions** | There is no connection to external authentication API (use mock) |
| **Procedure** |  |
| 1. | After launching software, enters valid email, password, and school combination (test@test.ca, Pass123!, X School) into the input fields |
| 2. | Clicks the submit button |
| **Expected Result** | |
| 1. | An error is displayed indicating "Connection error: please check your internet connection or try again later" |
| 2. | The same page is displayed, there is no redirection |

User error:

| ID: | AT 18.3 |
| ------: | ------ |
| **Use Case** | Standard User logs in (invalid login) |
| **Primary Actors** | Standard User |
| **Preconditions** | Firebase user with email "test@test.ca" and password "Pass123!" exists |
| | The test user belongs to School "X School" as standard user, and to no other schools |
| **Procedure** |  |
| 1. | After launching software, enters a valid email and password, but an invalid school combination (test@test.ca, Pass123!, Y School) into the input fields |
| **Expected Result** | |
| 1. | An error is displayed indicating "Invalid login credentials" |
| 2. | The user is not redirected |

Applicable Boundary conditions: (Note: could not think of boundary conditions for this use case, switched to creating account)

| ID: | AT 19.1 |
| ------: | ------ |
| **Use Case** | User creates account (boundary: minimum characters) |
| **Primary Actors** | Standard User |
| **Preconditions** | Firebase user with email "t@tt.ca" belonging to "M School" does not exist |
| | The test user has been invited to M School |
| **Procedure** |  |
| 1. | After launching software, clicks "create account" |
| 2. | Enters the email "t@tt.ca" into the email field and the password "Pass123!" into password and verify password fields |
| 3. | Enters "M School" into School field |
| 4. | Clicks submit button |
| **Expected Result** | |
| 1. | The user is directed to a dashboard screen, with the message "Welcome T TT" displayed |

#### Test Plan
The test plan can either be written in an external document, be created as python files and outlined with method stubs and comments, or may be completely implemented as failing test code before begin coding. Thought should be given to fixtures, mocks, or parametrize values that may be used. However, before merging, the code must be correctly implemented and pass.

```python
test_authentication_service.py

//UT 18.1: test that correct UID is returned when valid login credentials given
@pytest.mark.parametrize("email, password, school, uid", [valid, boundary]
def test_valid_login():
    assert(AuthService.login(email, password, school) == uid)

//UT 18.2: test that an error is returned when invalid login credentials given
@pytest.mark.xfail
@pytest.mark.parametrize("email, password, school, uid", [invalid, wrongschool]
def test_invalid_login():
    warnings.warn("not sure how to write this test yet")
    assert(1 == "not written yet") // what is the ideal way to mark tests as incomplete? xfail, warning, or simple failures may all work.
```

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

some rules:

merge a branch before all the unit and integration test within that branch passed





