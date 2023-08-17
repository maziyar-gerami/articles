# The Many Meanings of Event-Driven Architecture • GOTO 2017

by Martin Fowler

 

He stated that four different things come after Event Driven Design that he called "Patterns". when people say they use Event-driven, they usually mean they are using one of these patterns.

## Pattern 1: Event Notification

When we change something, the managers and the system get notified. For example, in an insurance system, the address of where you live is critical; the system should be notified after changing it. Often it doesn't expect any answer at all, or if there is a response that the source does care about, it's indirect.

The problem with this pattern is the dependency of the customer management system on the quoting insurance system. It is applicable for small-size applications, but it won't be very easy for large-scale ones. It is simple and provides a low level of coupling. An event need not carry much data, often just some id information and a link back to the sender that can be queried for more information.

What is the difference between events and commands? In software engineering, some terms are equal, but they have some significant differences; "Event" and "Command" are one of them. An event only tells us what happened, but the command is imperative and says that something occurred, and you should face it this way! 

## Pattern 2: Event Carried State Transfer

This pattern is very similar to Pattern 1; in Pattern 1, the system will be informed about a change! But in this pattern, the system produces more information about the change. In the other word, in pattern 1, the producer will inform the system of the user address change, but in pattern 2, the producer will inform the system that the previous address was blah blah and the new address is blah blah blah. This procedure causes more improvements; because we don't need to query the producer about what was changed, we have the data about the event along with it.

This pattern is uncommon; because we will have a lot of replicated data, and establishing consistency is hard.

## Pattern 3: Event Sourcing

The core idea of event sourcing is that whenever we change the state of a system, we record that state change as an event, and we can confidently rebuild the system state by reprocessing the events at any time in the future. In event sourcing, first, we create a log and then change the current application state. With this method, even if the application blew up, we can rebuild its current state. Git and version control tools use event-sourcing patterns. Accounting ledgers are another example.

### Benefits and costs of Event Sourcing:

The vital property for memory images is that there is no longer any need to worry about keeping the application state in an up-to-date persistent store. Instead, you can keep the application state in the main memory. Should the process crash, you can rebuild it from the events (and snapshots).

In this approach, the program's current state is an in-memory image which, in case of short, the current state of the program can be rebuilt using events and snapshots. But persistent data will write on a database and persist memory.

Don't have any business logic in between your event and your storage.

If we do this, we face some tangling version problems.

## Pattern 4: CQRS (Command and Query Responsibility Segregation)

Use different models and components to read and write.
