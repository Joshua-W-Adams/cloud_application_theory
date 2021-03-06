# Elastic File System (EFS)

A managed Network File System (NFS) that can be mounted on many EC2s.

*Note: mountable across AZs*

Use cases:
- content management, web serving, wordpress.

Only compatible with Linux.

## Performance Modes

- General Purpose
- PIOPS
- Throughput (bursting or Provisioned) 

## Storage Tiers

A lifecyle managment feature that will move files after N days.

- Standard - For frequently accessed files
- Infrequent Access - **cost to retrieve files**, lower price to store

## Security 

You can use EFS access points to override user ID and group IDs used by the NFS client. 

When users attempt to access files and directories, Amazon EFS checks their user IDs and group IDs to verify that each user has permission to access the objects