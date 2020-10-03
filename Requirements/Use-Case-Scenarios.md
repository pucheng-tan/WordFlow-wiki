[[_TOC_]]

# 00: User creates an account
- The user must create an account before they are able to login.

| ID: | 00.1 |
| ------: | ------ |
| **Use Case** | The first Super-Admin account is created for a new School |
| **Primary Actors** | Super-Admin user |
| | Firebase API |
| **Preconditions** | None |
| **Basic Flow** |  |
| 1. | Opens the software |
| 2. | Selects "Create Account" |
| 3. | Enters a valid email address into the email field |
| 4. | Enters the same complex password into the password and verify password fields |
| 5. | Clicks "Create." A success message indicating that the account has been created is displayed |
| 6. | Selects the Profile menu option |
| 7. | Under the School section, selects the option to create a new School |
| 8. | For the new school, enters: name, mailing address, phone number |
| 9. | Optionally enters an email domain that can be used to automatically verify users against |
| 10. | Clicks "Create School." A success message is displayed indicating that the school has been created, and the user has been added as a Super-Admin |

| ID: | 00.2 |
| ------: | ------ |
| **Use Case** | A Super-Admin account is created for an existing school |
| **Primary Actors** | Existing Super-Admin user ("ESA") |
| | New Super-Admin user ("NSE") |
| | Firebase API |
| **Preconditions** | The School has already been created |
| | NSE already has the software installed on their device |
| **Basic Flow** | |
| 1. | ESA opens the software, and selects User Management |
| 2. | ESA chooses option to create new User |
| 3. | ESA enters the NSE's email address |
| 4. | ESA selects the option for "Super-Admin" user. A warning message is displayed indicating that this user will have full privileges. |
| 5. | ESA dismisses the warning by clicking "Continue" |
| 6. | ESA clicks the "Create User" button to invite NSE to the school |
| 7. | NSE receives an email inviting them to create an account within the School, and clicks the "Create Account" link in the email. |
| 8. | The software opens on NSE's device. NSE enters a complex password in the password and verify password fields, and clicks "Create Account" |
| 9. | A success message is displayed, indicating that NSE's account has been created and they have joined the school as a Super-Admin |

| ID: | 00.3 |
| ------: | ------ |
| **Use Case** | Standard user creates an account for the first time |
| **Primary Actors** | Standard user |
|  | Firebase |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | User enters an email into the email field and the same complex password into the password and verify password fields |
| 2. | User presses submit |
| 3. | Firebase responds |
| 4. | If the email is not taken, the account will be created. The user receives an email to verify their account, and is automatically logged in. |


# 01: User logs in
- The User logs in through the Firebase API

| ID: | 01.1 |
| ------: | ------ |
| **Use Case** | User logs in |
| **Primary Actors** | Any type of user (Standard, Admin, Super-Admin)|
|   | Firebase (authentication) |
| **Preconditions** | User has a user account |
| **Basic Flow** |  |
| 1. | User starts software and arrives at login screen |
| 2. | User click on email input box |
| 3. | User enters in email |
| 4. | User clicks on password box |
| 5. | User enters in the correct password |
| 6. | User presses enter |
| 7. | Firebase authentication responds |
| 8. | The user is redirected to a dashboard screen. |


# 02: User selects the Challenge Mode
- The user can choose between Standard, Programmer, and Dictation mode for a typing challenge

| ID: | 02.1 |
| ------: | ------ |
| **Use Case** | User takes a typing challenge |
| **Primary Actors** | Any type of user|
|  | Firebase |
| **Preconditions** | User is logged in and authenticated |
|  | User has internet connection |
| **Basic Flow** |  |
| 1. | After the user has logged in, a dashboard will be displayed |
| 2. | The user clicks on the Programming option |
| 3. | The user selects a programming language, Java, from a list of available options |
| 4. | The user clicks a start button to begin the challenge |
| 5. | Text content in the Java programming language is displayed to the user |
| 6. | When the user begins typing, a timer begins tracking time |
| 7. | The user types the text content of the challenge. Each correct character is highlighted. Each word disappears from the user's text input once it is typed completely. |
| 8. | Once the user types the last word, the typing challenge is over and the timer will stop counting |
| 9. | The challenge statistics: WPM, accuracy, and total time are displayed to the user, and saved in the Firebase database with the user's unique identifier |
| **Alternate Flows** |  |
| 2a. | The user clicks on the Standard option |
| 3a. | omitted |
| 5a. | Text content is displayed to the user, composed of English words, spaces, and punctuation. |
| 7b. | The user enters an incorrect character. It is highlighted in a colour distinct from the correct characters |
| 7b1. | The user backspaces to remove the incorrect character and re-enter it, or the user enters a space to move onto the next word |


