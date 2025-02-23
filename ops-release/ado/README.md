# ADO

## Overview

### Azure Pipelines key terms
- Agent - When your build or deployment runs, the system begins one or more jobs. An agent is installable software that runs a build or deployment job.
    - Microsoft-hosted agent - If your pipelines are in Azure Pipelines, then you've got a convenient option to build and deploy using a Microsoft-hosted agent.
    - Self-hosted agent - An agent that you set up and manage on your own to run build and deployment jobs is a self-hosted agent.
- Artifact - An artifact is a collection of files or packages published by a build. Artifacts are made available for the tasks, such as distribution or deployment.
- Build - A build represents one execution of a pipeline. It collects the logs associated with running the steps and the test results.
- Deployment Target - A deployment target is a virtual machine, container, web app, or any service used to host the developed application. A pipeline might deploy the app to one or more deployment targets after the build is completed and tests are run.
- Job - A build contains one or more jobs. Most jobs run on an agent. A job represents an execution boundary of a set of steps. All the steps run together on the same agent.
    - Agent pool jobs - The most common types of jobs. The jobs run on an agent that is part of an agent pool. Instead of managing each agent individually, you organize agents into agent pools. An agent pool defines the sharing boundary for all agents in that pool.
    - Container jobs - Similar jobs to Agent Pool Jobs run in a container on an agent part of an agent pool.
    - Deployment group jobs - Jobs that run on systems in a deployment group.
    - Agentless jobs - Jobs that run directly on the Azure DevOps. They don't require an agent for execution. It's also-often-called Server Jobs.
- Pipeline - A pipeline defines the continuous integration and deployment process for your app. It's made up of steps called tasks.
- Release - When you use the visual designer, you can create a release or a build pipeline. A release is a term used to describe one execution of a release pipeline. It's made up of deployments to multiple stages.
- Stage - Stages are the primary divisions in a pipeline: "build the app," "run integration tests," and "deploy to user acceptance testing" are good examples of stages.
- Task - A task is the building block of a pipeline. For example, a build pipeline might consist of build and test tasks. A release pipeline consists of deployment tasks. Each task runs a specific job in the pipeline.
- Trigger - A trigger is set up to tell the pipeline when to run. You can configure a pipeline to run upon a push to a repository at scheduled times or upon completing another build. All these actions are known as triggers.

### Azure Pipelines Gate Types:
- Invoke Azure Function: Trigger the execution of an Azure Function and ensures a successful completion.
- Query Azure Monitor alerts: Observe the configured Azure Monitor alert rules for active alerts.
- Invoke REST API: Make a call to a REST API and continues if it returns a successful response.
- Query work items: Ensure the number of matching work items returned from a query is within a threshold.
