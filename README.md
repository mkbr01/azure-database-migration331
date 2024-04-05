# Project: Azure Database Migration

This repository documents the progress and achievements in migrating a database to Azure using various services and tools provided by the platform. Below is a detailed overview of the tasks accomplished in this milestone:

## Virtual Machine Setup:

- Configured a Windows Virtual Machine (VM) as the foundation of the production environment.
- The VM emulates the functionality of a Windows server, replicating an on-premise system within the Azure infrastructure.
- Network settings and firewall rules were adjusted to ensure secure access to the VM, enabling connections via the RDP protocol.

## SQL Server Installation:

- Installed SQL Server and SQL Server Management Studio (SSMS) on the VM.
- These tools are vital for proficient database management within the production environment, mimicking corporate database server capabilities.

## Production Database Creation:

- Created the production database by restoring it from a provided backup file.
- The backup file corresponds to the AdventureWorks database, a comprehensive sample database emulating a fictional manufacturing company's operations.
- The AdventureWorks database includes various tables, views, stored procedures, and data, providing a rich and diverse dataset for simulation purposes.

### Backup Script:

```sql
-- Create the AdventureWorks database
CREATE DATABASE AdventureWorks;

-- Backup the AdventureWorks database
BACKUP DATABASE AdventureWorks TO DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL1

Backup Script:

sql

-- Create the AdventureWorks database
CREATE DATABASE AdventureWorks;

-- Backup the AdventureWorks database
BACKUP DATABASE AdventureWorks TO DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL1
