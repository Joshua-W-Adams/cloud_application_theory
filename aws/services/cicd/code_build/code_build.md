# CodeBuild

Serverless build service.

Operation descrbed in the following diagram:

![](./../../../img/code_build_overview.png)

## Engine

Ues docker under the hood.

## Build Instructions

Specified in 
```
./buildspec.yaml
```

### Phases

- Install - install any dependancies
- Pre-build - commands to execute before build
- Build - actual build commands
- Post build - commands to execute post build (e.g. zip)

### Outputs

outputs artifacts

## Networking (VPC)

By default all CodeBuild containers are lauched OUTSIDE your VPC.

Can connect your CodeBuild to your VPC by specifying:

- VPC ID
- Subnet ID
- Security Group ID