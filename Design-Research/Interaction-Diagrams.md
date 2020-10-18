This is a page for:

● Interaction Diagrams

○ UML sequence diagram(s)


Notes for the sequence diagrams in use cases 05-08:

Notes that should probably be left:
- Often in the sequence diagrams, repeated calls can be seen going from the ActiveWindow to a Service, this is meant to represent the layers in our architecture style with the GUI taking in parameters from the User but then passing it on to the logic layer to actually do the computation.
- Despite not being pictured in the sequence diagrams for brevity, it is assumed the logic layer would call the appropriate methods in the API service which would then make the appropriate changes in the Data.

Notes that should probably be removed later:
- I based them off of the components_domain_layer.svg image made by Tara which can be found in the Discord chat on October 15th
- I assume that clicking on a component in the MainMenu would bring up the appropriate list in the ActiveWindow e.g. Clicking on  UserManagement brings up UserList
- Other assumptions I make and functions in my sequence diagrams that are not in the image are:
  - Use Case 05.1
    - assignChallenge(Classroom, mode, duedate) in ClassroomService
    - createAssignment(mode) in ChallengeService
  - Use Case 06.1
    - classroomReport(Classroom) in ClassroomService
    - report(Classroom) in ChallengeService
  - Use Case 07.1
    - takeAssignment() in GUI called through clicking a button which calls getAssignments(Assignment) already in ChallengeServices and assumes getAssignments() in can get one assignment
  - Use Case 08.1
    - searchUsers(emailAddress or displayName) in SchoolService
    - changePrivilege(User, privilge) in the GUI where it calls confirm() or warning() based on the privilege and then if confirmation == True, calls it through the SchoolService
   - I also assume that changePrivilege() only returns a successMessage to the GUI
  - Use Case 08.2
    - getUsers(Admin) in GUI which calls getAdminUsers() in SchoolService, it's assumed this would also work with standard users and super-admin users
  - Use Case 09.2
    - Assumes removeUsers(user) already in SchoolService can remove one user and that it returns a successMessage as well as the new UserList to the GUI to show the user has been removed from the School

## 00: User creates an account

| ID | 00.1 |
| ------ | ------ |
| Use Case | The first Super-Admin account is created for a new School |
| Sequence Diagram | ![Use_Case_00.1v2.svg](uploads/79dfe268684189b2290abb47a6604c04/Use_Case_00.1v2.svg) |


OR?

| ID | 00.1 |
| ------ | ------ |
| Use Case | The first Super-Admin account is created for a new School |
| Sequence Diagram | ![Case_00.1v2.svg](uploads/ce26a5faade7360f94fa895ff98cba02/Case_00.1v2.svg) |

| ID | 00.2 |
| ------ | ------ |
| Use Case | A new User creates an Account |
| Sequence Diagram | ![Use_Case_00.2.svg](uploads/8de5b73ddfc526421e6d6101ba0fc9ba/Use_Case_00.2.svg) |

## 01: User logs in

| ID | 01.1 |
| ------ | ------ |
| Use Case | User logs in |
| Sequence Diagram | ![Use_Case_01.1.svg](uploads/c72e3cddff453048bc336e4b174f1df1/Use_Case_01.1.svg) |

## 02: User selects the Challenge Mode

| ID | 02.1 |
| ------ | ------ |
| Use Case | User starts a Standard Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.1.svg](uploads/d02932e9a5c5f5047ff3d4be9f4d6817/Use_Case_02.1.svg) |

| ID | 02.2 |
| ------ | ------ |
| Use Case | User starts a Programmer Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.2.svg](uploads/395c95831e78ecd8fbfe0e206a401fe1/Use_Case_02.2.svg) |

| ID | 02.3 |
| ------ | ------ |
| Use Case | User starts a Dictation Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.3.svg](uploads/e0529b521887b49ae1d27555a773431d/Use_Case_02.3.svg) |


## 03 User views their typing history

| ID | 03.1 |
| ------ | ------ |
| Use Case | User views their Report |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_03.1.svg](uploads/d04f799b494be88cd31788bfd0815cce/Use_Case_03.1.svg) |


## 04: Admin manages Classrooms

| ID | 04.1 |
| ------ | ------ |
| Use Case | Admin Creates a new Classroom |
| Precondition | Admin is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_04.1.svg](uploads/de2e8879765ea7901d69ca3859f96c87/Use_Case_04.1.svg) |

| ID | 04.2 |
| ------ | ------ |
| Use Case | Admin Deletes a Classroom |
| Precondition | Admin is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_04.2.svg](uploads/0d5833a60ed9bbf638d4309432391e24/Use_Case_04.2.svg) |

| ID | 04.3 |
| ------ | ------ |
| Use Case | Admin adds a User to a Classroom |
| Precondition | Admin is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_04.3.svg](uploads/f466edd26073a94a8f6b8bb8093f939b/Use_Case_04.3.svg) |

| ID | 04.4 |
| ------ | ------ |
| Use Case | Admin Removes a User from a Classroom |
| Precondition | Admin is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_04.4.svg](uploads/d2f2c3abf7f8d2567c56fbb5fd9e5080/Use_Case_04.4.svg) |


