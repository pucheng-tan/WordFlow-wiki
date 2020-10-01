## Non-functional Requirements (URPS)
//properties of the system or domain
### Python
- what version guys. Anything else? (I think Python 3, so maybe version 3? -Sarah; I now have version 3.6.8 - Tara)
-firebase requires python version <3.7

### APIs
- use the Google Firebase REST API for authentication and database interfacing

- Usability
  - DOCUMENTATION.
  - Users should easily be able to make a request with the API through the system
- Reliable
  - API should always be available
  - API should consistently give what asked for e.g. ask for random words, receive random words
- Performance
  - API should respond within a certain amount of time (one problem with Wordnik API is sometimes gives too many requests error)
-  Supportability
   - Should be easy to use on different versions of Python

### Usability

Standard User

- Must Have
  - Standard users must be able to access some level of documentation explaining the different modes of the typing test
  - There must be an easy method for standard users to change the mode of the typing test (e.g. from "standard" mode to "programmer" mode)
   - The typing test must have clear direction on how the standard user is to start the typing test whether it involves the use of a start button or instead starts automatically when the user starts typing
   - There must be a conspicuous button on quitting the test if the standard user wishes to
   - Users must be able to understand the units of the metrics, and (probably) how they were calculated
  -  Standard users should clearly be able to identify themselves on the leaderboard and gauge their standing relative to others, assuming it is available
  - Users should be able to see clearly what each number represents e.g. There should be a title with the units

- Should Have
  - If audio mode is selected, it must be loud enough to hear and clear enough to understand
  - The standard user should easily be able to see the play and pause button
  - To adjust the speed of dictation mode, there should be a method to easily slow it down such as by dragging a slider to the left and vice versa or pressing on a speed button


- Could Have
  - Standard users would be able to view the different languages available for typing and easily select one via a drop down menu or by entering one in
  - There would be documentation on typing foreign languages when the characters have accents or umlauts

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
  - If the standard user makes a typing error, the display must accurately detect and depict the error and appear almost immediately after the error
  - When the standard user switches to a different mode, the typing tool must not make the user wait too long (might want to discuss exact time, maybe 5 seconds?)

- Should Have
  - If the standard user has no WiFi, the response times should continue to be the same but with a limited database of things to type
  - If the standard user gets a score that improves their place on the leaderboard, the change will immediately be visible (maybe take no more than 5 seconds to appear)

- Could Have
  - If dictation mode is selected, the audio should start playing as soon as the player starts

Administrative User

- Must Have
  - It should take no more than an insignificant delay for a user to be created or deleted
  - Changing the name should take no more than an insignificant delay

- Should Have
  - It should take no more than an insignificant delay to create and delete user groups
  - It should take no more than an insignificant delay to add and remove users from a group
  - It should take no more than an insignificant delay to change the name of the group
  - The standard user's report should be up to date within 5 seconds of the standard user's progress and should always be available (?)

- Could Have
  - The group reports should be up to date within 5 seconds (?) of the standard user's progress and should always be available (?)

### Supportability

- Must Have
  - Anyone should be able to install the typing tool <-- what does this mean? Operating system? Technical skill level? (I was thinking like if anyone wanted to download the code off of GitHub, they'd be able to do so, do you think this is better: "- Anyone wishing to install and run the code for the typing tool must be able to do so)
  - Functions and classes should be commented
    - description of all parameters
    - description of the purpose of the function/class
    - description of any function return values (type/structure, units if applicable)
    - links to documentation for external libraries
  - Package management
    - external libraries should be included in the pip dependency list