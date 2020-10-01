[[_TOC_]]
# Standard User
The functionality of the standard user is also available to the Admin user and the Super-Admin user.
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
      1. The user should be able to adjust the playback speed of the audio content.
      2. The user should be able to pause and play the audio content.
      3. The user should be able to replay the audio content.
3. The system must recognize when the user completes the challenge, and display feedback to the user.
   1. The total time must be displayed
   2. The average WPM must be displayed
   3. The accuracy must be displayed as a percentage
   4. If the user has placed on the leaderboard, 
   - Show information like a: total time, b: average wpm, c: accuracy, d: leaderboard(Can be toggled by Admin) upon completing the typing challenge
   - The leaderboard will show a name, speed, time, and the type of challenge completed (max number of entries?)
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


# Administrator Users
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
