This is a page for:

● System Architecture Details

○ Long-form written description of your selected system architecture, which  includes clear, precise, and complete descriptions of ​each piece​ of your system

from Milestone 2: Design document.

# System Architecture Details
(Each of these paragraphs are rough drafts, feel free to edit them)

- intro paragraph

Our software will involve the presence of three different architectural styles. The first architecture style we will use is the blackboard architecture style. We will use this style during typing challenge runtime, and for interacting with a central database. The second architecture style we will use is the object-oriented style. We can use this style for creating different types of users with similar functionality. The third and final architecture style we will use is pipelines and filters. This style is known to work notoriously well with python, and we can make use of it by joining together the different sections of our user interface.

- paragraph for pipes and filters style

Using pipes and filters, we can create a general flow through different sections of our software. Starting at the authentication, we can collect the user's ID which would give us information on the user type. This info will be piped to the main menu, where we can choose which data to display based on the user's group. Next, as the user goes through the UI, data will be selected and sent through each stage. When the user starts a test, the test will need to be provided with text. This data can be provided through a pipeline, and the test can be seen as a filter that manipulates and displays data. We chose to use pipelines and filters to create a simple flow through our software that connects each piece of UI. The pipes and filters architecture also works well with python, making it a simple and easy choice.

Here is a diagram outlining the simple flow through our program using pipes and filters. Credit goes to Pucheng Tan.

![draft.svg](uploads/6fc2b551bd084990f24b9476fc54d4d0/draft.svg)

- paragraph for OOP style

For our system architecture style, one of the styles chosen was the object-oriented style. The reason for this is that our typing tool involves various real world entities. The object model then allowed us to clarify these entities into different objects, such as the different types of users, Classrooms, and Schools. Using these as components in a system, the connectors then are their operations with each other through function and procedure calls. This made sense with our requirements because there is a clear determination on what objects the user interface should interact with and there are requirements that could naturally be stated as a problem of agents interacting. For example, from an administrative user interface, administrative users should be able to add and remove students from Classrooms, so it is clear they should interact with the objects of standard users and Classrooms.

- paragraph for blackboard style- typing challenge

To manage the typing challenges, a blackboard style was chosen. It made sense to represent the typing challenge as a central element showing the current state with various agents connected to it since the typing challenge's state would continue to change as the user progresses through it and when it does so, it should notify its agents which in this case consist of the display and the administrative users. Another style that was considered for this was an event-based style which also made sense as the typing challenge would announce events to the broadcast medium which the agents then could listen for. However, a blackboard style was chosen as it also seemed a suitable choice and as we are using Python, seemed more in tune with it and there was also more past experience with blackboard style.


- blackboard style- database
For using and manipulating a database, we will follow a blackboard architecture style again. Using blackboard/repository architecture, the database itself represents the blackboard/current state, with independent individual users interacting, sending data to, and requesting data. The interactions between the users and the blackboard take place through API calls to the Firebase SDK. We chose blackboard style architecture for saving data in a database because it allowed us to have many different interactions asynchronously between a central database and the different users.

Here is an example diagram:
![IMG_7A0D8A1B128B-1](uploads/9e59a0f0b1c18a593a058afc764f178e/IMG_7A0D8A1B128B-1.jpeg)


- paragraph for why we didn't choose layered, interpreter, and event-base style here (?)