# Actors
A description of important tasks that an actor is able to complete is followed by an example persona when applicable.

## Standard User
- a user who is able to complete typing challenges
- may view their own typing progress through stored user metrics
- interact with user group(s)
- interacts with Firebase SDK (user will create a username and password for authentication, typing history is stored in the database)
- standard users can belong to Schools, and Classrooms within Schools.

*Tom is a high school student with an interest in programming. He would like to be faster and make fewer errors when he is writing Java code.*

*Mary is a college student with plans to become a court stenographer. She would like to be able to type things as she hears them.*

## Administrative User
- all of the functionality of the standard user is available to the Admin user
- a user who can manage other users, including creating them, and view reports on their typing progress
- manage Classrooms within Schools
- may assign typing challenges to standard users or Classrooms.
- also can do everything that a standard user is able to do
- admins are created by super administrators and belong to their creator's School.

*Naomi is a middle school teacher tasked with teaching students touch-typing. She wants to give typing assignments to the entire class and use reports to find out who needs additional instruction. To demonstrate, she completes a typing challenge herself.*

## Super Administrative User
- all of the functionality that is available to the standard user or the admin user is also available to the super-admin user
- manage Administrators
   - create Classrooms and assign an administrator to manage them
   - add and remove administrators
- manage their School
  - a School can have one or more super admins
  - super admins can invite users and remove users from a School
  - super admins can change the user privilege level of standard and admin users.

*Sam is the dean of technology at a post-secondary institution. Sam needs to be able to create administrator accounts for instructors and pull reports to track student progress. Sam also wants to improve their typing skills.*

*Anja is a high school principal. She wants to create super-admin accounts for the IT staff and leave the rest of the management up to them*

## Firebase SDK
- interacts with our software through API calls
- manages user authentication, 
- manages user permissions and profiles
- stores users' typing data

## Other APIs possibly!
//TODO: decide on the format for our tests (this will narrow down our choice in text fetching APIs)
