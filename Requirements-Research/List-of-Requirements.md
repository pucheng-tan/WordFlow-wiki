This is a page for brainstorming:

● List of Requirements

○ Using FURPS to identify both functional and non-functional requirements

○ Organized by scope - Must Have, Should Have, Could Have

from the Milestone 1 requirements document.

# Definitions
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

## Typing Definitions
### Words Per Minute (wpm)
- The average number of words per minute that a user is able to type.
- Given s = total time of typing challenge (seconds) and c = total number of correct characters typed (including spaces and punctuation):
   - wpm = (c / 5) / (s / 60)

### Accuracy
- The ratio of correct characters typed vs the total number of characters in the challenge:
- Given t = total characters in challenge, and c = total number of correct characters typed
   - accuracy = c / t

# Requirements
## Functional Requirements
//user tasks that the system needs to support

User shall be able to:
- M choose between a "programmer" mode to type code, "standard" to type words in English from written text, or "dictation" to type English words given in audio format
- (C) Numbers mode to work on numpad
- M choose different programming languages in the programmer mode: Python, Java, PHP, HTML, C
- (S1) if dictation mode is selected, play the typing challenge through their device's speakers
   - dictation mode cannot include special characters or punctuation
   - (S) speed up or slow down the speed of dictation mode to adjust the difficulty 
- replay a dictation typing challenge's audio content
   - (TBD) the replay will begin from the first word that is not completely typed (excluding spaces)
- (M) see how much of the given typing challenge they have typed highlighted
- (M) see any errors in their typing highlighted on the typing challenge
- (M) see how much time has elapsed since they have started the typing challenge ("stopwatch")
- see their a: total time, b: average wpm, c: accuracy, (S: admin can toggle leaderboard) d: place on the leaderboard (if applicable) upon completing the typing challenge
- (C) copy an image with the above information for sharing purposes upon completing a challenge
- (S) view a leaderboard of best (by wpm) typing challenges completed in their user group. The leaderboard will show a name, speed, time, and the type of challenge completed (max number of entries?)
- (C) view an analysis of which 2-letter character combinations they are weakest at (??)
- (S) complete basic typing challenges without an internet connection available
- (M) quit the typing test (e.g. they want to start a new one, or don't want to do it anymore)
- (C) select the language that they are typing in

Administrator users shall be able to:
- (M) create a new standard user
- (M) edit the name of a standard user
- (M) delete the standard user
- (S) create a new user group
- (S) edit the name of a user group
- (S) delete the user group
- (S) assign a standard user to a user group
- (S) remove a standard user from a user group
- (M) view a standard user's typing history (date, time elapsed, type of challenge, wpm, accuracy)
- (S) view a report of a standard user's typing history (showing change of wpm and accuracy over time)
- (C) view a report of a user group's typing history
   - view a comparison of all users' average accuracy and wpm over a specified period of time
   - view a comparison of all users' rate of change of accuracy and wpm over a specified period of time (ex: user x has improved accuracy by 5% from September 1 to September 24)
- (S/C) assign typing challenges to standard users or user group
   - determine the type of typing challenge
   - optionally set a date and time that the challenge must be completed by

## Non-functional Requirements (URPS)
//properties of the system or domain
### Python
- what version guys. Anything else? (I think Python 3, so maybe version 3? -Sarah; I've got 3.8.5 - Tara)

### APIs

### Usability
Must Haves

- Standard User
  - Standard users will be able to access some level of documentation on the different modes of the typing test

  - There will be an easy method to change the mode of the typing test (e.g. from regular mode to programmer mode)

  - The typing test will have a clear direction on how to start the typing test whether it involved the use of a start button or instead starts automatically when the user starts typing

  - There will be a conspicuous button on quitting the test if the user wishes to

- Administrative User

  - Administrator users will be provided with some level of documentation to be able to understand how to create, edit, and delete users

  - Administrator users will have a clear mechanism on selecting a standard user to view

  - Administrative users will easily be able to view and understand the information provided in the report for a standard user

- Super-administrative User

Should Haves

Could Haves

### Reliability
Must Haves

- As long as the user is connected to WiFi, they will be able to use the typing tool.

- While the user is typing, the system will not crash on the user.

Should Haves

- If the user is not connected to WiFi, they will still be able to use the typing tool but with limitations as to what they can type.

### Performance

Must Haves

- Standard User

 - As the user types, the display will move synchronously with the user's keystrokes.

 - If the user makes a typing error, the display will accurately detect and depict the error.

### Supportability
Must Haves

- Functions and classes should be commented
   - description of all parameters
   - description of the purpose of the function/class
   - description of any function return values (type/structure, units if applicable)
   - links to documentation for external libraries
- Package management
   - external libraries should be included in the pip dependency list