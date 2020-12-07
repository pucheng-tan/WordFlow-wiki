[[_TOC_]]

# Running Tests
Instructions for running tests can be found in the 
[README](https://git.cs.usask.ca/CMPT370-01-2020/group2/-/blob/master/README.md)

# Test Coverage
## Included Parts
Automatic tests are focussed on service/management classes that perform 'backend' logic and send/receive data to the API. Most but not all functions in these classes are tested. The ones that are not tested at all are either extremely similar to functions that were already tested or, like the classroom classes, were written later and tests were not prioritized.

The focus is on these classes for a couple of reasons:

1. Writing tests for logic-based classes is faster than writing a GUI for them and manually testing various scenarios.
2. Exceptions are hidden from the user (GUI) who does not need to see the inner workings of the software and should not ever see them. This makes debugging the backend using the user interface completely impractical.
3. These functions are more likely to be reused. This makes them both more integral to be tested, and increases the likelihood that a change for one scenario will break the code for another scenario. Automatic testing will catch such problems very efficiently.

## Excluded Parts
There are no tests for the user interface. Major reasons are as follows:
1. Automatic testing of user interfaces is very time-consuming and challenging to write.
2. In theory, all of the logic is being performed at another level and all the GUI is doing is outputting data. However, there is a certain amount of logic that is inherent to the GUI (such as page routing, and interpreting user input) and also a certain amount of logic that snuck in (such as validation, which could and should be moved into management classes).
3. The user interface is not easily testable as it is written. It is likely that a refactor would be necessary to make a structure that is more testable. A UI testing library would likely be required, but which one would depend on how the GUI is refactored- a switch to a browser-based GUI would probably use a JavaScript testing library like Jest or Selenium.

Outside of the user interface, there are many functions that are not tested in the backend. 
1. Some are tested indirectly. For example, the api_service has a couple of public functions and many private functions that support them. The private functions are not tested, but the public functions are tested in such a way that most of the logic paths in the private functions are covered.
2. Others are extemely similar to previously written (and tested) functions. For example, the "get_classrooms" function exists to return a list of classroom documents within a school. It has a limit of how many documents to return and a value of where to start in order to paginate results. Other functions following this same structure are not tested.
3. Extremely simple functions are not always tested. A function that posts a given piece of data to specified document path is not always tested as it is not significantly different than the api_service post method.
4. Prioritization. A greater focus was given to completing features rather than making them robust.

# External Libraries
## [pytest](https://pypi.org/project/pytest/) (6.1.2)
Automatic tests are run with the popular pytest library. 

## [pytest-json-report](https://pypi.org/project/pytest-json-report/) (1.2.4)
Pytest JSON Report is used to customize test output, creating automatic test logging and doing away with the need for tracking results with spreadsheets. Pytest has been modified in the pytest.ini file to force a report to be outputted every time pytest is run, and the report itself is modified in conftest.py

## [mock-firestore](https://pypi.org/project/mock-firestore/) (0.7.3)
Mock Firestore is not completely implemented and merged into the master branch, but a partial implementation is on branch #83. The purpose of this library is to mock the Firestore library. However, certain Firestore functions that are used in our implementation are not available in the mock. These functions would have to be added to the mock before adding it to the project. 
