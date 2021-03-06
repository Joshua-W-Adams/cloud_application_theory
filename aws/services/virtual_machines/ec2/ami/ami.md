# Amazon Machine Image (AMI)

Customisation of an EC2 instance. Effectively a copy of an EC2 instance and attached EBS.

AMIs are created from underlying EC2 snapshots.

Types:
- Public AMI (AWS provided)
- Private AMI (made by you)
- AWS marketplace (made by someone else)

Simply right click and "create image" on running ec2 instance.

*Note: Typical uses are a pre-boostrapped EC2 where a whole bunch of software has been installed. Using an AMI means that this software will not need to be installed on boot and therefore the new EC2 starts faster.*