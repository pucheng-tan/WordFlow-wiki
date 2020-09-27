This is a page for brainstorming:

● List of Actors, Scenarios, and Use Cases

○ Including proper supporting descriptions for each

from the Milestone 1 requirements document.

## Actors
- Standard User (different types of users exist, but I THINK they're the same actor? Find out for sure)
- Administrative User
- Super Administrative User
- APIs are actors (more specific! Nail down APIs!)

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
### Admins Can add different Users into Groups
### Thy can edit details of any group


### Administrator creates a group
- initialize a group with a name and extra parameters TBD
### Administrator deletes a group
### Administrator adds a standard user to a group
- admin will specify the name of group and the standard user's identifier
### Administrator views a standard user's typing history
### Administrator views a report of a group's typing history
### Administrator assigns typing challenges and tasks to a group.


###Super-Administrator assigns a user to be an Administrator
- One standard user will me moved to the group of administrators
###Super-Administrator assigns a group to an Administrator
###Super-Administrator deletes an Administrator
- This will remove the administrator's special permissions, essentially moving them to a standard user

## Use Cases
(must have features all need use cases, should have features maybe a couple of use cases)

