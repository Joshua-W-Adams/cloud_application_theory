# Elastic Block Store (EBS) Volume

A network drive (not a physical drive) that can be attached to an instance.

"A network USB stick."

## EBS Snapshot

A copy of a EBS volume at a specific point in time.

Can be used for 
- backups
- moving data across regions and AZs

## EBS Volume Types

General Purpose SSD (gp)
- gp2/gp3
- low latency, cost effective

High Performance / Provisioned IOPS (PIOPS) SSD
- io1/io2
- Perfect for databases
- >=32000 IOPS need io1, io2 with EC2 nitro
- With io2 Block Express volumes, you can provision volumes with Provisioned IOPS (PIOPS) up to 256,000

Hard Drives (HDD)
- Throughput Optimised (st1)
- Cold HDD (sc1)
- both low cost HDDs

## EBS Multi Attach

Ability to attach an EBS volume to multiple EC2 instances.

## EBS Encryption

Encrypting an EBS volume will encrypt the following:
- data at rest
- **data traffic between EBS and EC2**
- snapshots

Minimal impact on latency ("almost nothing")

*Note: Uses KMS encryption keys (AES-256)*

Encrypt a volume:
- create snapshot
- copy & encrypt snapshot
- create volume

## EBS RAID

EBS supports RAID as long as the OS supports it.

RAID 0 - Stripped
RAID 1 - Mirrored
RAID 0/1 - Stripped and Mirrored