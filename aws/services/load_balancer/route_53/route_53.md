# AWS Route 53

A Domain Name Server AND registrar managed by AWS.

Can be used for public AND private domains.

## Domain Name Server (DNS)

A set of rules and records which allows clients to understand how to get to a server from a domain name.

## Important records:

- A:        hostname to ipv4
- AAAA:     hostname to ipv6
- CNAME:    hostname to another hostname
    - does not work for the zone apex (domain.com)
- Alias:    hostname to an AWS resource
    - free 
    - can be used to map to the AWS hosted zone apex (root domain)
- NS:       name server, specifys what dns server to use for resolving names to ips

AWS supports
- public domains
- private domains (internal domains on AWS)

Note:
- nslookup - windows command to lookup ip address mapped to a domain name

### Time To Live (TTL)

Time to cache the response from a DNS server. Its purpose is to prevent overloading the DNS.

*Note: Web browser looks in own cache for ip address for duration of the TTL.*

### Architecture

The process by which a DNS works is as follows:

![](./../../../img/dns_process.png)

## DNS Routing Policies

7 routing policies (rulesets) are supported by AWS

### Simple

Use when you need to redirect to a single resouce.

### Weighted

Control the % of requests that go to a specific endpoint.

e.g. 70/20/10 accross 3 instances.

Use cases:
- deploy a new app, you can test 1% of traffic onto one instance.

### Latency

Redirect user to the server with the least latency.

Process:
1. Create a A record for each server 
2. Assign a latency policy based on AWS region

### Failover

Route 53 will automatically failover to a secondary server if the health check on the primary server fails.

### Geolocation

Direct user based off their location.

### Geoproximity

Route uses to resources based on geo location of users and bias value set.

Bias value used to increase / decrease region sizes so more or less traffic will go to each region.

### Multi-Value

Web browser will randomly pick one of provided A records. 

Used to do some level of client side load balancing.

*Note: Health checks can be assigned and if one fails the DNS wont send its record to the client. Also if the client cant connect to one server it will attempt to connect to one of the other values.*

## Health Checks

Domain name level health checking configuration.

unhealthy = fails 3 health checks
healthy = passes 3 health checks

## Registrar

Registrar is an organisation that manages the reservation of domain names.

### 3rd Party Registrar

AWS supports 3rd party registrars and can be setup as follows:

1. Buy doman name
2. Create hosted zone in Route 53
3. Get Name Server (NS) details on AWS
3. Update NS record on 3rd party DNS to use Route 53 name servers