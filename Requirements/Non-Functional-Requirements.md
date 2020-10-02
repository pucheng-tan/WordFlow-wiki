[[_TOC_]]

# Terminology
For the non-functional requirements, an insignificant delay is quantified as being less than or equal to 500 milliseconds.

# Usability

## APIs

- Must Have

  - Must have documentation on what the API does and how to use the functions it provides

## Standard User

- Must Have
  - Standard users must be able to access some level of documentation (e.g. explaining the different modes of the typing test)
  - There must be an easy method for standard users to change the mode of the typing test (e.g. from "standard" mode to "programmer" mode)
   - The typing test must have clear direction on how the standard user is to start the typing test whether it involves the use of a start button or instead starts automatically when the user starts typing
   - In order to understand progress, users must be able to differentiate between an indicator that they are on the letter and an indicator that they have made a mistake
   - There must be a conspicuous button on quitting the test if the standard user wishes to
   - Users must be able to understand the feedback (e.g. wpm, accuracy), and how they were calculated

- Should Have
  - If dictation mode is selected, it should be loud enough to hear and clear enough to understand
  - The standard user should easily be able to play and pause
  - To adjust the speed of dictation mode, there should be a method to easily slow it down such as by dragging a slider to the left and vice versa or pressing on a speed button
  -  Standard users should clearly be able to identify themselves on the leaderboard and gauge their standing relative to others, assuming it is available
  - Users should clearly be able to see what each number represents on the leaderboard (e.g. there should be a title with the units)

- Could Have
  - There would be documentation on understanding their weak letter combinations
  - Standard users would be able to view the different languages available for typing and easily select one via a drop down menu or by entering one in
  - There would be documentation on typing foreign languages when the characters have accents or umlauts

## Administrative User

- Must Have
   - Administrator users must be provided with some level of documentation on what and how they can work with Classrooms (e.g. creating and deleting Classrooms) as well as what typing challenges are and how to assign them

- Should Have
  - Administrative users should easily be able to view and understand the information provided in the report for a specific user in the Classroom and in the report for the Classroom itself
  - Administrative users should easily be able to change the visibility of the leaderboard for a Classroom

## Super-Administrative User

- Must Have
  - There must be documentation for the super-administrative user on the users (e.g. the different types of users and how to create them) and managing Schools (e.g. creating Schools and inviting users to Schools)

- Should Have
  - There should be documentation for the super-administrative user on assigning and unassigning Classrooms to administrative users and the effects of doing so

- Could Have
  - There would be documentation for the super-administrative user on removing users from Schools and the effects of doing so as well as creating custom typing challenge content

# Reliability

## APIs

- Must Have

  - The API must always be available
  - The API must consistently give what was asked for (e.g. ask for random words, receive random words)

## Standard User

- Must Have
  - The typing tool must be available 24/7
  - As long as the standard user is connected to WiFi, they must be able to use the typing tool
  - The typing tool must correctly generate text segments for the mode selected by the standard user (e.g. if "programmer" mode is selected, they consistently receive code to type and in the language they choose)
  - If the system crashes on the user, the standard user's history must be saved
  - If the standard user makes a typing error, the display must accurately detect and depict the error
  - The standard's user metrics must be reported accurately, specifically, it will use the standard method of calculating metrics such as wpm and accuracy
  - The standard user's data must be securely protected

- Should Have
  - The various buttons for dictation mode (e.g. play and pause) should consistently perform the function assigned for the standard user

## Administrative User

- Must Have
  - If a new Classroom is created, it must be created
  - If the Classroom is deleted, the Classroom must be deleted and it should not appear or be accessible for the administrative user and members of the deleted Classroom
  - If a user is added to a Classroom, the user should appear in the Classroom and vice versa
  - When the due date passes for the typing challenge, the administrative user should know that users assigned will no longer be able to get credit for it

- Should Have
  - If a Classroom report is implemented, if a standard user is added to the Classroom, the administrative user should be able to see their progress whilst in the Classroom and if a standard user is deleted from the Classroom, the administrative user should not see their progress going forward

## Super-Administrative User

- Must Have
  - When a super-administrative user creates a user, it should always be of the type specified
  - When a super-administrative user sends an invite to a School, it must be sent out

- Should Have
  - When the super-administrative user assigns and unassigns administrative users, the administrative user must be granted access or denied access to the specified Classroom

- Could Have
  - When a super-administrative user decides to remove users from a School, the user would be removed
  - When a super-administrative user creates custom content, it should show up in the typing challenges for the standard users

# Performance

## APIs

- Must Have

  - The API must respond within a certain amount of time

## Standard User

- Must Have
  - When the standard user switches to a different mode, the typing tool must take only an insignificant delay
  - As soon as the standard user starts the test, the timer starts synchronously with the standard user
  - As the standard user types, the display must move synchronously with the standard user's keystrokes including if they hit the backspace button
  - If the standard user makes a typing error, the display must highlight the error almost immediately after it occurred

- Should Have
  - If dictation mode is selected, the audio should start playing as soon as the standard user starts
  - The buttons for dictation mode should take no more than an insignificant delay to respond to the standard user
  - If the standard user gets a score that improves their place on the leaderboard, the change will take no more than an insignificant delay to be visible

- Could Have
  - If the standard user is in numbers mode, it should also detect the numbers synchronously

## Administrative User

- Must Have
  - It should take administrative users no more than an insignificant delay to create and delete Classrooms and to add and remove users from a Classroom

- Should Have
  - The Classroom's report should be up to date within 5 seconds of the standard user's progress and should always be available to the administrative user

## Super-Administrative User

- Must Have
  - Creating users must take no more than an insignificant delay to appear to the super-administrative user
  - Invites sent out by the super-administrative user must be sent out promptly

- Should Have
  - Assigning and unassigning administrative users to Classrooms should not take too long for super-administrative users to see the changes

- Could Have
  - Removing from Schools would not take too long for super-administrative users to see the changes

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