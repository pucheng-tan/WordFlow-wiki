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

## Non-functional Requirements
//properties of the system or domain
### Python
- what version guys. Anything else? (I think Python 3, so maybe version 3? -Sarah; I've got 3.8.5 - Tara)

### APIs
//TODO

## Non-Functional Requirements (URPS)

### Usability

### Reliability
- shouldn't crash while the user is typing

### Performance
- should read keystrokes in at the same time user types them

### Supportability
- Functions and classes should be commented
   - description of all parameters
   - description of the purpose of the function/class
   - description of any function return values (type/structure, units if applicable)
   - links to documentation for external libraries
- Package management
   - external libraries should be included in the pip dependency list