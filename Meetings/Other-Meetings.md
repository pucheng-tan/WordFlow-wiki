# **Meetings Tracker**

## **Meeting 1**

Time: 3:30p.m.-3:45p.m. (15 minutes) via Discord

Date: 2020/09/04

## Meeting Notes
-Short introductions and expectations

## Outcomes
-None


## **Meeting 2**

Time: 3:30p.m.-4:00p.m. (30 minutes) via Discord

Date: 2020/09/22

## Meeting Notes
-Short introductions

-Explained what we're making

-Python module: requests, can import it, use to take in code snippets from the API 

## Outcomes
-Try to find APIs with song lyrics or book excerpts

-Weekly meetings on Thursday @ 11:00a.m. or 12:00p.m. (tentative time)

-Action items due by next one, so set on Tuesday, due on Thursday (general rule)

## **Meeting 3**

Time: 4:15p.m.-4:30p.m. (15 minutes) via Discord

Date: 2020/09/22

## Meeting Notes

-Meeting after tutorial meeting

## Outcomes
-Look for APIs -Everbody

-Next chair: Tara Epp

-Next secretary: Pucheng Tan

-Next Meeting: 2020/09/24 @ 4:30p.m. via Discord

## **Meeting 4**

Time: 4:30p.m.-4:45p.m. (15 minutes) via Discord

Date: 2020/09/24

## Agenda
1. Go over instructor feedback on project scope
   1. Talk about user management in the system
   2. Talk about typing from audio
2. Adjust features in must/should/could haves
3. Go over API research
4. Talk about actors and use cases
5. Talk about other requirements (performance, permissions

## Meeting Notes

Action Items:
- Tara and Cameron test PoC for Firebase/Python
- Use cases (Abdul)
   - descriptions need to be updated
   - everything needs fleshing out
   - turned into a diagram (Pucheng)
- troubleshoot Abdul's google access //DONE
- non-functional requirements (Sarah)
- look for API things (Yuta)
- product description (day before handing in)
- mock-ups (Pucheng)
- review language at end to make sure everything is consistent

## Outcomes
- maybe just use firebase API for API requirement?
   - dictionary of words for standard mode
   - text-to-speech for dictation?
- fetch text from twitter API?

-Next chair: Tara Epp

-Next secretary: Pucheng Tan

-Next Meeting: 2020/09/29 @ 4:00p.m. via Discord

## **Meeting 5**

Time: 4:00p.m.-4:43p.m. (43 minutes) via Discord

Date: 2020/10/01

## Agenda
None 

## Meeting Notes
Q: Will the content be on the server side or are we storing the text? 

A: A mix of API and files.

Q: How to roll out updates on text files?

A: Could store text content on Firebase or store text on actual computer and update application to update text.

If you want to add a use case, there is a template at the bottom of Use Case Scenarios.

## Outcomes
Actors
1. The only API we are using is Firebase API.

Functional Requirements
1. The leaderboard is confirmed to be a should have for administrative users.
2. The assign standard users typing challenges is now a must have for administrative users.

Use Case Scenarios
1. We are removing no use cases. We changed “look at results” in use case 05 to “look at reports”.

## Action Items
- Think about design for next meeting

## **Meeting 6**

Time: 4:00p.m. via Discord

Date: 2020/10/07

## Agenda
1. Go over everything done thus far.
2. Finalize various things.
   1. How the components for Milestone 2: Design will be grouped together.
   2. The choice of architectural style.
   3. Who will be working on each component.
3. Decide what to have done by next Tuesday's meeting.

## Meeting Notes

-We chose a mixture of blackboard architecture (databases and test state), with object-oriented to handle users, and pipeline to connect everything
-We will use blackboard architecture during a test (keap track of state)



## Outcomes

## Action Items
1. Make a page in the Wiki for each component of Milestone 2: Design.

-storyboarding -Tara
-domain modeling -revise what we have
-paragraph description of our architecture

Pucheng - component diagrams - possibly finding GUI library
-how we are gonna handle progress

-sequence diagrams

## **Meeting 7**

Time: 4:00p.m. via Discord

Date: 2020/10/15

## Agenda
1. Review Domain models and vote for the final decision
2. Review system Architecture design
3. Review UML component diagrams
4. Review data structure
4. Go over the rest deliverables of milestone2 (sequence diagrams and so on)
5. Assign work for the weekend

## Meeting Notes & Outcomes
- Use Layered architecture to separate GUI, Logic, Data Interface, and Data
   - Connect with pipes and filters?
   - Use blackboard conceptualization for typing challenge
- component diagram will have to be updated to follow domain model
- Admins will no longer manage individual users (classrooms only), no adding users, no removing users
- Should users be able to play as a guest or outside of a school structure? This could be a Could Have. Current structure does not allow for it

## Action Items
1. Complete Domain Model (Tara, Cameron when done with System Architecture)
2. Complete Component Diagram (Pucheng)
3. System Architecture (Cameron)
4. Interaction Diagrams (Sarah, Abdul)
5. Persistent Storage Details (Tara will make diagram from test JSON content)
6. Review work for clarity (Yuta will see if things make sense)
7. Create list of modules organized by system layer (Cameron)
8. The calculation for WPM should be clarified (Tara? Anyone really)

- A "good" draft should be done of all items by Saturday night/Sunday noon to leave time for review and polishing

## **Meeting 8**

Time: 4:00p.m. via Discord

Date: 2020/11/5

## Agenda
1. Update on GUI
2. Update on API
3. Yuta?

## Meeting Notes & Outcomes


## Action Items
1.

## **Meeting 9**

Time: 3:15p.m.-4:15p.m. via Discord

Date: 2020/11/16

## Agenda
1. Demonstration of potential GUI structures

## Meeting Notes & Outcomes
- today we went over what everyone is working on


Sarah - working on log in screen
      - showed a nice looking working version

Cameron - working on main menu plus other windows
        - nothing to show


Pucheng - really busy with 332, will start on the weekend

Tara - organization of issues
     - hardcoding contexManager
     - at log in, you instantiate a contextService, when communicating with with firebase, ask for user key from 

Abdul - working with Tara

## Action Items
1. Make a complete version of basic structure for the GUI to potentially be able to merge with master.

## **Meeting 10**

Time: 7:10p.m.-:p.m. via Discord

Date: 2020/11/26

## Agenda

## Meeting Notes & Outcomes

## Action Items

[Markdown cheat sheet](https://support.squarespace.com/hc/en-us/articles/206543587-Markdown-cheat-sheet "Title") (for anyone editing this).
