# GitLab Usage
Goal: The features of GitLab should be leveraged to get as much out of the service as possible. Other users should be able to view changes made in GitLab and understand them easily.
- All tasks should be created as Issues on GitLab, including features, bugs, and non-programming tasks.
- Assign the appropriate tags to issues, to organize what type of issue it is, and its progress.
- Issues should be updated with comments where appropriate (ie: it is not necessary to duplicate a commit message into the comments section of an issue)
- Issues should be Closed when they are completed.
- When possible, a branch should be created from the issue to link them together.
- Branches should have a descriptive name.
- Commits should have descriptive messages, indicating what was done, why, and if applicable, any known problems that exist with it.
- Work should never be completed from the master branch. 
- Branches should be checked out by only one user at a time. If multiple people must work on the same branch, they should coordinate such that one user commits to the branch before the other user pulls from the branch and begins work on it.
- Before submitting a Merge Request for programming work, the master branch should be pulled and merged into the working branch, all functionality should be tested, and any prior tests must continue to pass.
- Before merging a branch into master, a Merge Request should be reviewed by another teammate

## GitLab Guide
All git commands should be executed in the repository folder on your computer (it will have a .git folder)
### Switching to a new branch
This will switch you to branch_name branch and pull the data from the repository
- git checkout branch_name
- git pull

### Committing Changes to the branch
Files must be staged before they are committed.
- git status //see the files that have been changed
- git add -A //this will stage ALL files displayed in git status, OR:
- git add file_name.py //this will stage a single file at a time
- git commit -m "A message saying what was done before committing" //we are being judged on commit messages. Say what you did, it is never too long.
- git push // this will send the changes up to the repository

### Merging Changes from another branch to yours
Usually you want to merge master into your branch before merging to master, or maybe another teammate wrote some code on their branch that you need. Before merging another branch into yours, commit your branch.
- git checkout other_branch
- git pull // get the changes from that branch onto your computer
- git checkout my_branch
- git merge other_branch
- Here is where you fix any merge conflicts. Somewhere it asks for a message but I forget where.
- git push

### Fixing Merge Conflicts
https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts

Merge conflicts happen when two branches both made changes to the same part of the code. 
Let's say that master branch has a file main.py that is made up of an import statement and the line "num = 10." Then, branch_one and branch_two are made. branch_one changes the line to "num = 1", and branch_two changes the line to "num = 2." branch_one is merged into master. When branch_two is being merged into master, they will get a merge conflict.

After attempting to merge, the code on branch_two will look like:

```python
from x import y

<<<<<< HEAD
num = 1
==========
num = 2
<<<<<< branch_two
```

The conflicting code from master is marked with <<<<< HEAD, and the conflicting code from your branch will say your branch name below it. You can use a search function on your editor to find the conflicts if you need to. You need to decide here what the line should be so that everyone's code works, and get rid of the <<<< HEAD and ==== stuff. Once you are done that, you can push it. If there are tests, they should be run here.

### Git Ignore
Code editors make a bunch of config files that nobody else needs. Or maybe you have log files that don't need to be shared. Any files and folders that are in the repository folder but shouldn't be committed should be put in the .gitignore. It is hard to ignore a file once it has already been committed, because now it is a tracked file, so try not to do that.

1. In the project repository (folder with .git), make a text file called .gitignore. Open the file
2. To ignore a folder, in this case __pycache__, put __pycache__/ in the file. 
3. To add another folder, in this case .pytest_cache, add .pytest_cache on a new line.
4. The gitignore can use a variety of different patterns. A list is here: https://www.atlassian.com/git/tutorials/saving-changes/gitignore
5. Save the file. When you go to commit, you will also commit the .gitignore file. Now it will ignore everyone's pycache once your .gitignore is in master!

### Oh no everything is broken!
Either:
- stash it: for things like "x was working on the branch, I was also working on the branch doing experiments. Now I can't get x's changes!"
  - git stash 
    - sends your code changes away to somewhere you don't care about (but can actually be accessed with git stash apply) so now you can go back to your normal branch
- nuclear option: when you are just done
  - move your code somewhere else, 
  - delete your repository, 
  - clone it again, 
  - make and checkout a new branch
  - put your code back in the repository
  - continue

# Working Outside of GitLab
Goal: Any work completed outside of the GitLab repository should be easily accessible to all team members.
(Some work is not possible to complete directly on GitLab. All programming and Wiki contributions should be completed directly on GitLab.)
- All team members should be able to view the work.
- All team members should be able to edit the work.

# Testing
Goal: Testing should be consistent, reliable, and cover everything important.
- Tests should be independent from each other.
- Test results should not change depending on which machine it is running on.
- Tests should avoid hitting our APIs too much and eating all of the bandwidth.
- Tests that must modify any database values should revert all changes regardless of whether the test passes or fails. These tests should be avoided in general.
- Specific directions should be written for manual tests that can be followed by a lay person, outlining every action and expected result for the test.
 
# Development Environment
Goal: It should be easy for changes in the development environment to be replicated by all team members.
- //TODO: figure out package management, and then write a process for adding (or removing) a package so everything runs nice for everyone

# Documentation
Goal: Documentation should be completed while new changes are still fresh in your mind. Documentation should not have  a backlog that needs to be "caught up" 
- When completing work on a feature or modifying an existing one, instructions should be included in the User Manual
- If completing work that modifies the product installation process, the README file should be updated in the branch.

# Meetings
Goal: Meetings should be organized and documented. All team members should be encouraged to contribute.
- A meeting Chair and a meeting Secretary will be appointed for each meeting. 
- These roles will be the same for the Thursday meeting and the following Tuesday meeting.
- The Chair is responsible for creating a meeting Agenda, and distributing the agenda in the Discord channel no less than 6 hours before the start of the meeting
- The Chair is responsible for keeping the meeting on-track (following the agenda, ending the meeting on time) and encouraging input from all attendees.
- The Secretary is responsible for tracking any new Action Items that need to be completed, creating Issues in GitLab for them, and assigning a person responsible and due date whenever possible
- The Secretary is responsible for recording any decisions that have been made, any changes to the agenda that occurred, and editing the appropriate meeting page on the  GitLab Wiki with these details.
- All team members are responsible for making sure that they have a task assigned to them such that they are able to contribute to the project.
- All team members are responsible for making sure that they understand what a task entails.
- Informal meetings are conducted on Thursdays at 4:30 pm, but may be moved if too many schedules conflict.
- If unable to attend a meeting, a team member is responsible for informing the rest of the team as soon as possible. They should review meeting notes and ask any questions they have after the meeting to catch up.

# Changes to Process
Goal: Processes that are ineffective or unnecessarily difficult should be changed. Processes that are disorganized or shoddy should have new processes. Processes should be understood by all team members
- If a team member wishes to change a process, they should @everyone in the Discord channel, and a decision will be reached by popular consensus.
- When a process is changed, this Wiki page should be modified to reflect the change.
- Any team members who were not available to discuss the change should be @-ed on Discord to bring the change to their attention.

# Suggestions

## Communication: 
Stand up meetings!
- Every day: 

      - Every person:

            1. "This is what I did"

            2. "This is what I am going to do"

            3. "This is what is getting in my way"

## To do:
- Issues on Gitlab
- How to review things by the whole group?
  - Comment on the GitLab issue either with your suggestions or your approval?
