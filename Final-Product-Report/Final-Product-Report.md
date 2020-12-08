[[_TOC_]]

# User Documentation

## As-Built Product Description
Word Flow is an application to train users to type faster and with greater accuracy. The focus is on unique uses not covered by other typing tools- special characters used by programming languages, and typing from audio content. It is designed with typing classes in a school environment in mind, and thus includes a hierarchical user management structure, based on a School having Classrooms.

Main functionality includes:
- Users can complete a variety of typing challenges and view their speed and accuracy for each challenge and a record of challenges that they have completed.
- Super Admin users can create a School, invite users to join, and create Classrooms of users.

The typing challenges will range from standard English words, to specific programming languages, and typing from audio dictation. It can check the user's input text against the challenge text, showing the user where they are in the text and if they have made any errors, and how long they have spent on the challenge. Once complete, they will see their speed and accuracy for the challenge.

The application is designed for desktop environments and created in the Python programming language. It utilizes the Firebase API for user and database management so that users can access their account information from different devices. Text content is stored in the same database. Audio content for dictation mode is generated via text-to-speech on the text content stored in the database. 

## [Usage Instructions](Final-Product-Report/User-Documentation/Usage-Instructions)

## As-Built Requirements
[Functional Requirements](Requirements/Functional-Requirements) are referenced by their number, formatted like so: **additions**, _deletions_ and **_changes_**
### Standard Users
- _F0.3 (view other users in the same classroom)_
- _F0.4 (see display names of admins/super-admins at school)_
- **_F1.3 "able to see the time elapsed since they began the challenge" --> "time remaining"_**
- **_F.2.2.1 The number of languages available in programmer mode was reduced to three and include Python, C, and HTML. The rest are not available._**
- _F4.3 (log out of account)_
- _F5 (audio controls on dictation challenge)_
- **"When using the dictation challenge mode: the next word should be played back when a space character is inputted"**
- _F6.1 (change display name)_
- _F7.3 (view a report of accuracy/wpm over time)_
- _F8 (view assignments)_
- _F9 (view leaderboard)_
- _F10-13 (all "could haves" for standard users)_
- **"Users should be able to see a virtual keyboard when completing a typing challenge that shows the keyboard layout and which keys they are pressing"**

### Admin Users
- **_F15 (management of classrooms, as far as creating and changing membership, was changed to super-admin scope)_**
- _F15.2-4 (classroom functionality is incomplete)_
- _F16 (assigning challenges)_
- _F17 (reports)_
- _F18 (classroom functionality is incomplete)_
- _F19 (showing/hiding leaderboard)_

### Super-Admin Users
- _F23.1 (users are no longer managed on an individual basis, but on a classroom level)_
- _F23.2 (classroom functionality is incomplete)_
- _F24 (user management functionality is incomplete)_
- _F25 (creating custom typing challenge content is not implemented)_

### Other changes
- [wpm](Requirements/Definitions#words-per-minute-wpm) was changed from a calculation based on keystrokes to actual _words_ per minute
- as accuracy was based on that definition of wpm, its definition has also changed.
- there is no longer a requirement for a "quit" button- the user simply navigates to another page
- there are references in the [Non-Functional Requirements](Requirements/Non-Functional-Requirements) to features that are removed in the functiona requirements above
- the Firebase library that was originally used, forcing a maximum Python version of < 3.7 is no longer used by the project.

The system architecture originally proposed is very close to the project as implemented (the layered architecture, with blackboard for typing challenges, and pipes/filters for the rest). Although, the pipes and filters in the project as built are dependent on what types of objects are passed to them (eg: The classroom dict cannot be passed through a user function without consequences) and so should be considered a modified pipe-and-filter design. 

# Programmer Documentation
## Compilation Instructions
[README](https://git.cs.usask.ca/CMPT370-01-2020/group2/-/blob/master/README.md)

### External Libraries
* [requests 2.25.0](https://pypi.org/project/requests/)
* [firebase-admin 4.4.0](https://pypi.org/project/firebase-admin/)
* [pyttsx3 2.90](https://pypi.org/project/pyttsx3/)
* [yapf 0.30.0](https://pypi.org/project/yapf/)

### Firebase
* Authentication: The API endpoint for authentication is [Google Identity Toolkit v1](https://cloud.google.com/identity-platform/docs/use-rest-api)
* Database: [Google Cloud Firestore](https://firebase.google.com/docs/firestore) is used as the document database.

Libraries used for testing are under Testing Documentation and Instructions.

## [Testing Documentation and Instructions](Final-Product-Report/Testing-Documentation-&-Instructions)
## [As-Built Design](Final-Product-Report/As-Built-Design)
## [Known Bugs, Incomplete Features, and Workarounds](Final-Product-Report/Known-Issues)

