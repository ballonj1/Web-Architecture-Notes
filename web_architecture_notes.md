## Web Application Architecture
Basic Rules
1. Scalability
-> Architecture should be capable of scaling horizontally, across multiple servers and across multiple regions.
-> As traffic goes up, you should be able to add and remove new servers

2. Availability
-> Users should still have access even if multiple servers fail

3. Security
-> Architecture should expose the smallest amount of code possible
-> Access to one piece of code should not grant access to all pieces of code

4. Extensibility
-> It should be easy to extend the architecture without having to worry about breaking other parts

5. Separation of responsibility
-> Code should be modular and as individualistic as possible
-> Back end should not create front end code nor the other way around
-> Layers of the application should communicate using RESTFul API calls with JSON content

-> The foundation of our application is the DATA LAYER
1. Includes our data store (Use something like AWS RDS (Amazon Relational Database Service) - A managed relational database service with a choice of six popular database engines.  Allows you to set up, operate, and scale a relational database in the cloud with just a few clicks)

-> The next layer is the SERVICE LAYER
1. Handles the interaction with the DATA LAYER -> Should be the only layer that has access to the data
2. Within this layer we would implement the Repository Pattern and the Unit of Work pattern to ensure we have an efficient way of talking to our data and handling our Business Entities right
-> There is no business logic in this layer
-> In the SERVICE LAYER, all we do is CREATE, RETRIEVE, UPDATE, AND DELETE to the DATA LAYER

## The Repository Pattern
-> Use a repository to separate the logic that retrieves the data and maps it to the entity model from the business logic that acts on the model
-> The business logic should be agnostic to the type of data that comprises the data source layer
-
