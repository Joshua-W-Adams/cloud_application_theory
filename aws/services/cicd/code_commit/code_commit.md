# CodeCommit

Service for managing a .git repository.

Notes:
- Privately .git repositories.
- Exists only in the AWS Cloud account.

## Security

Login to code commit repository with git command line. Supports authentication via:
- SSH
- HTTPS
- MFA

## Cross Account Access

Create an IAM role in your account. Then let the other user use STS with the AssumeRole API to access the repo.