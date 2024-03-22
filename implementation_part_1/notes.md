## Deploying multiple applications in AWS

There can be 10s, 100s or even 1000s of applications in organizations. Question is how do you deploy all these application in AWS. 

What is the strategy to manage hundreds of applications inside AWS providing the right level of segregation and security.

Lets look at the options we have here.

- Option 1 - All in one account
You deploy all the applications in one aws account and use different VPCs, IAM users, roles etc. This should never be done as it does not allow any separation for applications.

- Option 2 – One account per application
You deploy all prod, uat, test, dev environments in one account. This should also be avoided as it does not provide any separation between environments.

- Option 3 – One account per application per environment
Each application should have a separate account per each environment.

Option 3 is the ideal account strategy we should use. You may end up with lot of account and management overhead may increase. You have to use automation to manage accounts or implement a “Landing Zone”.

We call this the account policy or account strategy and it is known as **One account per workload per environment**.

For example student db app may have following accounts if there are 4 environments.
- Prod account - AWS-MSD-STUDENTDB-PROD
- UAT account - AWS-MSD-STUDENTDB-UAT
- Test account - AWS-MSD-STUDENTDB-TEST
- Dev account - AWS-MSD-STUDENTDB-DEV


## Measuring network latency in AWS

AWS Region to Region latency \
https://www.cloudping.co/grid

Latancy to AWS regions from your location \
https://aws-latency-test.com/ \

Following is a aws test specifically for AWS workspaces \
https://clients.amazonworkspaces.com/Health.html


## Miscellaneous Notes

### Application types in an organization
Applications organizations have can be of 2 types.

- Corporate Application – These are internal applications like HR systems, finance system, attendance systems etc.
- Enterprise Application – Business application generating revenue for the organization

We need to manage these 2 types of application in different ways. We call this Corporate IT and Enterprise IT. 

### What is a Landing Zone

A landing zone is a well-architected, multi-account AWS environment that is scalable and secure. 

To learn further please read the following.

https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-aws-environment/understanding-landing-zones.html
