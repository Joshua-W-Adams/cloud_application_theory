# AWS Application Programming Interface (API)

AWS provides the following 3 options for accessing your AWS account. i.e. communicating with the underlying AWS API.

1. Management Console
2. CLI - access aws via command line terminals e.g. Windows Command Prompt
3. SDK - access aws via programming languages e.g. JavaScript via Node.js
 
## AWS Access Keys

Keys that allow access to your IAM account via the AWS CLI or SDK. They have two components:

1. Access Key ID (your user name)
2. Secret Access Key (your password)

## AWS Cloud Shell

Online CLI.

Note: Cloud shell operates like your local computer shell. For example the environment is persisted...creating a file in cloud shell will be saved.

## Command Line Interface (CLI)

### Dry Run

You can run a cli command with the **--dry-run** flag to confirm if the command will work and not actually run the command. This is a good way to see if you have the appropriate permissions to run a command.

### MFA with CLI

You can authenticate with MFA via the CLI using the STS GetSessionToken API Call as follows.
```
aws sts get-session-token
```

## API Rate Limits

Limits on how many requests can be performed per second on an API.

## Exponential Backoff

Strategy to retry server (5XX) errors by doubling the time between each retry API call.

This is a good strategy to handle Throttling Exceptions (too many API calls).

## Credentials 

### Provider Chain

Heirarchy in which the AWS tool you are using to access the API will search for credentials.

#### CLI Credentials Provider Chain

1. Command Line options
2. Environment variables
3. CLI credentials file
4. CLI configuration file
5. Credentials container (ECS)
6. Instance profile credentials

### Best Practice

Never store credentials in your code. Credentials should always be inhereted from the credentials provider chain.

If working within AWS use IAM roles.
If working outside user environment variables.

## Manually Signing AWS API Requests

Only required if not using the SDK, CLI or management console.

The Sigv4 process can be used to sign them. which is very complicated. All we really need to know is the signed credentials can be manually passed by the following two options:
- HTTP header
- query strings (i.e. signed URLs)

## Service Quotas

How many resources we can run of something.