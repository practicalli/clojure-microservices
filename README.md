# Clojure Microservices 

John Smarts session
This live-coding session will design, build, deploy, and test a production-like web service writen in Java using BDD and TDD. We will use tools like Cucumber and Serenity to describe, document and automated the acceptance tests for the service, then implement the details with the help of unit-testing tools like Spock and REST-Assured. The application will be built and deployed to the cloud using a cloud-based CI/CD server.


## John Smart perspective

 A microservice 
 
  a natural concequence of applying the single responsibility princilple at the architecture level
 
 typicaly has its own data store, persistence layer, connected to an event bus 
 
 Needs to be loosley coupled 
 
## Bounded contenxt
 grouping your domain model in to self contained logical chunks 
 - small islands of concepts with relationships between them 
 - connection over rest or lightweight event bus
 - can be deployed quickly (hours not days/weeks)
 - understand the concequence of changes to a microservice easily
 
 
## Inside a microservice 

Resource 
service layer
domain model 
Repositories
Persistent layer  |  Gateway
    
    
Gateway 
Abstract awy the communication layer between microservices 


## Microservices should not fail or cause others to fail 

Forget everything about th etesting pyramid when it comes to microservices.

writing unit tests after the fact is counter-productive

* end-to-end tests  -- you dont really know what is being tested, as things are changing so fast
* integration tests
* unit tests 

unit tests should not delay the rate at which you deploy your microservices 

we need to do testing intelligently 


## why test 
- ensure we are delivering value
- document the system, they are specifications - at different levels 
- ensure the system works correctly

we test our ms so we can deplo with a sufficient level of confidence


* Outside in testing 
start with your acceptance tests, that tell you whant your service is supposed to be doing 
then work down through unit tests to code / repl 

* executable specifications and living documents 

* aggressive production monitoring 
- eg some backs will send a $1 through the system to see what happens with the transaction, a small investment to test end to end the service and check if it works (picking your battles)


## feature files 

Business requirements broken down into into features 

- specific in the business content, general in the implementation 

writing features is a collaborative effort, helping build up a common understanding and language



## Clojure BDD frameworks 

Speclj



## Tools 
Rest-Asured - testing restful web services 
Serenity BDD reporting framework 
swagger - uses annotations to document your api after the fact 
