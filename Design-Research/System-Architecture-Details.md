This is a page for:

● System Architecture Details

○ Long-form written description of your selected system architecture, which  includes clear,precise, and complete descriptions of ​each piece​ of your system

from the Milestone 2: Design document.

# System Architecture Details

- intro paragraph

- paragraph for pipes and filters style

- paragraph for OOP style

For our system architecture style, one of the styles chosen was the object-oriented style. The reason for this is that our typing tool involves various real world entities. The object model then allowed us to clarify these entities into different objects, such as the different types of users, Classrooms, and Schools. Using these as components in a system, the connectors then are their operations with each other through function and procedure calls. This made sense with our requirements because there is a clear determination on what objects the user interface should interact with and there are requirements that could naturally be stated as a problem of agents interacting. For example, from an administrative user interface, administrative users should be able to add and remove students from Classrooms, so it is clear they should interact with the objects of standard users and Classrooms.

- paragraph for blackboard style- database/typing challenge

To manage the typing challenges, a blackboard style was chosen. It made sense to represent the typing challenge as a central element showing the current state with various agents connected to it since the typing challenge's state would continue to change as the user progresses through it and when it does so, it should notify its agents. Another style that was considered for this was an event-based style which also made sense as the typing challenge would announce events to the broadcast medium which the agents then could listen for. However, a blackboard style was chosen as it also seemed a suitable choice and as we are using Python, seemed more in tune with it and there was also more past experience with blackboard style.

- paragraph for why we didn't choose layered, interpreter, and event-base style here (?)