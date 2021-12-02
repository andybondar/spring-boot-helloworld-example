# Using CI to build and run the Application
## GitHub Actions
Simply put, `GitHub Actions` is a hosted platform to automate `software development workflows`. Including, but not limited to `CI/CD workflows`.
Here are some examples of the `software development workflows`:
* Processing request from GitHub user wnating to join the project as a contributor (verification of his or her identity, granting access, etc.)
* Processing new pull request (running some tests, assigning it to somebody who can review, reporting status to its creator, merging it to master branch when it's ready, etc)
* Processing new issue from user (sorting and prioritizing the issue, assigning to someone who can handle it, reporting it's statut, etc)
* etc.

Basic concept of the `GitHub Actions` - it listents to the `Events` that happen IN or TO your repository, and it take pre-defined `Actions` on those events.
In this tutorial we will use `GitHub Actions` to automate a CI/CD workflow.

Please review simple workflow defined in the [.github/workflows/container_image.yml](.github/workflows/container_image.yml).


## CircleCI
TBD

## AWS CodeBuild
TBD

## GCP CloudBuild
TBD

## Jenkins
TBD

## GitLab CI
TBD