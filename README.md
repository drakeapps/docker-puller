# Docker image puller

![](/img/logo.png)

Due to [the new Docker Hub retention policy](https://www.docker.com/pricing/retentionfaq) a container image that has not been either pushed or pulled from the image repository in 6 or more months will be scheduled for deletion. Only accounts that are on the Free individual or organization plans will be subject to image retention limits.

![](/img/image_retention_policy.png)

This repository contains [the github workflow](/.github/workflows/main.yml) for pulling Docker images from a specific account so its images won't be counted as inactive. To run the flow you'll need to clone this repository and specify "UNAME" and "UPASS" secrets (which should be yours Docker Hub username and password):

![](/img/workflow_secrets.png)

Flow triggers by push or a schedule and consist two steps. At first it logins to Docker Hub and then it pulls all images, which contains Docker Hub username:

![](/img/flow_steps.png)

If the run was successful you can validate a result by checking "Actions" section on your repository:

![](/img/action_run.png)
