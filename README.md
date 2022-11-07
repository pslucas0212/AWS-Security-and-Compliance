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
  
