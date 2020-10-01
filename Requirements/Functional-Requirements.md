[[_TOC_]]
# Privacy (Must have)
0. Users cannot be viewed by other users, with the following exceptions. 
   1. Super-Admins can view all of the users inside of their school.
   2. Admins can view all of the users assigned to their management by a Super-Admin.
   3. Standard Users can view other users who are in the same Classroom.
   4. Standard Users can see the display names of the Admins and Super-Admins in their school.

# Standard User
## Must Haves
1. User must be able to take a typing challenge. The typing challenge will consist of content that they will have to type, and a space for the user to enter the content.
   1. They must be able to see their typing progress highlighted to indicate their position in the challenge (unless taking a challenge in Dictation mode)
   2. They must be able to see typing errors they have made highlighted in the challenge in a different colour (unless taking a challenge in Dictation mode). 
   3. They must be able to see the time elapsed since they began the challenge.
   4. They must be able to Quit the challenge at any time.
2. User must be able to select from different modes when taking a typing challenge.
   1. Content must be available in a "Standard" mode, consisting of English words, spaces, and punctuation.
   2. Content must be available in a "Programmer" mode, where the user types code, including special characters.
      1. The following languages will be available in programmer mode: Python, Java, PHP, HTML, C
   3. Content must be available in "Dictation" mode, where audio is played back over the devices speakers, and the user types words separated by spaces (no punctuation).
3. The system must recognize when the user completes the challenge, and display feedback to the user.
   1. The total time must be displayed
   2. The average WPM must be displayed
   3. The accuracy must be displayed as a percentage
4. The user must be able to manage their user account.
   1. They must be able to log into their account using a valid email and password combination
   2. They must be able to create an account
   3. They must be able to log out of their account
   4. They must be able to join a School when invited by a Super-Admin

## Should Haves
5. When using the Dictation Challenge mode:
   1. The user should be able to adjust the playback speed of the audio content.
   2. The user should be able to pause and play the audio content.
   3. The user should be able to replay the audio content.
6. When managing their user account:
   1. They should be able to change their Display Name
   2. They should be able to change their account password.
   3. They should be able to request a password reset to be sent to their email address when they are not logged into their account.
7. They should be able to view a report of their typing history
   1. They should be able to view a list of completed challenges
   2. For each completed challenge, they should be able to view the date/time it was completed, and their WPM, accuracy, total time, and challenge mode.
   3. They should be able to view a report of their WPM and accuracy over time.
8. They should be able to view Typing challenges which are assigned to them by an Admin user.
   1. They should be able to view the date it was assigned, the date it is due, and the challenge mode.
   2. They should be able to take the challenge to complete the assignment.
9. The user should be able to view the leaderboard, if the Admin user has made that option available.
   1. The leaderboard should have a different section for each challenge mode available, listing the top 20 entries for that challenge mode completed by the Classroom.
   2. Places on the leaderboard will be calculated by multiplying a challenge's WPM by the accuracy
   3. The information displayed on the leaderboard will be the user's Display Name, the WPM, and the Accuracy
   4. If the user has placed on the leaderboard, their new place on the leaderboard should be displayed when they complete the challenge.

## Could Haves
10. A Numbers challenge mode could be selected, using the numerical and mathematical keys on the numpad.
11. An image could be generated when a user completes a challenge, to share with others.
12. Reports could display which 2-letter character combinations the user is weakest at.
13. Multiple languages (ie: English, Spanish, French) could be supported.

# Admin Users
## Must Haves
14. Admin users must be able to perform all of the same actions that a standard user can.
15. Admin users must be able to manage Classrooms
    1. Admin users must be able to create Classrooms.
    2. Admin users must be able to add users to Classrooms.
    3. Admin users must be able to remove users from Classrooms.
    3. Admin users must be able to delete Classrooms.
## Should Haves
16. Admin users should be able to assign typing challenges to be completed by Classrooms or specific users.
    1. The assigned challenge should be able to have a due date.
    2. The assigned challenge should be able to have a mode selected.
17. Admin users should be able to view reports on specific users that they manage.
    1. The reports should be filter-able to only show assigned challenges.
    2. A report should show the user's WPM or accuracy over a given period of time.
    3. A report should show a list of the user's completed typing challenges. For each item on the list, the report should show: 
       1. Accuracy
       2. WPM
       3. Date/time completed.
       4. Challenge mode.
       5. Total time.
18. Admin users should be able to view reports on Classrooms that they manage.
    1. A report should show the Classroom's average WPM over a given period of time.
    2. A report should show the Classroom's average accuracy over a given period of time.
    3. A report should show the users in the Classroom's comparative WPM.
    4. A report should show the users in the Classroom's comparative Accuracy.
19. Admin users should be able choose to show or hide a leaderboard for Classrooms that they manage. 

# Super-Admin (SA) Users
## Must Haves
20. Super-Admin users must be able to perform all of the same actions that an Admin user can.
21. SA users must be able to manage users.
    1. They must be able to create users of all types, including Super-Admin.
    2. They must be able to change privilege levels of Admin and Standard Users.
22. SA users must be able to manage Schools.
    1. They must be able to create a School.
    2. They must be able to invite users to the School.

## Should Haves
23. When managing Schools:
    1. They should be able to assign and unassign standard users to be managed by Admin users.
    2. They should be able to assign and unassign Classrooms to be managed by Admin users.

## Could Haves
24. When managing Schools:
    1. They could be able to remove Admin or Standard users from a School.
    2. They could be able to remove their own account from a School.
25. Super-Admins can create custom typing challenge content.