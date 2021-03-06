# Cloud Development Kit (CDK)

Infrastructre as **Native** Code for all AWS services.

CDK generates CloudFormation code.

## Process

1. Initialise your cdk project with 

```shell
cdk init
```

2. Define your infrastructure as code using the langauge of your choice

3. Bootstrap your CDK project and initialise all the required AWS services

```shell
cdk bootstrap
```

4. Convert your native IAC to CloudFormation .yaml IAC

```shell
cdk synth
```

5. Deploy .yaml to CloudFormation

```shell
cdk deploy
```