| ID: | 02.2 |
| ------: | ------ |
| **Use Case** | User takes a typing challenge in dictation mode |
| **Primary Actors** | Any type of user |
| **Preconditions** | User is logged in and authenticated |
| **Basic Flow** |  |
| 1. | From the dashboard, the user will click on the Dictation option |
| 2. | An audio speed option is displayed to the user. The user changes the speed to 0.75x |
| 3. | The user clicks the start button to begin the text. A timer is displayed, counting the time elapsed since starting the challenge. |
| 4. | Audio content is played back to the user, consisting of English words |
| 5. | The user types each word, separated by spaces. The word disappears from their text input once it is typed correctly or the user has moved to the next word by typing a space. |
| 6. | The user completes the challenge by entering all of the words of the challenge. The timer stops counting. |
| 7. | The challenge statistics: WPM, accuracy, and total time are displayed to the user, and saved in the Firebase database with the user's unique identifier |
| **Alternate Flows** |  |
| 5a. | The user types a word incorrectly. The incorrect character(s) are highlighted on their text input. |
| 5a1. | The user backspaces to reenter the content, or enters a space to move onto the next word. |
| 6b. | The user is unable to complete the challenge before the audio content has completed playing. |
| 6b1. | The user clicks a button to replay the audio content from where their first incomplete word. |


# 03: User views their typing history
- The user views a record of challenges that they have previously taken.

| ID: | 03.1 |
| ------: | ------ |
| **Use Case** | User views their typing history |
| **Primary Actors** | Any type of user |
|  | Firebase |
| **Preconditions** | The user is logged in |
| **Basic Flow** |  |
| 1. | From the dashboard, the user selects the History option |
| 2. | A list of previously completed typing challenges is displayed, from newest to oldest. For each challenge, the total time, WPM, accuracy, and challenge mode is displayed |
| 3. | The user selects the option to view their progress report |
| 4. | A chart is displayed, with a date range beginning from their first typing challenge and ending with their more recent challenge, graphing their WPM on each challenge on one axis and the date range on the other. |
| 5. | The user changes an option from WPM to accuracy- the WPM axis changes to accuracy, and their accuracy is graphed instead of their WPM |
| 6. | The user adjusts the beginning date and end date of the date range. The data and labels on the chart adjusts accordingly. |


# 04: Admin manages Classrooms
- The Admin can create Classrooms and assign or remove users from a Classroom

| ID: | 04.1 |
| ------: | ------ |
| **Use Case** | Admin adds a user to their Classroom |
| **Primary Actors** | Admin user |
| **Preconditions** | Admin has control of the Classroom |
| | User is previously assigned to the management of Admin by a Super-Admin |
| | Admin is logged in |
| **Basic Flow** |  |
| 1. | The Admin selects Manage Classrooms from the dashboard. |
| 2. | Admin selects the Classroom the want to manage |
| 3. | Admin clicks add new member |
| 4. | A list of users the Admin manages is displayed |
| 5. | The Admin clicks on the user they want to add and presses add |
| 6. | A success message is displayed indicating that the user has been added to the Classroom |

| ID: | 04.2 |
| ------: | ------ |
| **Use Case** | Admin creates a new Classroom |
| **Primary Actors** | Admin user |
| **Preconditions** | Admin is logged in |
| **Basic Flow** |  |
| 1. | The Admin selects Manage Classrooms from the dashboard. |
| 2. | The Admin clicks the "New Classroom" button. |
| 3. | The Admin enters a name for the Classroom and clicks the Submit button. |
| 4. | A success message is displayed, indicating that the Classroom has been created. |

