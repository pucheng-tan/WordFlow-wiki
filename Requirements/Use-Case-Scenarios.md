[[_TOC_]]

# 00: User creates an account
- The user must create an account before they are able to login.

| ID: | 00.1 |
| ------: | ------ |
| **Use Case** | The first Super-Admin account is created for a new School |
| **Primary Actors** | Super-Admin user |
| | Firebase API |
| **Preconditions** | None |
| **Basic Flow** | The user: |
| 1. | Opens the software |
| 2. | Selects "Create Account" |
| 3. | Enters a valid email address into the email field. |
| 4. | Enters the same complex password into the password and verify password fields. |
| 5. | Clicks "Create." A success message indicating that the account has been created is displayed. |
| 6. | Selects the Profile menu option. |
| 7. | Under the School section, selects the option to create a new School. |
| 8. | For the new school, enters: name, mailing address, phone number. |
| 9. | Optionally enters an email domain that can be used to automatically verify users against. |
| 10. | Clicks "Create School." A success message is displayed indicating that the school has been created, and the user has been added as a Super Administrator |

| ID: | 00.2 |
| ------: | ------ |
| **Use Case** | A Super-Admin account is created for an existing school |
| **Primary Actors** | Existing Super-Admin user ("ESA") |
| | New Super-Admin user ("NSE") |
| | Firebase API |
| **Preconditions** | - The School has already been created |
| | - NSE already has the software installed on their device |
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
| **Primary Actors** | Standard user, firebase |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | User chooses a username and password |
| 2. | User types in email |
| 3. | User presses submit |
| 4. | Firebase reponds |
| 4. | If the email is not taken, the account will be created |


# 01: Users can Login
- The User can login through the firebase API

| ID: | 01.1 |
| ------: | ------ |
| **Use Case** | User logs in |
| **Primary Actors** | Every type of user (Standard, Admin, Super-Admin), Firebase (authentication) |
| **Preconditions** | User has a user account |
| **Basic Flow** |  |
| 1. | User starts software and arrives at login screen |
| 2. | User click on username input box |
| 3. | User enters in username |
| 4. | User clicks on password box |
| 5. | User enters in password |
| 6. | User presses enter |
| 7. | Firebase authentication responds |


# 02: Users can selects the Mode
- The user can choose between Standard, Programmer, and Dictation mode

