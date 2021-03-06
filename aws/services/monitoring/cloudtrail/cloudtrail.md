# CloudTrail

Compliance, governance and auditing service. Watches all **events and API calls** on your AWS account.

e.g. who deleted an EC2 instance? etc.

The operation of cloud trail can best be explained by the following diagram:

![](./../../../img/cloudtrail.png)

## Events

### Management Events

Any operations that are performed on AWS resources.

### Data Events

E.g. S3 object level activities, lambda executions.

### Insight Events

Analyses your cloud trail events and trys to detect unusual behaviour.

## Event Retention

- Stored for 90 days by default
- Longer term storage in S3 possible