# AWS Config

General configuration of all your AWS services. So you can monitor for compliance and non compliant resources.

## Config Rules

Rules can be 
- All EC2 instance must be t2.micro
- All ALBs must have HTTPs certificates assigned
- etc.

*Note: Do not replace actions from happening like IAM policies. They simplify inform of non compliance resources.*

## Remediations

Manual or automated actions you can perform to fix non-compliant (rule failing) resources.

For example
Watch AWS access keys for a validity duration longer than 90 days. If longer than 90 days. Remediation action will fire to disable these keys.

Can connect to Event Bridge to create custom events which can be piped into specific AWS services such as lambda.