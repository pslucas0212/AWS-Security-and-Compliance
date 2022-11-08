# AWS Security and Compliance

[AWS Review Notes Table of Contents](https://github.com/pslucas0212/AWS-Review-Notes)

Understanding the Shared Responsibility Model
- In the public cloud, there is a shared security responsibility between you and AWS.
- AWS is responsible for protecting and securing their infrastructure.
  - AWS is responsible for its global infrastructure elements: Regions, edge locations, and Availability Zones.
  - Building security. AWS controls access to its data centers where your data resides.
  - AWS maintains networking components: generators, uninterruptible power supply (UPS) systems, computer room air conditioning (CRAC) units, fire suppression systems, and more.
  - AWS is responsible for any managed service like RDS, S3, ECS, or Lambda, patching of host operating systems, and data access endpoints.
- You are responsible for how the services are implemented and managing your application data. 
  - Application data.  You are responsible for managing your application data, which includes encryption options.
  - Security Configuration. You are responsible for securing your account and API calls, rotating credentials, restricting internet access from your VPCs, and more.
  - Patching. You are responsible for the guest operating system (OS), which includes updates and security patches.
  - Identity and Access Managment. You are responsible for application security and identity and access management.
  - Network Traffic.  You are responsible for network traffic protection, which includes security group firewall configuration.
  - Installed software.  You are responsible for network traffic protection, which includes security group firewall configuration.

- EC2 Shared Responsibility Model
  - Customer
    - Installed applications
    - Patching the guest operating system 
    - Security controls
  - AWS
    - EC2 service
    - Patching the host operating system
    - Security of the physical server
- Lambda Shared Responsibility Model
  - Customer
    - Security of code
    - Storage of sensitive data 
    - IAM for permissions
   - AWS
     - Lambda service
     - Upgrading Lambda languages
     - Lambda endpoints 
     - Operating system
     - Underlying infrastructure
     - Software dependencies

- Which security responsibilities are shared?
  - Patch Management
    - AWS: Patching infrastructure
    - Customer:  Patching guest OS and applications
  - Configuration Management
    - AWS: Configuring infrastructure devices
    - Customer: Configuring databases and applications
  - Awareness and Traing
    - AWS: AWS Employees
    - Customer: Customer Employees.   
    
  - How do I report abuse of AWS resources?  Contact the AWS Trust & Safety team using the Report Amazon AWS abuse form or by contacting abuse@amazonaws.com.

- Study for the Exam
  - Shared Responsibility Model
    - Going into the exam, remember what you are responsible for and what AWS is responsible for.
  
  
Leveraging the Well-Architected Framework
- The 6 pillars of the Well-Architected Framework describe design principles and best practices for running workloads in the cloud.


- Here are a few examples of applying best practices and design principles from the 6 pillars of the Well-Architected Framework in the real world. 
  - Operational Exellence
    - You can use AWS CodeCommit for version control to enable tracking of code changes and to version-control CloudFormation templates of your infrastructure.
  - Security
    - You can configure central logging of all actions performed in your account using CloudTrail.
  - Reliability
    - You can use Multi-AZ deployments for enhanced availability and reliability of RDS databases.
  - Performance Efficiency
    - You can use AWS Lambda to run code with zero administration. 
  - Cost Optimization
    - You can use S3 Intelligent-Tiering to automatically move your data between access tiers based on your usage patterns.
  - Sustainability
    - You can use EC2 Auto Scaling to ensure you are maximizing utilization.


Understanding IAM Users
- Identity and Access Management (IAM).  IAM allows you to control access to your AWS services and resources. Permissions. Roles. MFA
  - Helps you secure your cloud resources
  - You define who has access
  - You define what they can do
  - A free global service
- Identites vs Access
  - Identities. Who can access your resources
    - Root user
    - Individual users
    - Groups
    - Roles
  - Acess.  Whatresources they can acces
    - Policies
    - AWS managed policies
    - Customer managed policies
    - Permissions boundaries
- Authntication (Who) vs Authorization (What)
  - Authentication is where you present your identity (username) and provide verification (password).
  - Authorization determines which services and resources the authenticated identity has access to.
- Users are entities you create in IAM to represent the person or application needing to access your AWS resources.
  - The root user is created when you first open your AWS account. 
  - What can only the root user do?
    - Close your account
    - Change email address
    - Modify your support plan
  - Individual users are created in IAM and are used for everyday tasks.
  - What can individual users do?
    - Perform administrative tasks 
    - Access application code
    - Launch EC2 instances
    - Configure databases
  - Did you know applications can be users?
  - You'll create a user in IAM so you can generate access keys for an application running on-premises that needs access to your cloud resources.
  
  - Don't forget activity performed by users in your account is billed to your account!

  - The principle of least privilege involves giving a user the minimum access required to get the job done.
    - Create access keys for an IAM user that needs access to the AWS CLI. The AWS Command Line Interface (CLI) allows you to access resources in your AWS account through a terminal or command window. Access keys are needed when using the CLI and can be generated using IAM.
  - Groups. A group is a collection of IAM users that helps you apply common access controls to all group members.
    - Administrators perform administrative tasks such as creating new users.
    - Developers use compute and database services to build applications.
    - Analysts run budget and usage reports.
  - ***Note:*** Do not confuse security groups for EC2 with IAM groups. EC2 security groups act as firewalls, while IAM groups are collections of users.
  - Key Takeaways - Groups
    -  Used to group users that perform similar tasks.
    -  Access permissions apply to all members of the group.
    -  Access is assigned using policies and roles.
  -  Apply the same access controls to a large set of users.  Groups save you time by allowing you to apply the same access permissions to more than one user at once. When a user no longer needs access, they can be removed from the group.

- Studying for the Exam
  - Users and groups
    - Going into the exam, understand the differences between users and group.
  - Root user tasks
    - Remember the tasks that only the root user can do. 
  - Principle of least privilege
    - Don't forget about the principle of least privilege.
  - Real-world use cases
    - Don't forget the real-world use cases for IAM.



