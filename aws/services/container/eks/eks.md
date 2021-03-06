# Elastic Kubernetes Service (EKS)

Service to launch a managed kubernetes cluster on AWS.

Kubernetes is an **open source** container management application. Developed by Google.

Allows clusters to be cloud-agnostic. i.e. cloud independant / cross cloud.

## Architecture

- EKS
    - Cluster
        - EKS pods
            - EKS node
                - Container

### Defintions
                
EKS pods: Collection of multiple pods 
EKS nodes: wrapper to a single container (docker or otherwise)

## Cluster Management

Support manual (EC2 ASGs) and automated (Fargate) management of instance clusters.