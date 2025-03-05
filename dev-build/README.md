# Development - Build

## Bringing it all together
The build phase is a pivotal stage where code changes are integrated, compiled, and validated within the broader development ecosystem. Many process bottlenecks are often found in this phase, so its important to pay special care and attention. This part of the cycle involves:

- Compiling source code into executable artifacts
- Running comprehensive test suites
- Validating code quality and standards
- Checking dependency compatibility
- Creating deployable packages
- Generating documentation and reports
- Validating system integration points
- Ensuring build reproducibility

This systematic approach helps maintain code quality and stability while preparing deliverables for deployment.

## Continuous Integration
Continuous Integration (CI) enables automated building and testing of code changes:

- Code changes trigger automated builds
- Tests run automatically on each commit
- Early detection of integration issues
- Frequent validation of code quality
- Automated feedback to developers
- Ensures main branch stays stable
- Reduces integration problems
- Supports rapid development cycles

## Technologies and Components

## CI Platforms
- Jenkins
- Travis CI
- Circle CI
- Concourse CI
- Github Actions
- AWS Code Build/Pipeline

## Build Pipeline
Key automated steps:
1. Code checkout
2. Dependency installation
3. Static analysis
4. Unit testing
5. Integration testing
6. Environment deployment
7. End-to-end validation

## Test Environments - Branch Builds
A critical need and common ask from engineers is automations and integrations to facilitate building ephemeral test environments that fully integrate their code into a temporary test version of the system, without deploying it to lower environments used for testing. Testing in lower environments such as a "dev", "qa", or "staging" should be a focus in other phases such as **release** and **deploy**.

Goals:
For each feature branch:
- Ephemeral test environments automatically provisioned
- Clean isolated testing environment per branch
- Environments torn down after merge/close
- Infrastructure as code ensures consistency
