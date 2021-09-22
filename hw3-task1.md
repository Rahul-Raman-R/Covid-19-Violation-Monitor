#### HW3-task1
###### 1. You are implementing this User Story; what classes will be in your "model" UML class diagram? (Only name the classes.)
1. Professor
2. Announcements
3. Students

###### 2. The software system is implemented according to the Client-Server Architecture. To show your understanding of this architecture, describe how the above-stated User Story carries out through the interaction between different entities (user, client, server, database, ...) .
1. The professor/user visits the url of the application which it is deployed on using an internet browser on any device that provides internet
2. This opens a webpage which is the user-interface for of the application. This user-interface allows the professor to interact with the server.
3. In the client-side, the professor can use his JHU credentials to log into the application as a professor/user. Here the client side will send these credentials as an authentication request to the server.
4. The server will recieve the authentication request and then it triggers a response which is passed to the database as a query to check the database for the credentials and the database sends back the data requested.
5. The server uses this data from the database to construct and send a reponse to the client (Professor). This response provides access to the professor.
6. The client side uses the information from the response to render the final view to the professor.
7. Now the professor/user within the client-side has many features and one such feature is to make a post. The professor/user uses the client to write a post which is sent as a HTTP POST request with the data(text etc.)  to the server.
8. The server now creates a new entity with the data in the database. 
9. Now the student can use his credentials to login. Here the client side will send these credentials as an authentication request to the server.
10. The server will recieve the authentication request and then it triggers a response which is passed to the database as a query to check the database for the credentials
11. The database sends back the data requested. The server can now construct and send its response back to the client (student). In this case, the response is access to the application. 
12. The client side uses the information to render a final view to the student.
13. The client side user-interface sends a HTTP GET request to the server for the post made by the professor.
14. The server processes this request and passes a query to the database to get the data from the database. The data from the database is received by the server which then renders the data into a response to the client-side.
15. The client-side uses the response to provide the post my made by the professor to the student throught the user-interface.

###### 3. Based on the above-stated User Story (and your general understanding of how a Piazza-like system works), what design pattern(s) [among those we covered in lecture/readings] would be primed for application here. Name only one and elaborate (briefly) on the underlying problem and the proposed solution by the pattern (relate that to how the pattern fits here).
> The Observer design pattern would be appropriate for the given user story. In the given user story the professor needs to make announcements that need to reach every person in the class. These announcements made by the professor need to be updated within the announcement board of each student. The problem here is that the announcement made by the professor should automatically be updated on the announcement board within the student interface even if the student doesn't specifically search the database for the announcement. This is where our design pattern of Observer plays a role, we can assign the class making the professor's announcement to extend an Observable class and make the class retrieving the announcement to extend an Observer class. Therefore, the class extending Observable makes a post and the retrieval class extending Observer class listens to the events and automatically retrieves and updates the announcement from the database. One object can have multiple Observers which in our case are multiple students and this enables all students to receive the professor's announcement.    
      


