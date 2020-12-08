
## Design Storyboards

[Design Storyboards](/Final-Product-Report/As-Built-Design/Design-Storyboards)

## UML class diagram

#### Note: The diagram is quite large, so click on it to get a better view.

![Domain_Model_2.0.svg](uploads/eaf6276ce0dbf1917c6a35ef23ee31bf/Domain_Model_2.0.svg)

Differences: 

The biggest change here is in the GUI layer. This layer needed a lot of changes because the GUI contained a lot of modules that we never included in the original diagram. Note: In reality, there are still 20+ modules missing from the GUI layer. There are lots of active windows that were not outlined in this diagram because it would make the diagram too big. To represent these missing modules in the GUI layer, we replaced the active windows with the 'OtherWindow' module, and we replaced the menu item that creates that active window with 'OtherMenuItem'. Replace these with the respective active window and menu item to see the missing modules.

## UML component diagram(s)

![UML_Component_Diagram](uploads/2a216e2e4aa48f74f4c12d077faaf47c/UML_Component_Diagram.png)

Differences:

Added a new section for a dictation challenge. The notable change here is that the text to speech library component connects with the challenge content component and user input component. This is because the text to speech library needs the typing challenge content to read it out, but it also needs to know the user input, because it only reads out a new word on a space.

# UML sequence diagram(s)

[Sequence diagrams](/Final-Product-Report/As-Built-Design/Interaction-Diagrams)

# Persistent Storage Details

[Persistent Storage Details](/Design/Persistent-Storage-Details)

-No changes

■ Provide written content outlining the differences between your original Milestone 2 deliverables and these new diagrams. What changed? Why?