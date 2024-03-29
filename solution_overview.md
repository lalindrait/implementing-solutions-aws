
## Solution Overview

You are a DevOps engineer for a small start up. Your company has built an application that needs to be deployed in the AWS cloud.

You are supposed to implement a AWS infrastructure to host this Java application and expose it to the users with the adquate security measures and relevant operational capabilities.

Application is called "studentdb". Application is a very simple Spring Boot app that allows you to view, add, delete, modify student information for a tution class. Interaction is only possible through a REST API and application does not have a web UI

Following are the basic application details
1. Application runs on Linux
2. Application consist of an application server and a database
3. Application is developed in Java and can run inside a single Linux server
4. Application uses a postgres database
5. Application is stateless


## Approach
We will be implementing the solution in 4 phases
- Part 1 - Create network infrastructure & configure access
- Part 2 - Create compute resources & deploy application 
- Part 3 - Configure monitoring, security and operational requirements
- Part 4 - Optimize and test the solution

<!-- ## Solution Diagram
![Lab Solution Part 1](images/aws-lab-solution_part_1.png)
 -->