| ID: | 04.3 |
| ------: | ------ |
| **Use Case** | Admin deletes a Classroom |
| **Primary Actors** | Admin user |
| **Preconditions** | Admin is logged in, and is in the Manage Classrooms view |
| | The Classroom to be deleted already exists |
| **Basic Flow** |  |
| 1. | The Admin clicks the delete button on the Classroom they want to delete. |
| 2. | A message is displayed, confirming that the Admin wishes to delete the Classroom. |
| 3. | The Admin clicks the confirm button. |
| 4. | A success message is displayed, indicating that the Classroom has been deleted. The Classroom is removed from the database. |
| 5. | The Classroom is no longer visible on the list of Classrooms. |


# 05: Admin assigns typing challenges
- Admins can assign typing challenges to users under their management to be completed by them.

| ID: | 05.1 |
| ------: | ------ |
| **Use Case** | Admin assigns a typing challenge to a Classroom |
| **Primary Actors** | Admin user |
| **Preconditions** | The Admin has management of the Classroom |
| | Admin is logged in and in the Manage Classrooms view |
| **Basic Flow** |  |
| 1. | The Admin clicks a Classroom from the list. A view is displayed showing the name of the Classroom, the users, a Reports button, a list of challenges previously assigned to the Classroom, and an option to Assign Typing Challenges |
| 2. | The Admin selects the option to Assign Typing Challenges. |
| 3. | The Admin selects the challenge mode as Programming and the language as C. |
| 4. | The Admin selects the due date as January 14, 2021, at 11:59 pm. |
| 5. | The Admin clicks the submit button to assign the challenge to the classroom. |
| 6. | The Classroom view is displayed to the Admin. The challenge that was assigned is now at the top of the list of challenges assigned to the classroom. |


# 06: Admin views a Classroom Report
- The Classroom Report will show the Classroom's average WPM and accuracy over time, and a comparison of the Classroom's users' average WPM and accuracy in a chosen date range.

| ID: | 06.1 |
| ------: | ------ |
| **Use Case** | Admin views a Classroom report |
| **Primary Actors** | Admin user |
| **Preconditions** | The Admin has management of the Classroom |
| | Admin is logged in and in the Manage Classrooms view |
| **Basic Flow** |  |
| 1. | The Admin clicks a Classroom from the list. A view is displayed showing the name of the Classroom, the users, a Reports button, a list of challenges previously assigned to the Classroom, and an option to Assign Typing Challenges |
| 2. | The Admin selects the Report option. |
| 3. | A chart is displayed, showing the average WPM of the Classroom on one axis and dates on the other axis. The date range begins on the day the Classroom was created, and ends on the current day. |
| 4. | The Admin changes the "WPM" option to "Accuracy". The data adjusts to show Accuracy data instead of WPM. |
| 5. | The Admin changes the date range to begin one week prior to the current date. The data adjusts according to the data range. |
| 6. | The Admin changes the "Classroom Average" option to "Comparative". The chart shows a bar for each student, representing their average accuracy within the given date range. The option to change the data from Accuracy to WPM is still available. |


# 07: User takes an assigned typing challenge.
- the user can take typing challenges assigned to their Classroom or to the user specifically.

| ID: | 07.1 |
| ------: | ------ |
| **Use Case** | User takes a typing challenge assigned to their Classroom |
| **Primary Actors** | User |
| **Preconditions** | User is part of the Classroom "Room 203" |
|  | Admin has assigned a typing challenge to the Classroom "Room 203" |
|  | User is logged in |
| **Basic Flow** |  |
| 1. | From the main dashboard, Assigned Challenges has a number 1 indicating that there is 1 incomplete Challenges assigned to the user. |
| 2. | The user clicks Assigned Challenges, and a list of the Challenges is displayed. For each challenge, the challenge mode, assign date, due date, and a button to take the challenge is displayed. |
| 3. | The user clicks the button to take the assigned challenge. |
| 4. | User completes the challenge |
| 5. | When viewing the list of assigned challenges, there is no number, indicating that all assigned challenges are complete. When the user expands the list, the challenge is still displayed with an indication that it is complete. |
| 6. | Admin is able to view that the user has completed the challenge, including their WPM, accuracy, and total time. |



