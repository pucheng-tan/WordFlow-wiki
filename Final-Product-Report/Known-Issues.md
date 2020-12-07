[[_TOC_]]
# Are there things that didn't get done? Any features that are incomplete?
A list of incomplete tasks and their details can be found on the [development board](https://git.cs.usask.ca/CMPT370-01-2020/group2/-/boards) but are summarized here.

## Classroom Management
Classroom management has only just started- classrooms are able to be created with a name, but adding users to classrooms, and assigning admins to them is not yet implemented. Likewise, users cannot properly be removed, and classrooms cannot be deleted.

## Reports
No reporting functionality has been implemented yet. The first step, retrieving a user's challenge history, has been completed, but amalgamation, analysis, presentation, and access to other users' history has not been implemented yet.

## Leaderboard
No leaderboard has been created, nor has the option to display the leaderboard for admins.

## Assignments
Assignment functionality, where admins can assign challenges to classrooms or specific users, has not been implemented.

## Mock Database
A mock database for testing purposes has been started, but is not yet usable. See branch #83.

## Full testing coverage
Testing currently does not cover private functions, user interface, or all of the backend functionality

# Anything that doesn't work as expected?
## Virtual keyboard ????

# Any workarounds you have?
For unique identification of Schools, currently just their name is being used, instead of something more reliable like a domain name. Similarly, users don't have first/last names or display names stored, they are primarily identified with their email addresses.