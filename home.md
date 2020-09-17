## Group Members

- Cameron Mcleod - cvm791@mail.usask.ca
- Abdul Salawu - aas171@mail.usask.ca
- Pucheng Tan
- Sarah Chen
- Tara Epp - tme017@mail.usask.ca

## Project Description

This is a typing tool that helps users improve their typing speed. The target users are any computer users that wish to improve their speed. The user is given text to type, and metrics are recorded and displayed at the end of the test. 

### Must Have

1. GUI interface
2. Gets text from a 3rd party API (text excerpt), displays to user
3. Record key presses from the user and compare to the given text
4. Calculate the user's accuracy (%) and speed (wpm: 5 characters/word including spaces, punctuation), present to the user
5. Display a timer (elapsed time)

### Should have

1. Record data calculated by user's accuracy and speed locally on the device
2. Different typing settings available:
a. Programmer mode with more brackets, special characters.
b. Select text source (such as novels, song lyrics)
c. Change length of text excerpt
3. Locally stored leaderboard with name entered after completing the test
4. Give user a specific amount of time to type as much content as possible

### Could Have

1. User selects specific characters to focus on. ($ for PHP, etc)
2. User creates a user account that can be accessed from multiple devices
3. Change keyboard layout: like from QWERTY to Dvorak
a. Display virtual keyboard on screen, keys being pressed
b. If in mode of specific key rows, character set would change
4. Typing from audio (ie: learn new language, or stenographers)
5. Track user strengths and weaknesses (between certain letters/combinations)
6. Challenge users based on their weaknesses.
a. On their weak letter combinations
7. GUI enhancement: display as a 2D chasing game, with you "running" from the police by typing faster than them. 
a. Police speed is your previous speed
b. Manually set police speed
c. Start slow, go faster


# Technology(s)

1. Python
2. API(s) to source text (TBD)