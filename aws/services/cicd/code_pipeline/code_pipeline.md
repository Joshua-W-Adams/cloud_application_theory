# CodePipeline

Service to orchestrate all your CI/CD operations.

## Structure

```
Stage 1
    Action Group 1
        Action 1
        Action 2
    ...
...
```

Stages can be whatever you want. For Example.
- Build
- Test
- Deploy
- Load Test
- etc.

Actions are single actions to be performed in each stage, for example, manual approval, deploy with Beanstalk etc.

## Artifacts

Files that are output by each stage and piped into the next.

Separated into input and output artifacts.