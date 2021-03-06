# Relation Database Service (RDS)

AWS managed relational (SQL) databases.

Supports
- Aurora
- All major relational database engines 
    - MySQL
    - PostGres
    - MariaDB
    - Oracle
    - MS SQL Server

## Backups

- Automatically setup
- Daily with 7 - 35 day rentention
- Transaction backups
- Daily and transactional backups give you the ability to restore the db at any point in time

## DB Snapshots

Can be kept as long as you want.

## Horizontal Scaling

Supported via read replicas.

Read replicas can be configured as follows:
- Up to 5 replicas
- Across AZ and region
- Replicas are ASYNC (eventually consistent)

![](./../../../img/rds_replicas.png)

Use case:
- Say you have a reporting application, to avoid overloading the main application you create a read replica so all reporting traffic can occur here.

Notes:
- read replicates require new read end point configuration (non Aurora RDS engines)

## High Availability

Supported with Multi AZ configuration. Which creates a standby database for disaster recovery.

Standby database is a replica with **synchronous** replication of all master database operations. This means that if one availability zones fails AWS RDS will automatically switch over to the synchronously replicated db.
