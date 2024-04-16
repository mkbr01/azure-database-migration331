# Azure Database Migration

- **Project Name**: Azure Database Migration
- **Author**: Mark Baker
- **Started On**: 23/03/2024
- **GitHub Repository**: [Azure-Database-Migration](#)

## Overview

This README provides a guide to setting up and migrating a production database to Azure SQL Database. The project aims to demonstrate expertise in cloud engineering by implementing a robust, secure, and efficient database migration process on Microsoft Azure.

## Table of Contents

1. [Project Introduction](#project-introduction)
2. [Set up the Environment](#set-up-the-environment)
3. [Set up the production environment](#set-up-the-production-environment)
4. [Migrate to Azure SQL Database](#migrate-to-azure-sql-database)
5. [Data Backup and Restore](#data-backup-and-restore)
6. [Disaster Recovery Simulation](#disaster-recovery-simulation)
7. [Geo replication and failover](#geo-replication-and-failover)
8. [Microsoft entra Directory Integration](#microsoft-entra-directory-integration)
9. [UML Diagram](#uml-diagram)
10. [Conclusion](#conclusion)

## Project Introduction

In this project, a cloud-based database system is architected and implemented on Microsoft Azure, showcasing hands-on expertise in cloud engineering. An on-premise database is migrated to Azure SQL Database, utilizing various Azure services and tools.

## Objectives

- Set up a production environment database on a Windows Virtual Machine (VM).
- Migrate the on-premise database to Azure SQL Database.
- Implement data backup and restore strategies.
- Configure geo-replication for enhanced data resilience.
- Integrate Microsoft Entra ID authentication for user management.

## Set up the Environment

### Windows Virtual Machine (VM)

- Provision a Windows VM to serve as the production environment.
- Configure network settings and firewall rules for RDP access.
- Install SQL Server and SQL Server Management Studio (SSMS).

### Azure Services

- Request Azure login credentials for project usage.
- Set up Azure Blob Storage for database backups.
- Create an Azure SQL Database for migration target.

## Set up the production environment

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

## Migrate to Azure SQL Database

### Sandbox

A sandbox is a controlled and isolated environment where applications and software can be tested, developed, and experimented with, all without impacting the production systems. To create this development environment, the Windows VM which is currently the Production Environment, with all of its infrastructure, is duplicated. The purpose of a sandbox is to work on the application, test new features, and troubleshoot issues in a safe and isolated environment before making changes in the production system.

### Backup Process

- **Full Backup**
    - Generate a full backup of the production database hosted on the Windows VM.
    - Store the resultant backup file in a designated location on the computer.

### Azure Blob Storage Configuration

- **Blob Storage Account**
    - Configure an Azure Blob Storage account to serve as a secure online repository for database backups.
- **Backup Upload**
    - Upload the production database backup file to the Blob Storage container for redundant backup storage.

### Development Environment Provisioning

- **Windows VM Setup**
    - Provision a new Windows VM mirroring the development setup.
    - Install SQL Server on this VM to mimic the necessary database infrastructure.
- **Database Restoration**
    - Restore the production database backup onto the new development environment ("sandbox").

### Automated Backups for Development

- **Management Task in SSMS**
    - Utilize SQL Server Management Studio (SSMS) to establish a Management Task for automating regular backups of the development database.
- **Backup Schedule**
    - Configure a weekly backup schedule to ensure consistent protection and simplify recovery for the development environment.

### Testing and Validation

- **Development Environment**
    - Functionality: Verify the restored database's functionality in the development environment.
    - Data Integrity: Confirm data integrity post-restoration, ensuring consistency with the production database.
- **Automated Backups**
    - Consistency: Validate the automated backup schedule, ensuring regular and consistent backups.

### Insights Gained

- **Data Security**: Leveraging Azure Blob Storage provides an extra layer of backup protection, enhancing data security.
- **Development Efficiency**: The provisioned development environment ("sandbox") facilitates controlled experimentation and testing without impacting production data.
- **Operational Resilience**: Automating backups streamlines the backup process, enabling swift recovery and reducing operational overhead.

## Data Backup and Restore

### Disaster Recovery Simulation

This segment of the project intentionally induces data loss and corruption in the production environment to evaluate the effectiveness of disaster recovery processes.

## Geo replication and failover
![Geo rep](https://github.com/mkbr01/azure-database-migration331/blob/main/geo-rep.png)

### Setting up Geo-Replication

- **Azure Portal Setup**
    - Navigate to the primary database in Azure Portal.
    - Select Replicas under the Data management tab.
    - Create a new replica in a different region.
    - Configure SQL authentication for disaster recovery.
- **Validation**
    - Connect to the secondary replica via Azure Data Studio.
    - Run queries to ensure data synchronization and functionality.

### Failover Setup

- **Failover Groups**
    - Create a new failover group in Azure Portal.
    - Associate the secondary server as the failover target.

### Failover

- **Planned Failover**
    - Initiate a planned failover from the primary to the secondary region.

### Tailback

- **Failback**
    - Initiate a failover back to the primary region after testing.

### Insights Gained

- **Redundancy**: Geo-replication provides an effective redundancy strategy, ensuring continuous data availability across regions.
- **Resilience**: The failover mechanism proves resilient, maintaining data integrity and availability during planned transitions.
- **Operational Confidence**: Conducting planned failovers and failbacks provides valuable insights into the failover process, bolstering confidence in disaster recovery capabilities.

## Microsoft entra Directory Integration

### Integration Steps

- Enable Microsoft Entra ID authentication for Azure SQL Server.
- Create admin and DB Reader user accounts.
- Assign roles and test permissions.

## UML Diagram
![UML Diagram](https://github.com/mkbr01/azure-database-migration331/blob/main/Azure%20Project%20Diagram.jpeg)


## Conclusion

This project covers various aspects of migrating a database to Azure SQL Database, including environment setup, data migration, backup and restore strategies, geo-replication, authentication, and disaster recovery testing. The README serves as a guide documenting each step, providing insights, and sharing the experience gained throughout the project.
