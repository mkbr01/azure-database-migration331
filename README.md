# Azure Database Migration

- **Project Name**: Azure Database Migration
- **Author**: Mark Baker
- **Started On**: 23/03/2024
- **GitHub Repository**: [Azure-Database-Migration](#)

## Overview

This README provides a comprehensive guide to setting up and migrating a production database to Azure SQL Database. The project aims to demonstrate expertise in cloud engineering by implementing a robust, secure, and efficient database migration process on Microsoft Azure.

## Table of Contents

1. [Project Introduction](#project-introduction)
2. [Environment Setup](#environment-setup)
3. [Database Migration](#database-migration)
4. [Data Backup and Restore](#data-backup-and-restore)
5. [Geo-Replication and Failover](#geo-replication-and-failover)
6. [Microsoft Entra ID Authentication](#microsoft-entra-id-authentication)
7. [UML Diagram](#uml-diagram)
8. [Conclusion](#conclusion)

## Project Introduction

In this project, you'll architect and implement a cloud-based database system on Microsoft Azure, showcasing hands-on expertise in cloud engineering. You will migrate an on-premise database to Azure SQL Database, utilizing various Azure services and tools.

## Objectives

- Set up a production environment database on a Windows Virtual Machine (VM).
- Migrate the on-premise database to Azure SQL Database.
- Implement data backup and restore strategies.
- Configure geo-replication for enhanced data resilience.
- Integrate Microsoft Entra ID authentication for user management.

## Environment Setup

### Windows Virtual Machine (VM)

- Provision a Windows VM to serve as the production environment.
- Configure network settings and firewall rules for RDP access.
- Install SQL Server and SQL Server Management Studio (SSMS).

### Azure Services

- Request Azure login credentials for project usage.
- Set up Azure Blob Storage for database backups.
- Create an Azure SQL Database for migration target.

## Database Migration

### Initial Setup

- Restore the AdventureWorks database backup on the production VM.
- Install Azure Data Studio for database management.

### Migration Steps

- Connect to on-premise and Azure SQL databases using Azure Data Studio.
- Use SQL Server Schema Compare extension for schema migration.
- Utilize Azure SQL Migration extension for data migration.

### Validation

- Validate migration success by checking data integrity and configurations.
- Document migration process and achievements in README.

## Data Backup and Restore

### Backup Process

- **Full Backup**
    - Generated a full backup of the production database hosted on the Windows VM.
    - Stored the resultant backup file in a designated location on my computer.

### Azure Blob Storage Configuration

- **Blob Storage Account**
    - Configured an Azure Blob Storage account to serve as a secure online repository for database backups.
- **Backup Upload**
    - Uploaded the production database backup file to the Blob Storage container for redundant backup storage.

### Development Environment Provisioning

- **Windows VM Setup**
    - Provisioned a new Windows VM mirroring the development setup.
    - Installed SQL Server on this VM to mimic the necessary database infrastructure.
- **Database Restoration**
    - Restored the production database backup onto the new development environment ("sandbox").

### Automated Backups for Development

- **Management Task in SSMS**
    - Utilized SQL Server Management Studio (SSMS) to establish a Management Task for automating regular backups of the development database.
- **Backup Schedule**
    - Configured a weekly backup schedule to ensure consistent protection and simplify recovery for the development environment.

### Testing and Validation

- **Development Environment**
    - Functionality: Verified the restored database's functionality in the development environment.
    - Data Integrity: Confirmed data integrity post-restoration, ensuring consistency with the production database.
- **Automated Backups**
    - Consistency: Validated the automated backup schedule, ensuring regular and consistent backups.

### Insights Gained

- **Data Security**: Leveraging Azure Blob Storage provided an extra layer of backup protection, enhancing data security.
- **Development Efficiency**: The provisioned development environment ("sandbox") facilitated controlled experimentation and testing without impacting production data.
- **Operational Resilience**: Automating backups streamlined the backup process, enabling swift recovery and reducing operational overhead.

## Geo-Replication and Failover

### Setting up Geo-Replication

- **Azure Portal Setup**
    - Navigated to the primary database in Azure Portal.
    - Selected Replicas under the Data management tab.
    - Created a new replica in East US region.
    - Configured SQL authentication for disaster recovery.
- **Validation**
    - Connected to the secondary replica via Azure Data Studio.
    - Ran queries to ensure data synchronization and functionality.

### Failover Setup

- **Failover Groups**
    - Created a new failover group in Azure Portal.
    - Associated the secondary server as the failover target.

### Failover

- **Planned Failover**
    - Initiated a planned failover from the primary to the secondary region.

### Tailback

- **Failback**
    - Initiated a failover back to the primary region after testing.

### Insights Gained

- **Redundancy**: Geo-replication provides an effective redundancy strategy, ensuring continuous data availability across regions.
- **Resilience**: The failover mechanism proved resilient, maintaining data integrity and availability during planned transitions.
- **Operational Confidence**: Conducting planned failovers and failbacks provided valuable insights into the failover process, bolstering confidence in disaster recovery capabilities.

## Microsoft Entra ID Authentication

### Integration Steps

- Enable Microsoft Entra ID authentication for Azure SQL Server.
- Create admin and DB Reader user accounts.
- Assign roles and test permissions.

### Documentation

- Update README with Microsoft Entra ID integration details.

## UML Diagram


## Conclusion

This project has covered various aspects of migrating a database to Azure SQL Database, including environment setup, data migration, backup and restore strategies, geo-replication, and authentication. The README serves as a comprehensive guide documenting each step, providing insights, and sharing the experience gained throughout the project.
