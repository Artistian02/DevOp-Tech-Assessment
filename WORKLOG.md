WORKLOG

Pipeline:
Format, build, test, and security checks can run at the same time. The Docker job waits for them to pass before continuing.

Secrets:
I used GitHub's built in token for GHCR instead of putting credentials in the code. The permissions are limited to what is needed.

Security:
Trivy checks for HIGH and CRITICAL vulnerabilities. "ignore unfixed" keeps issues without an available fix from stopping the build.

Deployment:
The deployment replaces the old container with the new one. A restart policy would help if the container stops unexpectedly.

Scaling:
For more traffic, I would run multiple containers behind a load balancer.