## 05: Admin assigns typing challenges

| ID | 05.1 |
| ------ | ------ |
| Use Case | User logs in |
| Preconditions | The Admin has management of the Classroom |
| | Admin logged in and in the Manage Classrooms view |
| Sequence Diagram | ![Use_Case_05.1.svg](uploads/1b3ab722a0d63d93bbcb1e9e980936e9/Use_Case_05.1.svg) |

## 06: Admin views a Classroom Report
| ID | 06.1 |
| ------ | ------ |
| Use Case | Admin views a Classroom report |
| Preconditions | The Admin has management of the Classroom |
| | Admin logged in and in the Manage Classrooms view |
| Sequence Diagram | ![Use_Case_06.1.svg](uploads/2e05b1f22f43dd99add8866c7de467cb/Use_Case_06.1.svg) |

## 07: User takes an assigned typing challenge.
| ID | 07.1 |
| ------ | ------ |
| Use Case | User takes a typing challenge assigned to their Classroom |
| Preconditions | User is part of the Classroom "Room 203" |
| | Admin has assigned a typing challenge to the Classroom "Room 203" |
| | User is logged in |
| Sequence Diagram | ![Use_Case_07.1.svg](uploads/42af4dedf56898cf9592942b82843182/Use_Case_07.1.svg) |

## 08: Super-Admin can create and manage Admins

| ID | 08.1 |
| ------ | ------ |
| Use Case | Super-Admin makes a Standard User into an Admin User |
| Preconditions | New Admin User exists in the Super-Admin's School as a Standard User |
| | Super-Admin is logged in |
| Sequence Diagram | ![Use_Case_08.1.svg](uploads/2c06a9911020979ecfc90fcb4e25bf98/Use_Case_08.1.svg) |

| ID | 08.2 |
| ------ | ------ |
| Use Case | Super-Admin changes an Admin user into a Standard User |
| Preconditions | The Old Admin User exists as an Admin User in the Super-Admin User's School |
| Sequence Diagram | ![Use_Case_08.2.svg](uploads/ddabdd82525903b39432da22de0aa632/Use_Case_08.2.svg) |

| ID | 09.2 |
| ------ | ------ |
| Use Case | The Super-Admin removes a user from their School |
| Preconditions | The Users that the Super-Admin wants to remove must be in the Super-Admin's School |
| | Super-Admin is logged in |
| | The User is not a Super-Admin | 
| Sequence Diagram | ![Use_Case_09.2.svg](uploads/b9a6a5e9099105787d1afb494d4ef480/Use_Case_09.2.svg) |

Other:

Use Case 05.1

Version 1: ![Untitled_Diagram.svg](uploads/f47dd738ef4385d47ed99a238f51340f/Untitled_Diagram.svg)

Version 2: ![Use_Case_05.1.svg](uploads/c7b0f617a136f0e821ce9257d971950a/Use_Case_05.1.svg)

Version 3: ![Use_Case_05.1.svg](uploads/10a12fc6c2a8079afbda5d157b2f2b75/Use_Case_05.1.svg)

Version 3 Notes: I wasn't sure whether or not to return the ClassroomManagement component or ClassroomList. I also left out calls to the database.

Version 4: ![Use_Case_05.1.svg](uploads/a0c5d1e2b22274e3dadab02555bf4e9b/Use_Case_05.1.svg)

Use Case 06.1

Version 1: ![Use_Case_6.svg](uploads/8c7e84eaa80ea8ddb37afd2db3eef932/Use_Case_6.svg)

Version 2: ![Use_Case_06.1.svg](uploads/87819c5775896f83a532529b061409fa/Use_Case_06.1.svg)

Version 3: ![Use_Case_06.1.svg](uploads/54ce9552b00b87888d780f0ce720518d/Use_Case_06.1.svg)

Use Case 07.1

Version 1: ![Use_Case_7.svg](uploads/c65ab31876a039ec4b8482f9ebd40383/Use_Case_7.svg)

Version 2: ![Use_Case_7_1.svg](uploads/4d85d88de5228b9f520b1179b6273ad1/Use_Case_7_1.svg)

Version 3: ![Use_Case_07.1.svg](uploads/85ddc0407b9a24780ff2f2ed1198d358/Use_Case_07.1.svg)

Version 4: ![Use_Case_07.1.svg](uploads/150145d5dfd0c40c7488bab8156c9a21/Use_Case_07.1.svg)

Use Case 08.1

Version 1: ![Use_Case_08.1.svg](uploads/05462aed4f58a5739056a3d6496573ae/Use_Case_08.1.svg)

Use Case 08.2

Version 1: ![Use_Case_08.2.svg](uploads/1e429d5c49c59356fcf6fafe62c94ed3/Use_Case_08.2.svg)

Use Case 09.2:

Version 1: ![Use_Case_09.2.svg](uploads/7d0f6732189949a4aaeb04790af2e19b/Use_Case_09.2.svg)
