

## Implementation Requirements - Part 1
In part 1 of the implmentation you are supposed to do the following.

1. Create AWS Network infrastrcture - VPC, Subnets, Route Tables
2. Implement a NAT solution to download application app updates and dependencies
3. Implement the security groups and NACL as needed - Use least priviledge principle
4. Application support engineers should be able to login to servers through SSH from their laptops through internet - Implement a suitable solution
5. You as the DevOps engineer should have CLI access to the cloud environment - Implement aws cli access
6. Give read acess to the developers to view the environement - Give access to a dev IAM account called "msd-dev"


**Please take note of the following unfunctional requirements**

1. Every resource should have the following mandatory tags
    - Name = Resource Name
    - ApplicationName = StudentDB
    - AppOwner = MIT-MSD
    - CostCenter = MSD
2. Application should have HA within the region
3. Multi-regional redundancy is not required in this phase of the implementation
  
## Few things to note
- Organization corporate network uses the 10.0.0.0/8 IP range & existing Azure cloud uses 172.16.0.0/16 range



## Solution Diagram
![Lab Solution Part 1](../images/aws-lab-solution_part_1.png)


## Guidelines

### Selecting a region
- Data governance and legal requirements
- Proximity to customers - Latency
- Service available in the region
- Costs 

### Selecting the VPC and other resource names
Follow a resource naming convention

A resource naming convention is already available in the following link. Use it as a guide.

https://millenniumitesp.atlassian.net/wiki/spaces/MSTDevOps/pages/203685892/Cloud+Resource+Naming+Standard

### Selecting a VPC CIDR range
- VPC CIDR should not overlap with other VPCs and networks (Corporate subnets)
- Should use private IP address ranges
- Block size – between /16 - /28

### Implementing resource tagging

Following documentation shows how to implement a tagging standard for a solution/organization

https://millenniumitesp.atlassian.net/wiki/spaces/MSTDevOps/pages/203685922/Cloud+Tagging+Standard

