# Software Architecture vs. Code
Simon Brown, Writer of Software Architecture for Developers

The original video https://www.youtube.com/watch?v=GAFZcYlO5S0
 
## The intersection Between Software architecture and code

There's a common misconception that software architecture should be conceptual and exclude technology.
## How do we communicate Software architecture?

Why? Because we develop the same thing as what the architecture said!

One of the wrong ways is using UML! UML is the standard way for communicating between software architecture! But who cares about it? Because it is very complicated, and almost non of us know it entirely! UML is complex and too low-level, and in new software development procedures, we use agile and TDD.

Some say we do TDD and don't need software architecture!
## Software architecture provides boundaries for TDD.

When discussing software architecture, showing the entire design on a single diagram is hard. So we implement different views. This is how ancient books stayed about software architecture: Logical view, Physical View, Process view and Development view. But again, who cares about it? It is an excellent way to think about software, but confusing. If we map it, logical view and development are corresponding. ‌But…

## Logical and development views are often separate.

The logical view is thinking about software without thinking about code. 

Software teams can't effectively visualize the software architecture of their system.

Simon Brown showed some pictures of some UMLs and views and stated that they are complex, confusing and crowded.

So what should we do? If we draw a UML, are we committed to it?
## The code is the embodiment of the architecture.

Code is the representable form of architecture. When we draw an architecture of a system, we draw abstractly and reduce details. We are not going to draw all details in architecture!
## Does your code reflect the abstractions that you think about?

Sometimes architecture is clear, but the code doesn't reflect it ultimately. There is a mismatch between what we draw in pictures and what we implement in code; for example, We draw a layered architecture nicely. So is it correct that say layers are bad? This problem led to a new concept invention: the Organization of Code, which differs from the Architectural View; The trick here is to merge the model and the code. 

Why don't we have a proper diagram for showing codes? Because Diagramming tools see packages and Classes rather than components. OO programming languages provide the wrong abstractions for modern software systems. We need programming languages to represent components of the system.
## Abstractions on Diagrams should reflect the code.

We should draw a picture that reflects the code and vice versa. This picture should reflect abstractions. What is essential in this picture is the level of abstraction rather than a standard notation.

A set of abstractions and notations should be agreed in the team. 

Then he presented his mod named the C4 model.

 
## The C4 Model

This model consists of 4 layers:

System Context: The System + users and system dependencies

Containers: The Overall shape of the architecture and technology choices

Components: Logical components and their interactions within a container

Code Diagram (optional): Component or pattern implementation details
Context

### Questions which we solve in the System Context Diagram
    What are we building

    Who is Using it?

    How does it fit into the existing IT environment?

### Questions which we solve in the System Container Diagram
    What are the high-level technology decisions?

    How do containers communicate with one another?

    As a developer, where do I need to write code?

### Questions which we solve in the System Component Diagram
    What component/services is the container made up of?

    Are the technology choices and responsibilities clear?


This model is not about enforcing some standards because very of developers don't like boundaries. C4 is about the static structure of software, which is ultimately about code. But these are diagrams, too, and don't show the code. We need more diagrams.

### Components

What component/services is the container made up of?

Are the technology choices and responsibilities clear?

This thing is like maps. They show software components and details of what we have drawn before using Context and Containers diagrams.

## Software Developers are the most stakeholders of software architecture.
 If not, are the diagrams helpful? As it shows the code, who better than developers can draw it? Many companies have a giant map of the system on the wall, but no one cares about it because they are of date and not drawn by developers.


A component is often a combination of some classes in different layers. But Drawing packages by layer is very complex. See the above picture. To simplify it and package them by component:

But in this way, I lose the ability to do unit testing. So Don't do Unit testing! I don't say I do not do testing, but I don't do unit testing. The unit testing was far in the early days when HDD and databases were very slow. Unit testing is a bad idea because isolating, it doesn't test everything.

Instead of unit testing everything, what about testing your significant structural elements as black boxes? He points is that we shouldn't test everything in isolation and should open some ways to communicate this component. But why are we here? We were talking about diagrams and pictures!

Good architecture enhances agility.