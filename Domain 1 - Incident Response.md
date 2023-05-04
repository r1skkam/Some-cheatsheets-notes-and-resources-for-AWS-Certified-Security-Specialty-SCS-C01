## Domain 1 - Incident Response

### For the exam, you should know how to:

1. Evaluate the suspected compromised instance or exposed access keys given an AWS abuse notice.
2. Verify that the incident response plan includes relevant AWS services.
3. Evaluate the configuration of automated alerting, and execute possible remediation of security-related incidents and emerging issues.

### Rethink incident response

### on-premises

![image](https://user-images.githubusercontent.com/58542375/236142819-77dd414f-c7fb-4995-b0ec-2d94a9272f90.png)

### AWS Cloud

![image](https://user-images.githubusercontent.com/58542375/236142907-853544d2-3b5d-42b4-9dd0-57200de3e20b.png)

### AWS tools for incident response

[AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/)
![image](https://user-images.githubusercontent.com/58542375/236168012-ea8fe8f8-cfc1-44e7-91b9-dbf2bf3fa99a.png)

[AWS CloudFormation](https://aws.amazon.com/cloudformation/)
![image](https://user-images.githubusercontent.com/58542375/236168850-b02f85b3-c39b-45a8-8c2e-974b1e6996f0.png)

[AWS Service Catalog](https://aws.amazon.com/servicecatalog/)
![image](https://user-images.githubusercontent.com/58542375/236169230-71905b3a-e2e6-46ba-9717-60e1a575fdf2.png)

[VPC Flow Logs](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)

![image](https://user-images.githubusercontent.com/58542375/236169710-a0438985-3a5b-4c12-b518-461c1a44561f.png)

[AWS Config](https://aws.amazon.com/config/)
![image](https://user-images.githubusercontent.com/58542375/236170231-414faf5e-f6db-4125-abdd-3ee2341ebadf.png)

[Amazon API Gateway](https://aws.amazon.com/api-gateway/)
![image](https://user-images.githubusercontent.com/58542375/236171234-fd7583fd-16ea-4371-a89a-d0f21e21b0f3.png)

[AWS CloudTrail](https://aws.amazon.com/cloudtrail/)
![image](https://user-images.githubusercontent.com/58542375/236171874-14b33b34-03c5-4eec-b943-2b10d590d275.png)

[Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)
![image](https://user-images.githubusercontent.com/58542375/236172540-31b0913d-d389-411a-8458-42ef7ba0ce99.png)

### Common incidents

`Compromised user credentials`

![image](https://user-images.githubusercontent.com/58542375/236173393-f54ca518-71d3-4c56-b928-ef54a9de1908.png)

`Insufficient data integrity`

![image](https://user-images.githubusercontent.com/58542375/236173692-64755df2-e1f0-42fa-b1cc-323153a3ffd3.png)

`Overly permissive access`

![image](https://user-images.githubusercontent.com/58542375/236173781-1b0e87be-dc90-4424-a136-386a40aa4e8d.png)

### Instance isolation example

![image](https://user-images.githubusercontent.com/58542375/236141438-2586eab8-f21b-4780-bf1c-d295e9c6c297.png)

![image](https://user-images.githubusercontent.com/58542375/236143189-e6ccd412-e0ff-4d80-bb4e-fd9cec8b71c0.png)

### Example response walkthrough

```
1. Invaildate credentials
  - Disable exposed credentials.
  - When appropriate, delete exposed access keys.
```
```
2. Revoke privileged access
  - Attach a “Deny IAM” policy to user.
  - Revoke any outstanding sessions.
```
```
3. Determine the source of the IAM access keys
  - Track down which user the access keys are associated with.
  - Review the scope of the policies associated with the access keys.
```
```
4. Verify integrity and determine blast radius
  - Use CloudTrail and AWS Config to determine if anything has changed.
  - Consider other IAM access keys or credentials that could be a problem.
```  

### AWS Config use case

![image](https://user-images.githubusercontent.com/58542375/236147537-6c23981c-e9cc-44b7-b07e-6a65d052c696.png)

```
1. ACL configuration change event
A bucket ACL configuration change event is recorded by AWS Config where a bucket was made public.
```
```
2. SNS topic published
If AWS Config finds a rule violation, such as making a bucket public write,
an SNS topic may be configured to send out an email notification.
```
```
3. Rule violation triggers Lambda function
AWS Config can also be set up to trigger a Lambda function.
```
```
4. Lambda function corrects bucket ACL
The Lambda function corrects the S3 bucket ACL.
```

### Sample question 1
```
Your company is serving content through a CloudFront distribution.
Your IR team wants to review data to identify possible indicators of compromise or anomalous events.
In particular, they are looking for source IP address, the original request, the referrer, and protocol information.

Where should they look for this data?

A. Amazon S3 bucket logs for the source content

B. CloudFront access logs for the distribution

C. CloudWatch logs for the Amazon S3 bucket and CloudFront

D. CloudTrail events logged in CloudWatch
```
[Automating processes for handling and remediating AWS Abuse alerts | AWS Cloud Operations &amp; Migrations Blog](https://aws.amazon.com/blogs/mt/automating-processes-for-handling-and-remediating-aws-abuse-alerts/)

### Sample question 2 
```
You are the security administrator at BigPhoneCompany, the national telecommunications carrier.
You want to be able to automate isolation of specific instances in several public subnets that contain EC2 instances.

What is the simplest way to do this?

A. Create a Lambda function that modifies the NACL to block inbound traffic.

B. Create a Lambda function that modifies the security group to block inbound traffic.

C. Create a Lambda function that modifies the WAF rules to block traffic to the EC2 instances.

D. Create a Lambda function that revokes active sessions for the role attached to the EC2 profile.
```

**Source:** *aws training and certification* 