| ID: | 02.1 |
| ------: | ------ |
| **Use Case** | user starts a typing challenge in programmer mode |
| **Primary Actors** | every type of user, firebase |
| **Preconditions** | user is logged in and authenticated, user has internet connection |
| **Basic Flow** |  |
| 1. | After the user has logged in, a dashboard will be displayed |
| 2. | The user clicks on the programming tab |
| 3. | Next the user will be able to select the programming language and the duration of the challenge (the challenge's options are TBD) |
| 4. | Once the user is ready, they press the start button |
| 5. | The challenge will begin with the duration and programming language of the users choice |
| 6. | The users stats from the challenge will be uploaded to the firebase db |


| ID: | 02.2 |
| ------: | ------ |
| **Use Case** | User starts a typing challenge in normal mode |
| **Primary Actors** | Any type of user, firebase |
| **Preconditions** | User is logged in and authenticated, user has an internet connection |
| **Basic Flow** |  |
| 1. | After the user has logged in, a dashboard will be displayed |
| 2. | User clicks on normal typing mode |
| 3. | User will be able to adjust the typing challenge (TBD), and the duration of the typing challenge |
| 4. | Once the user is ready, they press the start button |
| 5. | The challenge will begin with adjustments the user made in step 3 |
| 6. | The users stats from the challenge will be uploaded to the firebase db |


| ID: | 02.3 |
| ------: | ------ |
| **Use Case** | User starts a typing challenge in dictation mode |
| **Primary Actors** | Every type of user |
| **Preconditions** | User is logged in and authenticated |
| **Basic Flow** |  |
| 1. | From the dashboard, the user will click on the dictation tab |
| 2. | This will lead to a new page where the user can adjust the speed of the audio |
| 3. | After adjusted the audio to text test, the user can press the start button |
| 4. | One-by-one, words will begin being read out loud, and the user has to type the words before the next one pops up |
| 5. | After the test is done, the user will be notified of there typing stats |


# 03: User can view their typing test results
- The user can see all of their information from prior test and other metrics like wpm etc...

| ID: | 03.1 |
| ------: | ------ |
| **Use Case** | User checks their typing stats |
| **Primary Actors** | Every type of user, firebase |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | After logging in, the user will be displayed a dashboard |
| 2. | Somewhere on the dashboard (TBD) the users stats will be displayed, with a button to pull up more stats on page just for stats |


# 04: Administrator can create and manage groups
- The administrator can create groups and invite or delete users from a group

| ID: | 04.1 |
| ------: | ------ |
| **Use Case** | Admin adds user to their group |
| **Primary Actors** | Admin user (super admin in the same domain) |
| **Preconditions** | Admin has control of the group, the user the admin wants to add to the group must exist and be in the domain |
| **Basic Flow** |  |
| 1. | Once the admin logs in, they will be directed to the main dashboard. |
| 2. | When a user gets to the main dashboard, if they have admin persmissions, a manage groups page will be present |
| 3. | Admin clicks on manage groups page |
| 4. | Admin selects the group the want to manage |
| 5. | Admin clicks add new member |
| 6. | A list of users in the domain will appear |
| 7. | The admin clicks on the user they want to add and presses add |

| ID: | 04.2 |
| ------: | ------ |
| **Use Case** | Admin creates a new group |
| **Primary Actors** | Admin user |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | From the dashboard, the admin will click on the manage groups tab |
| 2. | From the manage groups page, the admin will be able to add a new group |
| 3. | The admin will first give the group a name, then press submit |

| ID: | 04.3 |
| ------: | ------ |
| **Use Case** | Admin deletes a group |
| **Primary Actors** | Admin user |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | From the dashboard, the admin will click on the manage groups tab |
| 2. | From the manage groups page, the admin will be able to see each of their groups |
| 3. | User selects the delete button on the group they wish to delete |
| 4. | Admin will be given a popup menu to double-check if the admin wants to delete the group |
| 5. | If the admin clicks yes, the group will be deleted |


# 05: Administrator can assign typing challenges
- admins can use these challenges to gage their group's performance and improvement

| ID: | 05.1 |
| ------: | ------ |
| **Use Case** | Admin assigns typing challenges to group |
| **Primary Actors** | Admin user |
| **Preconditions** | The admin is assigning a typing challenge to a group that they created or were given permissions to |
| **Basic Flow** |  |
| 1. | From the dashboard, the admin will click on the manage groups tab |
| 2. | Next, admin clicks on the group they want to manage |
| 3. | The admin will be able to pick a typing challenge, and edit the typing challenge with options such as duration and difficulty |
| 4. | The admin clicks a date/time which the typing challenge is to be completed by |
| 5. | The admin will click the submit button and the task will be sent to the group |


# 06: Admins can view a group report
- the group report will show statistics pulled from the assigned typing challenges 

| ID: | 06.1 |
| ------: | ------ |
| **Use Case** | Admin views a group report |
| **Primary Actors** | Admin user |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. | From the dashboard, admin clicks on the groups tab |
| 2. | When the admin selects the group that they manage, a list of the members will appear, and next to the list, the groups stats will show |
| 3. | The admin can then click on group report to see a report of the groups stats, or click on a single user to view there stats |


# 07: Users can take assigned tests
- the user can take tests that an admin assigned for the user's group

| ID: | 07.1 |
| ------: | ------ |
| **Use Case** | User attempts a certain group's assigned typing challenge |
| **Primary Actors** | User of a certain group (ex: group A) |
| **Preconditions** | User has been invited to group A and has accepted the invite, admin has sent out a task for group A |
| **Basic Flow** |  |
| 1. | From main dashboard, user clicks on groups pop down menu |
| 2. | User clicks on group A |
| 3. | Under challenges, user clicks on the challenge to be completed |
| 4. | User completes the challenge |
| 5. | Admin is notified that a user in their group has completed the challenge |



# 08: Super-Administrator can create and manage Administrators
- A super Admin can make a standard user an Admin User

| ID: | 08.1 |
| ------: | ------ |
| **Use Case** | Super admin creates a new admin |
| **Primary Actors** | Super admin |
| **Preconditions** | The user that the super admin wants to give admin persmissions to exists |
| **Basic Flow** |  |
| 1. | Somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin permissions |
| 2. | If the super admins clicks it, a list of users that the super admin had previously assigned to be admin will be shown |
| 3. | The super admin will be able to click on the add new button |
| 4. | After pressing the add new button, the super admin can type the unique identifier of the user they want to assign admin permissions |
| 5. | After the super admin presses submit, the user that was assigned to be an admin will be notified|


| ID: | 08.2 |
| ------: | ------ |
| **Use Case** | Super admin removes an admins permissions |
| **Primary Actors** | Super admin |
| **Preconditions** | The admin that the super admin wants to demote exists |
| **Basic Flow** |  |
| 1. | Somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin permissions |
| 2. | If the super admins clicks it, a list of users that the super admin had previously assigned to be admin will be shown |
| 3. | The super admin selects the admin that they want to remove |
| 4. | After select the user and press remove, the super admin will be given an extra popup to make sure that the super admin chose the correct admin |
| 5. | After the super admin presses submit, the admin that was removed will be notified |


# 09: Super-Administrator can promote am admin to super-admin
- A super Admin can make a standard user an Admin User

| ID: | 09.1 |
| ------: | ------ |
| **Use Case** | Super admin adds a user to their domain |
| **Primary Actors** | Super admin |
| **Preconditions** | The user that the super admin wants to add must exist |
| **Basic Flow** |  |
| 1. | Somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin permissions |
| 2. | After clicking on the special tab, there will be a place to manage their domain |
| 3. | The super admin presses 'add new user' |
| 4. | The super admin types the user's unique id and presses submit |
| 5. | The user will be added to the the domain |


| ID: | 09.2 |
| ------: | ------ |
| **Use Case** | The super admin removes a user from their domain |
| **Primary Actors** | Super admin |
| **Preconditions** | The user that the super admin wants to add must exist |
| **Basic Flow** |  |
| 1. | Somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin permissions |
| 2. | After clicking on the special tab, there will be a place to manage their domain, with a list of users in the domain |
| 3. | The user clicks on the user they want to delete and presses delete |
| 4. | The super admin will get an extra popup assuring that they chose the correct user |
| 5. | If the super admin presses yes, the user will be deleted from the domain |










//Keap this here to copy and paste

| ID: | 04.1 |
| ------: | ------ |
| **Use Case** |  |
| **Primary Actors** |  |
| **Preconditions** |  |
| **Basic Flow** |  |
| 1. |  |
| 2. |  |
| 3. |  |
| 4. |  |
| 5. |  |
| 6. |  |
| 7. |  |
| 8. |  |
| 9. |  |
| 10. |  |
