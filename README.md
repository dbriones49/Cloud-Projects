# Database Migration Archetictue


## Introduction

This project involved a migration of an on premise database to AWS with minimal changes to their current environment. They would like no disruption to their current reporting methods, no impact on any current management processes or tools, and they would like ease of data migration. Andre, is a database lead for the company. He has additional requirements, which include reduction operational management, increasing resilience and availability, mitigating risk of deployment in one location, implementing a mechanism for data archives, and potentially bringing in interns to support the DBA team.


## Next Steps and Asks
Next steps and asks were compiled to begin as follows:

Create the AWS Architecture.
Configure and launch the MySQL Server.
Implement the migration using AWS DMS.
Configure the AWS EBS Storage Service.
Configure AWS CloudWatch for monitoring the database
Integrate AWS Quicksight for reporting purposes and to ensure compatibility with their current methods.
Conduct post migration testing and optimization to ensure the database is functioning efficiently.
Provide training and support to the company staff on managing the database in the cloud.

## Cloud Archeticure
![image](https://github.com/dbriones49/Cloud-Projects/assets/143753667/818bcbd5-4785-47ad-bcad-1139b8b94b5f)



## Architecture After Hardening / Security Controls
![Architecture Diagram](https://i.imgur.com/YQNa9Pp.jpg)

The architecture of the mini honeynet in Azure consists of the following components:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel





## Conclusion

In this project, a mini honeynet was constructed in Microsoft Azure and log sources were integrated into a Log Analytics workspace. Microsoft Sentinel was employed to trigger alerts and create incidents based on the ingested logs. Additionally, metrics were measured in the insecure environment before security controls were applied, and then again after implementing security measures. It is noteworthy that the number of security events and incidents were drastically reduced after the security controls were applied, demonstrating their effectiveness.
