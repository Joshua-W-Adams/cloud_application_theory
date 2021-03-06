# AWS Elastic Cloud Compute (EC2)

EC2 is a service for renting virtual machines.

You can specify all the parameters about the machine such as:

- OS
- CPU
- RAM
- Storage
- Network Card
- Firewall

## AWS Instance Types

There are 7 types of instances and each of these types have families or subtypes. The key instance types are as follows:

- General Purpose (m) - Balanced instance type between cpu, memory, storage and networking.
- Compute Optimized (c)
- Memory Optimized (r [RAM])
- Storage Optimized (i, d, h1)

### Naming Conventions

m5.2xlarge

m = instance class / type. m is general purpose
5 = generation of hardware
2xlarge = size in instance class

## Connection Options

SSH, Putty and EC2 Instance Connect (uses web browser to connect to instance via SSH).

### Secure Shell (SSH)

ssh -i (key file .pem location) ec2-user@instance ip address

ec2-user is the same for all ec2 instances

*Note: common error: permissions 0644 - permissions are too open - it is required that the private key files are not accessible by others. ... This can be fixed by right clicking the .pem file, going to the security tab, ensuring you are the only user with access and remove all other user access from the key.*

## AWS commands

ec2 instances come with the aws commands installated and accessible via command line.

For example you can run...

```
aws iam list-users
```

For this to work an IAM Role will need to be attached ot the instance so it has the permissions to perform this operation.

## EC2 Instance Purchasing Options

*Memorisation Note: Associate each of the 4 pricing models to a hotel.*

### On-Demand

Pay for what you use on a per hour basis

High cost but no upfront payment or long term commitment

### Reserved

Reserve a specific type instance for a long period of time

- Up to 75% discount from on-demand
- Two types
    - Convertible (all day)
    - Scheduled (specific periods during the day)

Reservation Period - Can only be reserved for 1 or 3 years. No in between, more or less.

### Dedicated Hosts

Physical server with EC2 instance capacity.

- Help meet compliance - sometimes compliance dictates you must have your own physical servers
- if you have complicated liscencing model (BYOL - Bring Your Own Liscence)

There are also dedicated instances which are EC2 instances running on hardware that is dedicated to you.

### Spot Instances

Paying for left over instances where you specify the specific instance type, zone and also the instance count.

- Can be lost at any spot in time if your max price is less than the spot price
- Up to 90% discount. Most cost efficient
- Useful for workloads that are resistant to failure
    - image processing
    - distributed workloads

#### Spot Requests

Specify the details about the spot instance or spot fleet you require (i.e. max price, number of instances, instance types, request type).

Two typs of requests
- 1 time request
- persistent request

![](./../../img/aws_spot_instances.png)

#### Stopping Spot Instances

Need to cancel the spot request
THEN terminate the instances if they are up and running

#### Cost Strategies

Max Spot Price - maximum prive you are willing to pay, after which the instance will be stopped. 2 minute grace period provided.
Spot Block - **block** a spot instance between a period of time 1-6 hrs

#### AWS Spot Fleets

Like spot instances, however you specify launch pools (types of instances) and a strategy to launch from these pools.

Strategies

- lowest price - pick pool with lowest cost
- diversified - distribute workload accross all pools
- capacityOptimized - pool with optimal capacity for specified instances

## Bootstrapping

Running commands when a virtual machine starts.

This are only ever run once when the machine first starts.

Can be specified as user data scripts when configuring each instance.

## AWS Elastic IP

Fixed public IP address which is assignable to EC2 instances.

Notes:
- Starting and stopping instances changes their public ip address.
- in general avoid elastic IPs, instead use random public IPs and register DNS names against them.

## Placement Groups

Control over the EC2 infrastructure placement.

3 main types

- Cluster (High performance)
    - **same** server rack (same physical hardware) and same AZ.
    - low latency, high bandwidth solution.
    - higher risk due to same hardware being used.
- Spread (Highly reliability)
    - all instances on **different** server racks therefore can be spread accross AZs. 
- Partition (Distributed Applications)
    - ec2s placed in groups (partitions), these partitions are then placed on **different** racks and therfore can be on multiple AZs.
    - this grouping makes them ideal for large replicated workloads like hadoop, cassandra and kafka.    

## EC2 Hibernate

All in memory (ram) state is preserved therefore the the boot will be much faster as the OS is frozen in state. similar to how the hiberate functions runs on your local system.

RAM dumped onto root EBS volume.

## EC2 Nitro

AWS new underlying virtualisation technology.

For a higher EBS IOPS you need to use Nitro.

## EC2 CPUs

You can specify cores and threads per core when configuring EC2s.

a CPU represents a virtual CPU.
A vCPU = CPU thread.

Certain applications can be optimised by modifiying the vCPUs per CPU and EC2 instance costs can be optimised by reducing core counts.

## EC2 Capacity Reservations

Allows you to reserve EC2 compute resources for specific time frames.

Specify instance types, availability zones and quantity.

## Tenancy

Tenancy defines how EC2 instances are distributed across physical hardware.

- Shared (default) - Multiple AWS accounts may share the same physical hardware.
- Dedicated Instance (dedicated) - Your instance runs on single-tenant hardware.
- Dedicated Host (host) - An isolated server with configurations that you can control.