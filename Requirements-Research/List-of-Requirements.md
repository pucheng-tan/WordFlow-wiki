This is a page for brainstorming:

● List of Requirements

○ Using FURPS to identify both functional and non-functional requirements

○ Organized by scope - Must Have, Should Have, Could Have

from the Milestone 1 requirements document.

## User Definitions
### Standard User
- a user who is able to complete typing challenges
- may view their own typing progress

### Administrative User
- a user who can manage other users and view their typing progress
- may manage user groups
- may assign typing challenges to standard users or user groups

### Super-administrative User
- a user who can manage administrative users
- may perform all of the tasks of an administrative user
- may assign standard users or user groups to one or more administrative users for them to manage


## Functional Requirements
//user tasks that the system needs to support

### Standard User
- Must Haves
   - Choose between a "programmer" mode to type code, "standard" to type words in English from written text, or "dictation" to type English words given in though audio
   - Choose different programming languages in the programmer mode: Python, Java, PHP, HTML, C
   - Progress displayed highlighted on the screen
   - Errors should be clearly visible(The word is highlighted Red instead of Green)
   - Time visible on the screen in the form of a stopwatch
   - Show information like a: total time, b: average wpm, c: accuracy, d: leaderboard(Can be toggled by Admin) upon completing the typing challenge
   - The leaderboard will show a name, speed, time, and the type of challenge completed (max number of entries?)
   - Ability to complete basic typing challenges without an internet connection available
   - Ability to quit the typing test (e.g. they want to start a new one, or don't want to do it anymore)


- Should Haves
   - Audio for dictation mode must be played through their device's speakers
      - Dictation mode doesn't work for programmer mode
      - Speed up or slow down the speed of dictation mode to adjust the difficulty 
      - Pause and Play for dictation mode


- Could Haves
   - Numbers mode using only the numpad
   - A way to copy user data for sharing 
   - View an analysis of which 2-letter character combinations they are weakest at(To help them improve)
   - Multiple languages support


### Administrator Users
- Must Haves
   - Create a new standard user
   - Edit the name of a standard user
   - Delete the standard user
   - View a standard user's typing history (date, time elapsed, type of challenge, wpm, accuracy)


- Should haves
   - Create a new user group
   - Edit the name of a user group
   - Delete the user group
   - Assign a standard user to a user group
   - Remove a standard user from a user group
   - View a report of a standard user's typing history (showing change of wpm and accuracy over time)
   - Assign typing challenges to standard users or user group
      - determine the type of typing challenge
      - optionally set a date and time that the challenge must be completed by

- Could Haves
   - View a report of a user group's typing history
      - View a comparison of all users' average accuracy and wpm over a specified period of time
      - View a comparison of all users' rate of change of accuracy and wpm over a specified period of time (ex: user x has improved accuracy by 5% from September 1 to September 24)

## Non-functional Requirements (URPS)
//properties of the system or domain
### Python
- what version guys. Anything else? (I think Python 3, so maybe version 3? -Sarah; I've got 3.8.5 - Tara)

### APIs

### Usability

Standard User

- Must Have
  - Standard users must be able to access some level of documentation explaining the different modes of the typing test
  - There must be an easy method for standard users to change the mode of the typing test (e.g. from "standard" mode to "programmer" mode)
   - The typing test must have clear direction on how the standard user is to start the typing test whether it involves the use of a start button or instead starts automatically when the user starts typing
   - There must be a conspicuous button on quitting the test if the standard user wishes to
 
- Should Have
  -  Standard users should clearly be able to identify themselves on the leaderboard and gauge their standing relative to others, assuming it is available

- Could Have
  - Standard users would be able to view the different languages available for typing and easily select one via a drop down menu or by entering one in
  - There would be documentation on typing foreign languages when the characters have accents or umlauts
  - If audio mode is selected, it must be loud enough to hear and clear enough to undestand

Administrative User

- Must Have
   - Administrator users must be provided with some level of documentation of the specifics on how to create, edit, and delete standard users
   - Administrator users must have a clear mechanism on selecting a standard user to view

- Should Have
  - Administrative users should easily be able to view and understand the information provided in the report for a standard user
  - Administrative users should be able to make the leaderboard visible by the check of a box or something as simple

- Could Have
  - Administrative users could bring up a group report, in which case, the typing test would make the information easy to view and understand

### Reliability

Standard User

- Must Have
  - The typing tool must be available 24/7
  - As long as the user is connected to WiFi, they must be able to use the typing tool
  - While the user is typing, the system must not crash on the user
  - If the system does crash on the user, the user's past metrics must be saved
  - The standard's user metrics must be reported accurately, specifically, it will use the standard method of calculating metrics such as wpm and accuracy
  - The user's data must be securely protected (looking at Google Firebase)
  - The typing tool must correctly generate text segments for the mode selected, so if "programmer" mode is selected, they consistently receive code to type 

- Should Have
   - If the user is not connected to WiFi, they should still be able to use the typing tool but with limitations as to what they can type

Administrative User

- Must Have
  - If an administrative user creates a new user, it must be created
  - If an administrative user changes the name of the user, the name must be changed both for the administrative user and the standard user
  - If an administrative user deletes a user, the user must be deleted and must no longer be able to access their account
  - If an administrative user views a standard's user typing history, it the most recent history and accurately depict the user's history

- Should Have
  - If a new user group is created, it should be created
  - If the user group's name is edited, the name should be changed both the administrative user and the standard user
  - If the user group is deleted, the user group should be deleted and it should not appear for either the administrative user or standard user
  - If the user is added to a group, the user should appear in the group
  - If a user is removed from a group, the user no should no longer appear in the group

- Could Have
  - If a group progress report is implemented, if a standard user is added to the group, the administrative user would be able to see their progress whilst in the group
  - If a group progress report is implemented, if a standard user is deleted from the group, the administrative user will not see their progress going forward

### Performance

Standard User

- Must Have
  - As soon as the standard user starts the test, the timer must take no more than a second to begin (not sure of exact time yet)
  - As the standard user types, the display must move synchronously with the standard user's keystrokes including if they hit the backspace button
  - If the standard user makes a typing error, the display mus accurately detect and depict the error and appear almost immediately after the error
  - When the standard user switches to a different mode, the typing tool must not make the user wait too long (might want to discuss exact time, maybe 5 seconds?)

- Should Have
  - If the standard user has no WiFi, the response times should continue to be the same but with a limited database of things to type
  - If the standard user gets a score that improves their place on the leaderboard, the change will immediately be visible (maybe take no more than 5 seconds to appear)

- Could Have
  If dictation mode is selected, the audio should start playing as soon as the player starts

### Supportability

- Must Have
- Functions and classes should be commented
   - description of all parameters
   - description of the purpose of the function/class
   - description of any function return values (type/structure, units if applicable)
   - links to documentation for external libraries
- Package management
   - external libraries should be included in the pip dependency list


## Typing Definitions
### Words Per Minute (wpm)
- The average number of words per minute that a user is able to type.
- Given s = total time of typing challenge (seconds) and c = total number of correct characters typed (including spaces and punctuation):
   - wpm = (c / 5) / (s / 60)

### Accuracy
- The ratio of correct characters typed vs the total number of characters in the challenge:
- Given t = total characters in challenge, and c = total number of correct characters typed
   - accuracy = c / t
