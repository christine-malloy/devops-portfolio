# Operations - Release

## Release Management
The purpose of the release phase is to prepare releases to deployed environments, starting with lower environments for testing, and eventually ending with deploying to production for live release. Pipeline reliability and robustness is paramount for this phase. Without a strong CI/CD story, **release** will become a bottleneck for the entire rest of the process and cause massive delays in development.


## CI/CD

Release is about tying the Build phase (Continuous Integration) with the Deploy Phase (Continuous Deployment)

### Continuous Integration
Continuous Integration (CI) enables automated building and testing of code changes:

- Code changes trigger automated builds
- Tests run automatically on each commit
- Early detection of integration issues
- Frequent validation of code quality
- Automated feedback to developers
- Ensures main branch stays stable
- Reduces integration problems
- Supports rapid development cycles

### Continuous Development
Continuous Development (CD) streamlines software delivery through automation:

- Automates release deployment processes
- Enables rapid and reliable deployments
- Maintains consistent deployment procedures
- Reduces manual intervention and errors
- Supports multiple deployment environments
- Facilitates rollback capabilities
- Ensures repeatable release processes
- Speeds up time-to-market
- Improves development efficiency

## Platform Deploy - Releasing a Microservices based system

When releasing a microservices based system, its essential to coordinate the release across the related services and ensure versions are compatible with each other

### Backwards compatibility

### Deprecations

### 

## Rolling back a Release

## Technologies
Common CI/CD technologies include:

- [Jenkins](https://www.jenkins.io/): Open-source automation server
- [GitLab CI/CD](https://docs.gitlab.com/ee/ci/): GitLab's integrated CI/CD solution
- [GitHub Actions](https://github.com/features/actions): GitHub's automation platform
- [CircleCI](https://circleci.com/): Cloud-native CI/CD platform
- [Travis CI](https://travis-ci.org/): CI/CD service for open source projects
- [Concourse CI](https://concourse-ci.org/): 
- [Azure DevOps](https://azure.microsoft.com/en-us/products/devops): Microsoft CI/CD service with task boards [portfolio docs](./ado/README.md)
- [AWS CodePipeline](https://aws.amazon.com/codepipeline/): AWS CI/CD service
- [TeamCity](https://www.jetbrains.com/teamcity/): JetBrains CI/CD solution
- [Bamboo](https://www.atlassian.com/software/bamboo): Atlassian's CI/CD server
- [ArgoCD](https://argoproj.github.io/cd/): Declarative GitOps CD tool
- [Tekton](https://tekton.dev/): Cloud-native CI/CD framework
- [Spinnaker](https://spinnaker.io/): Multi-cloud continuous delivery platform