# 08: Super-Admin can create and manage Admins
- A Super-Admin can make a standard user an Admin User

| ID: | 08.1 |
| ------: | ------ |
| **Use Case** | Super-Admin makes a Standard User into an Admin User |
| **Primary Actors** | Super-Admin User |
| | New Admin User (NAU) |
| **Preconditions** | New Admin User exists in the Super-Admin's School as a Standard User |
|  | Super-Admin is logged in |
| **Basic Flow** |  |
| 1. | From the dashboard, the Super-Admin selects the Manage Users option. A list of users in the Super-Admin's school is displayed. |
| 2. | The Super-Admin starts typing the NAU's display name or email address to filter the list. |
| 3. | The Super-Admin clicks the desired user. |
| 4. | The Super-Admin selects the option to change the NAU's privilege level, and selects "Admin" |
| 5. | The Super-Admin clicks Submit. A prompt is displayed, asking if the Super-Admin would like to change the user to Admin user. |
| 6. | After clicking confirm, a success message is displayed indicating that the NAU's privilege level has been changed. |
| 7. | An email is sent to the NAU informing them of their change in privilege level. |
| **Basic Flow** |  |
| 4a. | The Super-Admin selects the option to change the NAU's privilege level, and selects "Super-Admin" |
| 5a. | The Super-Admin clicks Submit. A prompt is displayed, asking if the Super-Admin would like to change the user to Super-Admin user. There is a warning that once this change has been made, it cannot be undone. |


| ID: | 08.2 |
| ------: | ------ |
| **Use Case** | Super-Admin changes an Admin user into a Standard User |
| **Primary Actors** | Super-Admin |
| | Old Admin User (OAU) |
| **Preconditions** | The OAU exists as an Admin User in the Super-Admin User's School |
|  | Super-Admin is logged in |
| **Basic Flow** |  |
| 1. | From the dashboard, the Super-Admin selects the Manage Users option. A list of users in the Super-Admin's school is displayed. |
| 2. | The Super-Admin User types "Admin" into the search box, and the users are filtered to Admin users. |
| 3. | The Super-Admin selects the OAU. |
| 4. | The Super-Admin selects the option to change the OAU's privilege level, and selects "Standard" |
| 5. | The Super-Admin clicks Submit. A prompt is displayed, asking if the Super-Admin would like to change the OAU to Standard user. |
| 6. | After clicking confirm, a success message is displayed indicating that the OAU's privilege level has been changed. |


| ID: | 09.2 |
| ------: | ------ |
| **Use Case** | The Super-Admin removes a user from their School |
| **Primary Actors** | Super-Admin |
| **Preconditions** | The User that the Super-Admin wants to remove must be in the Super-Admin's School |
|  | Super-Admin is logged in |
|  | The User is not a Super-Admin |
| **Basic Flow** |  |
| 1. | From the dashboard, the Super-Admin selects the Manage Users option. A list of users in the Super-Admin's School is displayed. |
| 2. | The Super-Admin User types the User's email into the search box, and the users are filtered. |
| 3. | The Super-Admin User selects the User. A view is displayed with the User's display name, email address, date added to School, privilege level, Admin management (any Admins who manage the user), and Classroom membership. There are options to change the privilege level, Admin management, and Classroom membership. An option is available to remove the User from the School. |
| 4. | The Super-Admin User selects the option to remove the User from the School. A prompt is displayed, warning the Super-Admin User that this action cannot be undone, and once the user has been removed, the Super-Admin will not be able to manage the User unless they are invited to the School again. |
| 5. | The Super-Admin User confirms to remove the User from the School. A success message is displayed. |
| 6. | The Super-Admin is redirected to the User Management view. The removed User is no longer on the list. |
