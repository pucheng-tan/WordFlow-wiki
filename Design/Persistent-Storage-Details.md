[[_TOC_]]
# Persistent Storage Needs
The Word Flow data strategy is created based on requirements of the application, summarized by:
- Hierarchical user management
- Access to users' typing history by the user themselves and other users that manage them, in real time
- Typing content that is accessible and does not require the user to update the application to receive more content

# Firebase Storage
Data will be stored in Google Firebase. It offers user authentication, extensive documentation, reliability, and all necessary functionality and controls. Users will be stored as Firebase users, which will store their email address, create date, last sign in, and a unique User UID for each user. All other data will be stored in the Cloud Firestore, including typing challenge text content, detailed user data, and school hierarchy. Cloud Firestore is a NoSQL document database; data is stored in collections, collections can have documents, and documents can have a combination of collections and attributes of various data types, including references to other documents. 

# Rationale
NoSQL has a much simpler structure than SQL databases- only a few "foreign key" references are necessary to represent the largely hierarchical data. A traditional SQL database would require, for example, all students to store a School foreign key, and queries to find users in that school would have to search all of the users of every school. Instead, the School is set as the top of the user hierarchy and no user data outside of the school will have to be searched. In addition to this, NoSQL databases can omit empty fields for documents, making the structure much more flexible. Firebase also offers the Realtime Database in addition to the Cloud Firestore, but Firestore was chosen due to its improved querying and sorting, indexing, and ability to scale.

# Likely Places of Change
It is expected that as the project progresses that modifications could be made to the data structure.
- documents in the Assignments collection may be assigned to Classrooms documents
- the ChallengeContent mode is referenced in multiple documents as a number- in implementation this may change to a string, or a mapping could be made either in the document database or in the application code.
- Certain fields that reference users (such as an assignment assignedTo) may be more suitable for a Classroom reference
- Users may build very large history collections, and the data may have to be stored in an aggregated form past a certain size

# Entity Relationship Diagram
A legend and descriptions are provided. Note that documents with "AutoID" as their name represent dynamically created documents that will have an ID generated for them. With the exception of Modes and the ChallengeContent documents, all documents will be created through user activity.
![Persistent_Storage_Details.svg](uploads/65e2557cbd59a817c3f833b7acc1eb19/Persistent_Storage_Details.svg)
