# Database Migration Architecture


## Introduction

This project involved a migration of an on premise database to AWS with minimal changes to their current environment. They would like no disruption to their current reporting methods, no impact on any current management processes or tools, and they would like ease of data migration. Andre, is a database lead for the company. He has additional requirements, which include reduction operational management, increasing resilience and availability, mitigating risk of deployment in one location, implementing a mechanism for data archives, and potentially bringing in interns to support the DBA team.

This is a project focusing on the deployment of a new AWS database cloud archeticture, versus a project that focuses on the provisioning of the instances and services in the AWS console.


## AWS Well Architected Framework

The AWS Well-Architected Framework is a set of best practices for building secure, high-performing, resilient, and efficient infrastructure in the cloud. It provides guidelines for designing and implementing cloud architectures that align with business objectives and technical requirements. By following these best practices, clients can ensure that their cloud environments are optimized for cost, performance, and security, leading to improved operational efficiency and reduced risk.

AWS offers a Well-Architected Framework Tool on the AWS console as part of it's services. The AWS Well-Architected Framework tool guides users through a series of questions about their architecture, workloads, and best practices. Users input information about their current infrastructure, identify areas for improvement, and receive recommendations for optimizing their workloads based on AWS best practices. The tool processes this information to generate a report with actionable insights and recommendations to help users improve the security, reliability, performance, and cost-efficiency of their AWS environment. For the scope of this project, we will deem the action of using the tool as completed and will begin the next steps and actions. 



## Next Steps and Asks
Next steps and asks were compiled to begin as follows:


- Define the scope of the structure.
- Access the current database environment and gather necessary information.
- Choose the appropriate AWS Database service for migration.
- Deploy the new database instance in AWS.
- Configure security settings and access controls for the database.
- Measure baseline performance metrics before Migration.
- Migrate data from the existing database to the new AWS database instance.
- Conduct post-migration testing to ensure data integrity and functionality.
- Optimize database performance and make nescessary adjustments.
- Monitor and manage the new AWS database instance for ongoing performance and security.

To define the scope, we must identify the databases that need to be migrated, defing the migration strategy, determine the migration method, define the target AWS infrastructure, identify any dependencies between databases or applications that may impact the migration process, define the migration timeline, and identify key stakeholders. It is crucial in setting milestones with timing expectations, and relaying those expectations as well as providing updates at each phase to the key stakeholders.

The current database must then be accessed for serveral reasons. The current database environment must be identified, information about the database schema must be collected, the data size and volume must be determined, any custom scripts or stored procedures must be identified, database version and configuration must be determined, dependencies must be identified, compliance and security requirements must be evaluated, and performance and scalability requirements must be assessed.

To determine the appropriate database service, several factors must be also considered. Data volume and type must be considered and matched to the appropriate service, performance requirements considered, scalabitly needs, cost of the service, compatibility of the database service with the existing infrastructure and tools, and security and compliance requirements must be considered. 

Next the new instance should be created, which invovles installing the instance, installing the database, and also installing the additional services, which include Amazon CloudWatch, Amazon QuickSight, Elastic Block Storage, and AWS Identity and Access Managment. Ensuring your architecture can be scaleable and meet your client's project growth needs is also imporant. For this project, while a load balancer is not needed for only one instance, the load balance was noted on the diagram to represent a scalable network. A NAT Gateway was included to allow the VPC to communicate with the internet, should a patch be needed to be downloaded at any time. 

When it comes to security, I feel security is "ground zero". All resources must have sold security designed into the architecture. We start with ensuring a VPC is created, which will serve as a firewall on the subnet level. Next, AWS Cloudshield should be installed to serve as an IDS and provide additional DDoS protection. Furthermore, security groups should be configured to provide additional security at the instance level. If the company is using endpoints, I would also suggest using an endpoint firewall or malware software for them. Next, data encryption should not be overlooked. Both data at rest and data in transit should be encrypted. The VPC and private subnet will serve in encrypting data. AWS Key Management can also be considered to encrypt the data stored. MySQL databases can also be configured by enabling the encryption option when creating the database. AWS identity and Access Management is crucial from a security standpoint. IAM helps managage user, roles, and permssions to resources.

Measuring baseline performance of the existing database should be completed prior to migrating the data. AWS DMS will be used to complete the migration. To measure baseline performance metrics of the existing Database, tools like SQL Profiler or Performance Monitor can be used. They can monitor key metrics such as CPU usage, disk I/O, memory usage, and query execution times over a period of time. This will help establish a benchmark for comparison after the migration.

Once we have the performance baseline, the DMS service is then set up in the AWS console and configured to connect to the on-premise server. Next, a replication instance is created to facilitate the transfer of data between the source and target databases. The tables and schemas to be migrated are then selected, and the migration process is initiated, with DMS continuously replicating changes from the source to the target database until the migration is complete.


Post migration testing should be completed next by comparing data between the on premise server, and the RDS in AWS to ensure consistency. Performing functional testing to ensure that all applications and services are working as expected in the new environment is also important. This will ensure that data integrity is maintained during the migration process.


After migration and testing in AWS cloud, items such as database performance, storage usage, and query optimization can be monitored and optimized. By tracking performance metrics like CPU utilization, memory usage, and I/O operations, database administrators can ensure efficient operations and identify potential bottlenecks. 

Finally, resources such as AWS Cloudwatch and QuickSight can assist in monitoring and managing the new AWS database. AWS CloudWatch can be used to monitor the performance of the new AWS database instance by setting up alarms for key performance metrics such as CPU utilization, disk I/O, and memory usage. Amazon QuickSight can be used to create dashboards and visualizations that provide insights into the performance and security of the database instance. QuickSight can be configured to pull in data from CloudWatch and other monitoring tools to provide a comprehensive view of the database's health. By using these resources in conjunction with each other, administrators can proactively monitor and manage the new AWS database instance to ensure ongoing performance and security.





## Cloud Archeticure

![image](https://github.com/dbriones49/Cloud-Projects/assets/143753667/f1a018e6-8b79-4ef0-9cb6-99f8c0cc4f67)








## Conclusion
Understanding the client's needs is crucial in determining the scope and requirements of the data migration project. It helps in identifying the specific goals and objectives that need to be achieved. Understanding the current resources allows for a more efficient migration process, as it helps in assessing the existing infrastructure and data to be migrated. Utilizing the AWS Well-Architected Framework ensures that the cloud solutions are built in a secure, reliable, and cost-effective manner, ultimately leading to successful data migration and deployment

