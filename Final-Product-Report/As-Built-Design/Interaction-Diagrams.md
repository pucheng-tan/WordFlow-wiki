This is a page for updated sequence diagrams.

Notes:
- Often in the sequence diagrams, calls can be seen going from the ActiveWindow to a Management component to a Service. This is meant to illustrate the interaction between the different layers in our architecture style. It starts with the ActiveWindow, representing the GUI, which takes in requests and parameters from the User. The logic layer requests data from the API services, performs calculations, and sends save data back to the API services. The API Services are all based on the apiService abstract module, which performs get and post HTTP requests to the Firebase API.
- However, the calls the Services would make to the Database are not pictured in the sequence diagrams for brevity. Instead, it is assumed the Services would call the appropriate methods which would then make the appropriate changes to the Database.
- Any sequence diagrams for user cases not listed were either not updated or not implemented.

## 08: Super-Admin can create and manage Admins

Use cases 08.1, 08.2, and 08.3 begin with the Super-Admin selecting User Management generating a list of Users and then selected the desired user as depicted in the two sequence diagrams below before branching off:

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on User Management |
| Differences | 1. The user interacts with GUI instead of ActiveWindow. This is because when a user clicks the User Management button, the button is part of the main menu which is part of the GUI. The user doesn't actually click on the ActiveWindow to get to a new ActiveWindow.|
| Differences | 2. To get the users of a given privilege level, the UserManagementWindow actually communicates with SchoolManagement instead of UserManagement. This is because getting all the users of a given privilege level at a School involves the entire School while UserManagement deals more with individual user tasks. As a result, UserService also becomes SchoolService. |
| Updated Sequence Diagram | ![share_use_case_8.svg](uploads/d3cfcc81090d929e772866a93794dd2e/share_use_case_8.svg) |

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on a tab, clicks on a user, and clicks View User |
| Differences | 1. To get users of a certain privilege, rather than searching, the super-admin can select one of the tabs to get them all. This was done as it was more convenient to make three different tabs for users than having to search for them. |
| Differences | 2. It is the same logic for selecting users. It is easier to have the user select one than searching by display name or email. |
| Differences | 3. Instead of displaying the user directly on the UserManagement window, it was easier to open to a new window. That way, none of the widgets on the UserManagement window need to be cleared. It also allowed for consistency with the UserManagement storyboards. |
| Updated Sequence Diagram | ![view_user_8.svg](uploads/796e75014c623e9b3cff59cb40f9f61d/view_user_8.svg) |

| ID | 08.1 |
| ------ | ------ |
| Use Case | Super-Admin makes a Standard User into an Admin User |
| Preconditions | New Admin User exists in the Super-Admin's School as a Standard User |
| | Super-Admin is logged in |
| Differences | 1. Super-admin users get a confirmation box as well, because it flowed more consistently to have only a warning for changing a user's privilege level to super-admin and asking for confirmation to change the privilege for all privilege levels. |
| Differences| 2. Updating the profile actually didn't need the display name but the user id. |
| Updated Sequence Diagram | ![use_case_08.1.svg](uploads/9ebb7d2f7e2a13e5031150234028f94f/use_case_08.1.svg) |

| ID | 08.2 |
| ------ | ------ |
| Use Case | Super-Admin changes an Admin user into a Standard User |
| Preconditions | The Old Admin User exists as an Admin User in the Super-Admin User's School |
| Updated Sequence Diagram | ![use_case_08.2.svg](uploads/a39e9f11911fa11d0bc4e6808c68fce0/use_case_08.2.svg) |