# AWS Infrastructure

A general overview of the global AWS infrastructure that allows AWS to provide its services.

## AWS Regions 

A cluster of data centers in a specific location e.g. sydney, london etc.

You will pick a region based on the following factors:

- Compliance - governemnt and legal requirements
- Proximity  - reduce lag
- Available Services - Not all regisions have the same services
- Pricing - varies from region to region

*Memorisation Note: "Australia wearing a CAPP."*

## AWS Availability Zones

An **isolated** set of one or more data centers with redundant power, networking and connectivity.

![](./../img/aws_regions_and_availability_zones.png)

### AWS Edge Locations

A location that AWS Cloud front uses to cache your static content. To enable faster delivery to worldwide users.

### AWS Points of Presence 

An edge location with less sophisticated infrastructure.
