# Snow Family

Highly secure portable devices to collect, process and migrate data in and out of aws.

## Devices

- Snowcone 
    - smaller device
    - Edge computing, storage and datatransfer
    - 8Tbs of data.
- Snowball Edge
    - small device
    - Compute optimised
    - storage optimised
    - 70 TBs of data 
    - Support storage clustering
- Snowmobile 
    - truck
    - 1EB (1000 PB)
    - each snowmobile has 100PB capacity

All devices can run EC2 instances and also lamda functions
Use CLI or OpsHub (GUI to connect to snow devices)

## Applications

### Data Migration

importing or exporting data from aws

*Note: **Snowball cant import directly into Glacier**. Needs to go into s3 first. Then a lifecycle rule needs to be setup to transfer to glacier.*

### Edge Computing 

Process data while its being created

Edge location = can produce data but has limited internet connectivity.