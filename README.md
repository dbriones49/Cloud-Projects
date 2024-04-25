# Database Migration Archetictue


## Introduction

This project involved a migration of an on premise database to AWS with minimal changes to their current environment. They would like no disruption to their current reporting methods, no impact on any current management processes or tools, and they would like ease of data migration. Andre, is a database lead for the company. He has additional requirements, which include reduction operational management, increasing resilience and availability, mitigating risk of deployment in one location, implementing a mechanism for data archives, and potentially bringing in interns to support the DBA team.

This is a project focusing on the deployment of a new AWS database cloud archeticture, versus a project that focuses on the console construction of the instances and services.


## Next Steps and Asks
Next steps and asks were compiled to begin as follows:


- Define the scope of the structure.
- Access the current database environment and gather necessary information.
- Choose the appropriate AWS Database serivce for migration.
- Deploy the new database instance in AWS.
- Configure security settings and access controls for the database.
- Migrate data from the existing database to the new AWS database instance.
- Measure baseline performance metrics before Migration.
- Conduct post-migration testing to ensure data integrtiy and fucntionality.
- Optimize database performance and make nessessary adjustments.
- Monitor and manage the new AWS database instance for ongoing performance and security.

To define the scope, we must identify the databases that need to be migrated, defing the migration strategy, determine the migration method, define the target AWS infrastructure, identify any dependencies between databases or applications that may impact the migration process, define the migration timeline, and identify key stakeholders.

The current database must then be accessed for serveral reasons. The current database environment must be identified, information about the database schema must be collected, the data size and volume must be determined, any custom scripts or stored procedures must be identified, database version and configuration must be determined, dependencies must be identified, compliance and security requirements must be evaluated, and performance and scalability requirements must be assessed.

To determine the appropriate database service, several factors must be also considered. Data volume and type must be considered and matched to the appropriate service, performance requirements considered, scalibitly needs, cost of the service, compatibility of the database service with the existing infrastructure and tools, and security and compliance requirements must be considered.

Next the new instance should be created, which invovles installing the instance, installing the database, and installing the additional services.

When it comes to security,I feel security is "ground zero". All resources must have sold security designed into the archeticure. We start with ensuring a VPC is created, which will serve as a firewall on the subnet level. Next, AWS Cloudshield should be installed to serve as an IDS and provide additional DDoS protection. Furthermore, security groups should be configured to provide additional security at the instance level. If the company is using endpoints, I would also suggest using an endpoint firewall or malware software for them. Next, data enryption should not be overlooked. Both data at rest and data in transit should be encrypted. The VPC and private subnet will serve in encrypting data. AWS Key Management can also be considered to encrypt the data stored. MySQL databases can also be configured by enabling the encryption option when creating the database. 









## Cloud Archeticure

![image](https://github.com/dbriones49/Cloud-Projects/assets/143753667/f1a018e6-8b79-4ef0-9cb6-99f8c0cc4f67)








## Conclusion

