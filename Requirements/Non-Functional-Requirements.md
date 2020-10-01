[[_TOC_]]

# Usability

## APIs

- Must Have

  - Must have documentation on what API does and how to use the functions it provides

## Standard User

- Must Have
  - Standard users must be able to access some level of documentation (e.g. explaining the different modes of the typing test)
  - There must be an easy method for standard users to change the mode of the typing test (e.g. from "standard" mode to "programmer" mode)
   - The typing test must have clear direction on how the standard user is to start the typing test whether it involves the use of a start button or instead starts automatically when the user starts typing
   - In order to understand progress, users must be able to differentiate between an indicator that they are on the letter and an indicator that they have made a mistake
   - There must be a conspicuous button on quitting the test if the standard user wishes to
   - Users must be able to understand the units of the metrics, and how they were calculated

- Should Have
  - If audio mode is selected, it must be loud enough to hear and clear enough to understand
  - The standard user should easily be able to see the play and pause button
  - To adjust the speed of dictation mode, there should be a method to easily slow it down such as by dragging a slider to the left and vice versa or pressing on a speed button
  -  Standard users should clearly be able to identify themselves on the leaderboard and gauge their standing relative to others, assuming it is available
  - Users should be able to see clearly what each number represents (e.g. there should be a title with the units)

- Could Have
  - Standard users would be able to view the different languages available for typing and easily select one via a drop down menu or by entering one in
  - There would be documentation on understanding their weak letter combinations
  - There would be documentation on typing foreign languages when the characters have accents or umlauts

## Administrative User

- Must Have
   - Administrator users must be provided with some level of documentation (e.g. creating and deleting standard users)
   - Administrator users must have a clear mechanism on selecting a standard user to view

- Should Have
  - Administrative users should easily be able to view and understand the information provided in the report for a standard user
  - Administrative users should be able to make the leaderboard visible by the check of a box or something as simple

- Could Have
  - Administrative users could bring up a group report, in which case, the typing test would format the information to be readable and understandable

## Super-Administrative Users

- Must Have
  - There must be documentation (e.g. on how to create each user of a different type and how to manage Schools and invite Schools)

# Reliability

## APIs

- Must Have

  - API should always be available
  - API should consistently give what asked for (e.g. ask for random words, receive random words)

## Standard User

- Must Have
  - The typing tool must be available 24/7
  - As long as the user is connected to WiFi, they must be able to use the typing tool
  - The typing tool must correctly generate text segments for the mode selected (e.g. if "programmer" mode is selected, they consistently receive code to type and in the language they choose)
  - If the system crashes on the user, the user's history must be saved
  - If the standard user makes a typing error, the display must accurately detect and depict the error
  - The standard's user metrics must be reported accurately, specifically, it will use the standard method of calculating metrics such as wpm and accuracy
  - The standard user's data must be securely protected

- Should Have
  - The various buttons for dictation mode (e.g. play and pause) should consistently perform the function assigned for the standard user

## Administrative User

- Must Have
  - If an administrative user creates a new standard user, it must be created
  - If an administrative user changes the name of the standard user, the name must be changed both for the administrative user and the standard user
  - If an administrative user deletes a standard user, the standard user must be deleted and must no longer be able to access their account
  - If an administrative user views a standard's user typing history, it must be the most recent history and accurately depict the standard user's history

- Should Have
  - If a new user group is created, it should be created
  - If the user group's name is edited, the name should be changed both the administrative user and the user group
  - If the user group is deleted, the user group should be deleted and it should not appear or be accessible for the administrative user and members of the user group
  - If a user is added to a group, the user should appear in the group
  - If a user is removed from a group, the user no should no longer appear in the group

- Could Have
  - If a group progress report is implemented, if a standard user is added to the group, the administrative user would be able to see their progress whilst in the group
  - If a group progress report is implemented, if a standard user is deleted from the group, the administrative user will not see their progress going forward

## Super-Administrative Users
- Must Have
  - When a super-administrative user creates a user, it should always be of the type specified
  - When a super-administrative user sends an invite to a School, it must be sent out

# Performance

## APIs

- Must Have

  - API must respond within a certain amount of time

## Standard User

- Must Have
  - When the standard user switches to a different mode, the typing tool must not make the user wait too long (might want to discuss exact time, maybe 5 seconds?)
  - As soon as the standard user starts the test, the timer being synchronously with the standard user
  - As the standard user types, the display must move synchronously with the standard user's keystrokes including if they hit the backspace button
  - If the standard user makes a typing error, the display must highlight the error almost immediately after it occurred

- Should Have
  - If dictation mode is selected, the audio should start playing as soon as the standard user starts
  - The buttons for dictation mode should take no more than an insignificant delay to respond to the standard user
  - If the standard user gets a score that improves their place on the leaderboard, the change will immediately be visible (maybe take no more than 5 seconds to appear)

- Could Have
  - If the standard user is in numbers mode, it should also detect the numbers synchronously

## Administrative User

- Must Have
  - It should take no more than an insignificant delay for a user to be created or deleted
  - Changing the name should take no more than an insignificant delay

- Should Have
  - It should take administrative users no more than an insignificant delay to create and delete user groups, to add and remove users from a user group, and to to change the name of the user group
  - The standard user's report should be up to date within 5 seconds of the standard user's progress and should always be available (?) to the administrative user

- Could Have
  - The group reports should be up to date within 5 seconds (?) of the standard user's progress and should always be available to the administrative user

## Super-Administrative User
- Must Have
  - Creating users must take no more than an insignificant delay to appear to the super-administrative user
  - Invites sent out by the super-administrative user must be sent out promptly

# Supportability

## APIs

- Must Have

   - Must be able to use the API on different versions of Python

## System/Domain

- Must Have

  - The code should be transferable between different versions of Python as long as it is greater than 3 and less than 3.7, due to Google Firebase only working with versions less than 3.7 and on any operating system
  - Functions and classes should be commented
    - Description of all parameters
    - Description of the purpose of the function/class
    - Description of any function return values (type/structure, units if applicable)
    - Links to documentation for external libraries
  - Package management
    - External libraries should be included in the pip dependency list