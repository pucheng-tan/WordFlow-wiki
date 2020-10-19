# Sequence Diagrams

Notes that should probably be left:
- Often in the sequence diagrams, calls can be seen going from the ActiveWindow to a Management component to a Service. This is meant to illustrate the interaction between the different layers in our architecture style. It starts with the ActiveWindow, representing the GUI, which takes in requests and parameters from the User. The logic layer then actually does the computation to fulfill the request which uses a Service to get data from or write data to our Database when necessary.
- However, the calls the Services would make to the Database are not pictured in the sequence diagrams for brevity. Instead, it is assumed the Services would call the appropriate methods which would then make the appropriate changes to the Database.

## 00: User creates an account

| ID | 00.1 |
| ------ | ------ |
| Use Case | The first Super-Admin account is created for a new School |
| Precondition | Program is launched and on logIn page |
| Sequence Diagram | ![Use_Case_00.1.svg](uploads/94583daea8bc0e02121c016e47fb903e/Use_Case_00.1.svg) |

| ID | 00.2 |
| ------ | ------ |
| Use Case | A new User creates an Account |
| Precondition | Program is launched and on logIn page |
| Sequence Diagram | ![Use_Case_00.2.svg](uploads/17159c7688f46b495e006277c834ea7a/Use_Case_00.2.svg) |

## 01: User logs in

| ID | 01.1 |
| ------ | ------ |
| Use Case | User logs in |
| Precondition | Program is launched and on logIn page |
| Sequence Diagram | ![Use_Case_01.1.svg](uploads/59be366f9bf0e0292f759bb271ca2c82/Use_Case_01.1.svg) |

## 02: User selects the Challenge Mode

| ID | 02.1 |
| ------ | ------ |
| Use Case | User starts a Standard Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.1v2.svg](uploads/f9e633dd5e4a445f123573316d09227f/Use_Case_02.1v2.svg) |

| ID | 02.2 |
| ------ | ------ |
| Use Case | User starts a Programmer Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.2.svg](uploads/bae39c1e4948f91c9a94f12774fe65c5/Use_Case_02.2.svg) |

| ID | 02.3 |
| ------ | ------ |
| Use Case | User starts a Dictation Challenge |
| Precondition | User is Logged in and in the Main menu |
| Sequence Diagram | ![Use_Case_02.3.svg](uploads/ac4ca029d9a35a80e73f0843229bc77b/Use_Case_02.3.svg) |


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


## 05: Admin assigns typing challenges and 06: Admin views a Classroom Report

Use cases 05.1 and 06.1 begin with the Admin selecting the Classroom as depicted below before branching off:

| ID | 05.1 and 06.1 |
| ------ | ------ |
| Step | Admin selects a Classroom |
| Sequence Diagram | ![Use_Cases_5-6_Step_1.svg](uploads/a67614fccf09d49c58a3dc324f04e8b4/Use_Cases_5-6_Step_1.svg) |

| ID | 05.1 |
| ------ | ------ |
| Use Case | Admin assigns a typing challenge to a Classroom |
| Preconditions | The Admin has management of the Classroom |
| | Admin logged in and in the Manage Classrooms view |
| Sequence Diagram | ![Use_Case_05.1.svg](uploads/63758cb26d744808e4d76c975441eb15/Use_Case_05.1.svg) |

| ID | 06.1 |
| ------ | ------ |
| Use Case | Admin views a Classroom report |
| Preconditions | The Admin has management of the Classroom |
| | Admin logged in and in the Manage Classrooms view |
| Sequence Diagram | ![Use_Case_06.1.svg](uploads/3956c41d20edfe04707849b6fa003d2c/Use_Case_06.1.svg) |

## 07: User takes an assigned typing challenge.
| ID | 07.1 |
| ------ | ------ |
| Use Case | User takes a typing challenge assigned to their Classroom |
| Preconditions | User is part of the Classroom "Room 203" |
| | Admin has assigned a typing challenge to the Classroom "Room 203" |
| | User is logged in |
| Sequence Diagram | ![Use_Case_07.1.svg](uploads/d21940a90123cc2bf78afe9cf0a86678/Use_Case_07.1.svg) |

## 08: Super-Admin can create and manage Admins

Use cases 08.1, 08.2, and 08.3 begin with the Super-Admin selecting User Management generating a list of Users as depicted below before branching off:

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on User Management |
| Sequence Diagram | ![Use_Case_Step_1.svg](uploads/7ecab53a0cc95222de17818a13f05e01/Use_Case_Step_1.svg) |

| ID | 08.1 |
| ------ | ------ |
| Use Case | Super-Admin makes a Standard User into an Admin User |
| Preconditions | New Admin User exists in the Super-Admin's School as a Standard User |
| | Super-Admin is logged in |
| Sequence Diagram | ![Use_Case_08.1.svg](uploads/f01718078760cdf788487d0be5224ec2/Use_Case_08.1.svg) |

| ID | 08.2 |
| ------ | ------ |
| Use Case | Super-Admin changes an Admin user into a Standard User |
| Preconditions | The Old Admin User exists as an Admin User in the Super-Admin User's School |
| Sequence Diagram | ![Use_Case_08.2.svg](uploads/49150995cd6c59e79eb54e8bb628fd69/Use_Case_08.2.svg) |

| ID | 09.2 |
| ------ | ------ |
| Use Case | The Super-Admin removes a user from their School |
| Preconditions | The Users that the Super-Admin wants to remove must be in the Super-Admin's School |
| | Super-Admin is logged in |
| | The User is not a Super-Admin | 
| Sequence Diagram | ![Use_Case_09.2.svg](uploads/6dc629b2146e6c7ba388e3874c81c043/Use_Case_09.2.svg) |
