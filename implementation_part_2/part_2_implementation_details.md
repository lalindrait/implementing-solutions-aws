

## Implementation Requirements - Part 2
In part 2 of the implmentation you are supposed to do the following.

1. Create a AMI image for the application
2. Create EC2 instances for application deployement 
3. Change/create security groups and route tables 
4. Deploy postgres rds instance
5. Deploy application
6. Expose traffic to users through a application load balancer
7. Test the application



## Solution Diagram
![Lab Solution Part 1](../images/aws-lab-solution_part_1.png)


## Guidelines

### Creating the AMI image

```
# Installing java
dnf install -y java-17-amazon-corretto java-17-amazon-corretto-devel

# Installing postgre client - To test DB connectivity
dnf search postgres
dnf install postgresql15.x86_64

# Testing the RDS DB connection
psql -h studentdb.cpny086a0vbw.us-east-1.rds.amazonaws.com -p 5432 -U lv -d studentdb
```

### Deploying the application

Application is simple application developed using java and hibernate. Application allows us to add, delete,change student data and retrieve student data through a REST API. Application does not have any web UI.

Application is hosted in GitHub

https://github.com/lalindrait/studentdb-app


You can use the following steps to deploy the application inside a EC2 instance.

```
# Step 0 - Check RDS connectivity and create the DB

# Login to the database
psql -h studentdb.cpny086a0vbw.us-east-1.rds.amazonaws.com -p 5432 -U lv -d studentdb


# Step 1 - Download the application binary - jar file

# Use the latest release in the github repo
wget https://github.com/lalindrait/studentdb-app/releases/download/v0.0.1/studentdb-0.0.1.jar


# Step 2 - Configure datasource settings

# Create a "application.properties" file in the same location as the jar file and add the necessary entries as follows.

vi application.properties

# add the following entries and change the values accordingly
spring.datasource.url=jdbc:postgresql://studentdb.cpny086a0vbw.us-east-1.rds.amazonaws.com:5432/studentdb
spring.datasource.username=lv
spring.datasource.password=lv123456

# Step 3 - Run the application

java -jar studentdb-0.0.1.jar

# Step 4 - Verify applicaiton is up and functioning
# From the same ec2 instance execute the following. You shoud get some raw json output as the result
curl http://127.0.0.1:8080/api/v1/student

# If you have jq installed following will give you a formatted json output
curl http://127.0.0.1:8080/api/v1/student | jq
```




### How to use the application
Application has no web UI and yuo can only interact with it using the REST API.

To interact with the application you need to use either a command line tool like curl to access the REST API or a tool like postman

Postman is a popular tools for accessing and teating APIs.
There is both a online version and a desktop app. You can download postman desktop app from the following URL.

https://www.postman.com/downloads/


