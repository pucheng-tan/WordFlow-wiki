This is a page for updated sequence diagrams.

## 08: Super-Admin can create and manage Admins

Use cases 08.1, 08.2, and 08.3 begin with the Super-Admin selecting User Management generating a list of Users as depicted below before branching off:

| ID | 08.1 and 08.2 and 08.3 |
| ------ | ------ |
| Step | Super-Admin clicks on User Management |
| Sequence Diagram | ![Use_Case_Step_1.svg](uploads/734542d092d89d95e4abc75a16a427e1/Use_Case_Step_1.svg) |

| ID | 08.1 |
| ------ | ------ |
| Use Case | Super-Admin makes a Standard User into an Admin User |
| Preconditions | New Admin User exists in the Super-Admin's School as a Standard User |
| | Super-Admin is logged in |
| Sequence Diagram | ![Use_Case_08.1.svg](uploads/9330ddc1567ee2e514aab2e71c41efbe/Use_Case_08.1.svg) |

| ID | 08.2 |
| ------ | ------ |
| Use Case | Super-Admin changes an Admin user into a Standard User |
| Preconditions | The Old Admin User exists as an Admin User in the Super-Admin User's School |
| Sequence Diagram | ![Use_Case_08.2.svg](uploads/be68cb6b61960db19055ba840b3a2d00/Use_Case_08.2.svg) |