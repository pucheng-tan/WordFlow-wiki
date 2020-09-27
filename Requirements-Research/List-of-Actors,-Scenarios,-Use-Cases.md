This is a page for brainstorming:

● List of Actors, Scenarios, and Use Cases

○ Including proper supporting descriptions for each

from the Milestone 1 requirements document.

## Actors

### Standard User
- a user who is able to complete typing challenges
- may view their own typing progress through stored user metrics
- interact with user group(s)
- interacts with Firebase SDK (user will create a username and password for authentication)

### Administrative User
- a user who can manage other users and view their typing progress
- manage user groups
- may assign typing challenges to standard users or user groups
- also can do everything that a standard user is able to do

### Super Administrative User
- manage Administrators
   - create groups and assign an administrator to manage the group
   - add and remove administrators
- also can do everything that a standard user and administrator can do


### Firebase SDK
- interacts with our software through API calls
- manages user authentication, user permissions/user groups, store user data in cloud database, store user data

### Other APIs possibly!
//TODO: decide on the format for our tests (this will narrow down our choice in text fetching APIs)


## Scenarios
//TODO: Flesh out with actual steps, add more scenarios

### (Special Note: Every permission given to an Administrator will also be given to a Super-Administrator)

### Users can Login
- The intro screen for the game needs a Login button and a play as Guest button
- Clicking the login button takes you to another screen where you can enter your information
- Clicking the play as guest button takes you to the "Select Mode" screen
- Playing as a guest does not require an Internet connection and some modes may not be available

### Users can selects the Mode
- A screen where the user can select one of the three buttons for the different modes, Standard, Programmer, and Dictation mode
- Clicking any mode starts a typing test

### Change Programing Language
- After selecting Programing mode, the User can select between different programming languages

### User can choose difficulty
- After selecting the mode, the User can then choose the difficulty or for Dictation mode, change the speed

### After the User completes a typing test
- After Completing a typing test, an information screen is displayed with all the relevant information, wpm speed, accuracy, etc
- Buttons to try again, quit and main menu are also displayed
- Try Again button restarts the test and saves the User data if the user is logged in
- Quit button closes the application
- Main Menu button takes the User to the Main Menu Screen where they can select a new mode
### User selects a typing test without an internet connection available
// We probably need internet connection to verify the login information
### User selects a typing test requiring data from an unavailable API
- If the API is unavailable, A Popups window informs the User that the mode is unavailable
- It can then take then back to the main menu
### User loses connection to API in the middle of a typing test

### User views their typing test results
- If User is logged in, there could also be a button in the main Menu for there "Profile", showing there history, past results and other statistics
### User views their typing analytics

### User shares their typing test results

### User runs out of time for a timed test
- The test ends and there stats are displayed on a new screen with options to Try Again, Quit, and Main Menu
### API takes longer than 10 seconds (??) to respond to request for data
### User selects character combinations to focus on (??)
### User views the leaderboard
- A Leaderboard Button should be available on the main menu for the User
### User decides to quit in the middle of the typing test
- Stop Test button on screen while the test is active
- Clicking the button takes the User back to the main menu or exits the application
### User wants to pause the typing test and resume, restart or quit later
- Pause Restart and Quit buttons all available on screen as the test is active
### Turn off the background music (??)

### Administrator creates a group
- initialize a group with a name and extra parameters TBD
- Each group has a unique identifier (maybe?)
### Administrator deletes a group
- Administrator specifies name of group to be deleted
### Administrator adds a standard user to a group
- admin will specify the name of group and the standard user's identifier
### Administrator views a standard user's typing history
### Administrator views a report of a group's typing history
### Administrator assigns typing challenges and tasks to a group.


### Super-Administrator assigns a user to be an Administrator
- One standard user will me moved to the group of administrators
### Super-Administrator assigns a group to an Administrator
### Super-Administrator deletes an Administrator
- This will remove the administrator's special permissions, essentially moving them to a standard user

## Use Cases

### Use Case
- User logs in
### Primary Actor(s)
- Every type of user (Standard, Admin, Super-Admin)
- Firebase (authentication)
### Preconditions
- User has a user account
### Basic Flow
1. user starts software and arrives at login screen
2. user click on username input box
3. user enters in username
4. user clicks on password box
5. user enters in password
6. user presses enter
7. firebase authentication responds
### Alternative Flow
6. a) User entered in wrong username
   - a1) User is notified to reenter
   - a2) User is given option to pick new username
   - a3) back to step 6.

6. b) user entered in wrong password
   - b1) user is notified to reenter password
   - b2) user is given option to reset password
   - b3) back to step 6.

6. c) user does not have internet connection
   - c1) user given notice to connect to internet
7. a) firebase doesnt respond in time

### Use Case
- user starts a typing test
### Primary Actor(s)
### Preconditions
### Basic Flow
### Alternative Flow






