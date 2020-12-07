This is a page for updated sequence diagrams.

## 08: Super-Admin can create and manage Admins

Use cases 08.1, 08.2, and 08.3 begin with the Super-Admin selecting User Management generating a list of Users and then selected the desired user as depicted in the two sequence diagrams below before branching off:

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on User Management |
| Sequence Diagram | ![share_use_case_8.svg](uploads/d3cfcc81090d929e772866a93794dd2e/share_use_case_8.svg) |

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on a tab, clicks on a user, and clicks View User |
| Sequence Diagram | ![view_user_8.svg](uploads/796e75014c623e9b3cff59cb40f9f61d/view_user_8.svg) |

| ID | 08.1 |
| ------ | ------ |
| Use Case | Super-Admin makes a Standard User into an Admin User |
| Preconditions | New Admin User exists in the Super-Admin's School as a Standard User |
| | Super-Admin is logged in |
| Sequence Diagram | ![use_case_08.1.svg](uploads/9ebb7d2f7e2a13e5031150234028f94f/use_case_08.1.svg) |

| ID | 08.2 |
| ------ | ------ |
| Use Case | Super-Admin changes an Admin user into a Standard User |
| Preconditions | The Old Admin User exists as an Admin User in the Super-Admin User's School |
| Sequence Diagram | ![use_case_08.2.svg](uploads/d4e66769d9da659f1828447d912ed46b/use_case_08.2.svg) |