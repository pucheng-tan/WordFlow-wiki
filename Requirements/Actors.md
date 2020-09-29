# Actors
A description of important tasks that an actor is able to complete is followed by an example persona when applicable.

## Standard User
- a user who is able to complete typing challenges
- may view their own typing progress through stored user metrics
- interact with user group(s)
- interacts with Firebase SDK (user will create a username and password for authentication)
*Tom is a high school student with an interest in programming. He would like to be faster and make fewer errors when he is writing Java code.*
*Mary is a college student with plans to become a court stenographer. She would like to be able to type things as she hears them.*

## Administrative User
- a user who can manage other users, including creating them, and view their typing progress
- manage user groups
- may assign typing challenges to standard users or user groups
- also can do everything that a standard user is able to do
*Naomi is a middle school teacher tasked with teaching students touch-typing. She wants to give typing assignments to the entire class and find out who needs additional instruction. To demonstrate, she completes a typing challenge herself. When a new student is added to the class, Naomi needs to add them herself instead because the Principal is too busy*

## Super Administrative User
- manage Administrators
   - create groups and assign an administrator to manage the group
   - add and remove administrators
- also can do everything that a standard user and administrator can do
*Sam is the dean of technology at a post-secondary institution. Sam needs to be able to create administrator accounts for instructors and pull reports to track student progress. Sam also wants to improve their typing skills.*
*Anja is a high school principal. She wants to create accounts for instructors and leave the rest up to them.*

## Firebase SDK
- interacts with our software through API calls
- manages user authentication, user permissions/user groups, store user data in cloud database, store user data

## Other APIs possibly!
//TODO: decide on the format for our tests (this will narrow down our choice in text fetching APIs)
