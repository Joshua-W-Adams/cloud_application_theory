# Elastic Container Registry (ECR)

Service for managing **private** docker images.

## Public Docker Image Repository

Public images are managed on the following website.

https://hub.docker.com

You can find an image for pretty much anything here.

Good for getting base images which you customise with your application code.

## CLI Login

### CLI v1

```
aws ecr get-login
```

### CLI v2

```
aws ecr get-login-password | docker login ...
```