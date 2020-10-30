# Milestone 3: Test Plan - Research and Rough Draft


## Quality Assurance Strategy



## Test Outline

### Unit Testing

We do unit testing to test each single class or component. Unit testing of a certain class are done by the developer while writing the class.

we use two strategies to do unit testing:

- black box testing:
We use black box testing to test data and UI layer. Classes in the data layer contain many functions which are defined by the third-party database. We cannot see what’s code inside those methods so we’d better test the performance of them by black box testing. It’s also hard to test classes in the UI layer by generating test cases directly from the code being tested, so we choose black testing for UI layer as well.

we have different strategies for different type of parameters:
  - Numeric parameters: zero, positive, negative, integer, floating point
  - String parameters: non-empty strings, empty strings
  - List parameters: non-empty, empty, some entries are unqualified

- white box testing
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

we do integration testing between components or layers which interacts with each other. integration testing are done by tester after all the single components have passed the corresponding unit testing

### End-to-End Testing

we do system test to make sure everything works well together.
we only do system test when we have certain confidence in all unit testing and integration testing.

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

### Formal Methods
Use mathematical models to verify the correctness of accuracy and wpm in challenge results.

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





