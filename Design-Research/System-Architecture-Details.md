This is a page for:

● System Architecture Details

○ Long-form written description of your selected system architecture, which  includes clear, precise, and complete descriptions of ​each piece​ of your system

○ UML component diagram(s) ensuring:

■ Identification of all major components

■ Packages and nested components included (if necessary)

■ Associations between components outlined

from Milestone 2: Design document.

# System Architecture Details
(Each of these paragraphs are rough drafts, feel free to edit them)

- intro paragraph

Our software will involve the presence of three different architectural styles. The first architecture style we will use is the blackboard architecture style. We will use this style during typing challenge runtime, and for interacting with a central database. The second architecture style we will use is the object-oriented style. We can use this style for creating different types of users with similar functionality. The third and final architecture style we will use is pipelines and filters. This style is known to work notoriously well with python, and we can make use of it by joining together the different sections of our user interface.

IMPORTANT NOTE: We have split up the different architectures we will be using into primary and secondary architectures. The primary architecture we will use is used throughout our system and is crucial when looking at the big picture of our system. The secondary architectures that we will use are only used in certain modules and interactions in smaller portions throughout our system. They are all connected through the primary architecture.

## Primary Architecture

### Layered Architecture - entire system

The main architecture style we will be using is the layered architecture style. We will do this by creating four layers.

These layers are:
1. Layer 1 - User layer
2. Layer 2 - Logic layer
3. Layer 3 - Data layer
4. Layer 4 - Remote Database

The highest layer (layer 1) or the user layer will be composed of the modules that we need in order to create our user interface. This includes a module that will load our main menu, the typing challenge view, and the different management views. During authentication, the user who is being authenticated will receive a key in their requested user json file. This key will let the user interface know which different views to unlock, and which modules to load from the second layer. For example, if the user receives a key that gives super administrator permissions, the user interface will unlock a domain management tab, as well as load a domain management module (from the second layer).

The second layer (layer 2), also known as the logic layer, will interact with the user interface, as well as the third layer. This layer is used to hold all the modules and methods that are needed to fully implement our use cases. The user layer will make a request to this layer when something needs to be done (i.e add a user to a group) by loading the module that is needed, and using the proper method. The idea is that this will break up the user interface and the needed functionality of our program in a way that allows us to finish the user interface without knowing how the back end works. For example, a super admin wants to manage a domain. When they click the domain management tab, a domain management module will be loaded. This will have all the high-level methods needed in order for the super admin to manage a domain. When the super admin clicks the add user button, this will use the addUser method from the domain management module, which may or may not be implemented yet. The UI layer does not need to know how to add a user, it just needs to give the proper arguments. Any sort of calculations or data manipulation will most likely take place in this layer.

The third layer (layer 3), or the Data layer, will interact with interact with the methods in the logic layer, while making API requests to the database (the fourth layer). This is the only layer that actually interacts and knows about the database. This layer will be composed of lower-level methods that encompass every single interaction we will need to make with the database. The logic layer will request data from this layer when it needs some sort of information, and it will send data to this layer when it needs to store data, all without knowing about the database. This layer is necessary in order to hide all of the code that interacts with the Firebase API.

The last layer (layer 4) is composed of the database we will use to store user data. This is currently firebase, and the communication between layer 3 and 4 takes place through API calls.

Using a layered architecture approach, each layer is only allowed to communicate with the layers above and below it. This means that layers 1 and 2 know nothing about the database, and layer 3 knows nothing about the UI. If we were to change our API, in practice we would not need to change the top two layers. This is a huge plus of the layered architecture approach.

Here are some simple diagrams to help visualize our use of this architecture:

![File_001](uploads/115c32f326676548b77ddf39580432d7/File_001.png)

![File_001__1_](uploads/3a3b81b6bfc894c8461694e80e1d5f1c/File_001__1_.png)

![layered](uploads/fc7143db35e0d91ee8f971c459c00341/layered.svg)

## Secondary Architectures

### Blackboard Architecture - at typing challenge runtime

During the runtime of typing challenges, we will use blackboard style architecture. We chose the blackboard style because it made sense to represent the typing challenge as the main element, with the current state held in a python list. We can display the current state, as well as the entire test, and any errors that are made. As the current state updates, it can update other components, such as the display, and possibly an on-screen keyboard. Make a note that the extent of our use of blackboard style architecture will be contained within the implementation of typing challenges, with possibly one other exception. We will not be using this architecture commonly throughout our program. Another style that was considered for typing challenges was an event-based style which also made sense as the typing challenge would announce events to the broadcast medium which the agents then could listen for. However, the blackboard style was chosen as it seemed the suitable choice as we are using Python.

### Blackboard Architecture - users interacting with a central database

The exception mention earlier where we will also make use of the blackboard architecture style is in using and manipulating a database. Using blackboard/repository architecture, the database itself represents the blackboard/current state, with independent individual users interacting, sending data to, and requesting data. The interactions between the users and the blackboard take place through API calls to the Firebase SDK. We chose blackboard style architecture for saving data in a database because it allowed us to have many different interactions asynchronously between a central database and the different users.

Here is an example diagram:
![IMG_7A0D8A1B128B-1](uploads/9e59a0f0b1c18a593a058afc764f178e/IMG_7A0D8A1B128B-1.jpeg)

### Pipes and Filters

Using pipes and filters, we can create a general flow through the different layers and sections of our software. It is important to note that the use of pipes and filters in our system can also just be seen as the interactions taking place between the layers of our system, and the interactions between the modules within those layers. This means that the use of pipes and filters in our system is really us just looking at our design from another point of view. We put pipes and filters architecture at the bottom because it is not absolutely necessary when trying to understand our system.

Starting at the authentication, we can collect a user JSON file from the database which contains the user's permission key which would give us information on the user type. This info will be piped to the main menu, where we can choose which data to display based on the user's group. Next, as the user goes through the UI, data will be selected and sent through each stage. When the user starts a Typing Challenge, the Typing Challenge will need to be provided with text content. This data can be provided through a pipeline, and the Typing Challenge can be seen as a filter that manipulates and displays data. We chose to use pipelines and filters to create a simple flow through our software that connects each piece of UI. The pipes and filters architecture also works well with python, making it a simple and easy choice.

Here is a diagram outlining the simple flow through our program using pipes and filters. Credit goes to Pucheng Tan.

![draft.svg](uploads/6fc2b551bd084990f24b9476fc54d4d0/draft.svg)


### Object-Oriented Programming

<del> For our system architecture style, one of the styles chosen was the object-oriented style. The reason for this is that our typing tool involves various real world entities. The object model then allowed us to clarify these entities into different objects, such as the different types of users, Classrooms, and Schools. Using these as components in a system, the connectors then are their operations with each other through function and procedure calls. This made sense with our requirements because there is a clear determination on what objects the user interface should interact with and there are requirements that could naturally be stated as a problem of agents interacting. For example, from an administrative user interface, administrative users should be able to add and remove students from Classrooms, so it is clear they should interact with the objects of standard users and Classrooms.

Note: We decided to remove our use of object-oriented programming due to complications within our chosen tech stack. However, this architecture can still be used to conceptualize the relationship between each user group.

Here is a conceptual diagram outlining that relationship. 
Note: This is purely conceptual and we will not be implementing this in such a way.

![Domain_Model__1___1_.svg](uploads/146ed56d2922617f37cf4bf6395b4935/Domain_Model__1___1_.svg)
