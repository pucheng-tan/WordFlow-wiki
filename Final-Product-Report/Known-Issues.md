[[_TOC_]]
# Are there things that didn't get done? Any features that are incomplete?
A list of incomplete tasks and their details can be found on the [development board](https://git.cs.usask.ca/CMPT370-01-2020/group2/-/boards) but are summarized here.

## Logging in and Creating Schools

Both have issues of poor error messages. For example, if a user enters in an incorrect school id or incorrect password, it will not tell the user that, it will just fail to open up into the welcome window or fail to create the school.

## School Management
School management was not implemented. In order to make a new school, the user must create one through the authentication screen.

## Classroom Management
Classroom management has only just started- classrooms are able to be created with a name, but adding users to classrooms, and assigning admins to them is not yet implemented. Likewise, users cannot properly be removed, and classrooms cannot be deleted.

## User Management
In the User Management window, there is an "Invite All" button. The functionality for this button has not been implemented. Instead, if the admin or super-admin wishes to send a new invitation email to multiple users, they must click "View User" for each of them and invite them from there.

Once a user has been selected and viewed, the buttons at the top of "Assign New Challenge", "Reports", and "Remove" are all features that did not get done, so clicking those buttons does not do anything.
The user's profile information is also incomplete as displaying the user's date created, last sign in, and classroom was not implemented. 

## Reports
No reporting functionality has been implemented yet. The first step, retrieving a user's challenge history, has been completed, but amalgamation, analysis, presentation, and access to other users' history has not been implemented yet.

## Leaderboard
No leaderboard has been created, nor has the option to display the leaderboard for admins.

## Assignments
Assignment functionality, where admins can assign challenges to classrooms or specific users, has not been implemented.

## My Profile

The user's ability to change their profile information is incomplete, as they cannot change their display name. They can only change their first name and last name.

## Mock Database
A mock database for testing purposes has been started, but is not yet usable. See branch #83.

## Full testing coverage
Testing currently does not cover private functions, user interface, or all of the backend functionality

# Anything that doesn't work as expected?

## Virtual keyboard
The virtual keyboard will only work sometimes on windows, usually never on MAC. We think this issue has something to do with the tkinter python GUI library that we are using, specifically, detecting key presses and key releases. Because this issue only happens on some PCs, its extremely hard for us to debug, and in order to fix this issue, we would probably have to choose an new GUI library. No current workaround.

## Storing Programming Challenges in the DB
When we store programming challenges, we have to hard incode the newlines and tabs in order for them to display on the GUI. However, when we store these challenges in the DB, when the challenge content is requested when someone is doing a challenge, it displays the \n's and \t's rather then the newlines and tabs.

### Workaround
Currently, we just hardcoded the challenge content, so we are not requesting tests from the database for programming challenges.

## Text-to-Speach Running Inside a Thread
When the text to speech library reads out text, it blocks. This means that we chose to run it inside a thread so it does not block our GUI and the rest of our system. However, when running the text to speech inside a thread on mac will crash the entire system.

### Workaround
Instead of running the text to speech library inside a thread, we now create a new process inside the thread, and the process runs the text to speech library with the word we want it to pronounce.

## Other workarounds
For unique identification of Schools, currently just their name is being used, instead of something more reliable like a domain name. Similarly, users don't have display names stored, they are primarily identified with their email addresses.