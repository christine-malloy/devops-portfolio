# Gitops

As previously mentioned, gitops is a philosophy and methodology around managing and maintained all aspects of an IT organization through git repositories using the git PR process.

## The Pull Request Process

## What can be managed by Git?

Short answer, *everything*.

It might sound like hyperbole, but in fact it all you need is the right solution and technical creativity.

Gitops is about automations. Thus, if it can scripted, it can be built into an automated flow, and that has real impact on developer hours.

An obvious starting example would be service deployments. That's usually one of the first areas automated deployments will be built, since app deployments are typically one of the most frequently changing systems, especially in greenfield projects or when there is a high rate of feature dev (as opposed to bug fixes/maintenance).

However, think of what other systems might change on a frequent basis, and other areas of automation:

- **Documentation**:  Keep docs such as Swagger, Confluence, Sharepoint in sync with code and infra changes.
  - **Tools**: MkDocs, Docusaurus, Sphinx.
  - **GitOps Practices**:
    - Treat documentation as code (e.g., Markdown in Git).
    - Auto-generate docs from OpenAPI specs or IaC.
- **Cloud Infrastructure**
  - **Tools**: Terraform, AWS CDK, Crossplane, Pulumi.
  - **GitOps Practices**:
    - Store IaC definitions in Git (e.g., Terraform manifests).
    - Automate cloud resource provisioning via CI/CD pipelines.
    - Use pull-based reconciliation (e.g., Flux Terraform Controller).
- **Environment Orchestration**: Spin up/down ephemeral environments (e.g., per PR, per feature).
  - **Tools**: Argo CD, Loft, vcluster.
  - **GitOps Practices**:
    - Define environments as code in Git (e.g., Kubernetes namespaces).
    - Auto-delete environments after PR merge/close.
- **Databases**:
  - **Tools**: Liquibase, Flyway, Velero.
  - **GitOps Practices**:
    - Version-controlled database migrations in Git.
    - Automate backup/restore workflows via Git triggers.
- **Ticketing**:
- **Observability Platform**: monitoring tools, dashboards, alerts, 
  - **Tools**: Prometheus, Grafana, Loki, OpenTelemetry.
  - **GitOps Practices**:
    - Store dashboards/alerts as code (e.g., Grafana JSON in Git).
    - Automate deployment of monitoring agents via GitOps operators.
- **DR Solution**: Automated backups, failover, and DR testing.
  - **Tools**: Velero, Kasten, Restic.
  - **GitOps Practices**:
    - Define DR plans as code (e.g., backup schedules in Git).
    - Trigger DR drills via GitOps workflows.
- **CI/CD Pipelines**: indeed, CI/CD process can and should be applied to the pipelines themselves. 
  - **Tools**: GitHub Actions, GitLab CI, Argo Workflows, Tekton.
  - **GitOps Practices**:
    - Trigger pipelines on Git commits/PRs.
    - Use Argo CD/Flux for declarative deployment sync.
    - Automated rollbacks on failed deployments (via Git revert).
- **Configuration Management**: server config, environment variables, feature flags
  - **Tools**: Helm, Kustomize, Jsonnet, Ansbile.
  - **GitOps Practices**:
    - Version-controlled configuration files in Git.
    - Automate config propagation across environments (e.g., staging → production).
- **Security and Compliance** - enforce policies, vulnerability scanning, and compliance checks
  - **Tools**: OPA Gatekeeper, Kyverno, Trivy, Checkov.
  - **GitOps Practices**:
    - Encrypt secrets in Git (e.g., Mozilla SOPS + GitOps).
    - Automate secret updates via CI/CD (e.g., Vault Agent Sidecar).
- **Secrets Management**: Securely store and rotate credentials, API keys, SSH keys certificates, etc.
  - **Tools**: Sealed Secrets, HashiCorp Vault, AWS Secrets Manager.
  - **GitOps Practices**:
    - Encrypt secrets in Git (e.g., Mozilla SOPS + GitOps).
    - Automate secret updates via CI/CD (e.g., Vault Agent Sidecar).
- **Networking and Service Mesh**: Configure service meshes, ingress, and network policies.
  - **Tools**: Istio, Linkerd, NGINX Ingress Controller.
  - **GitOps Practices**:
    - Define routing rules and policies in Git.
    - Automate certificate management (e.g., Cert-Manager + Let’s Encrypt).
- **Cost Optimization**: Autoscaling, resource right-sizing, and budget alerts.
  - Tools: Keda, Goldilocks, Kubecost.
  - **GitOps Practices**:
    - Autoscaling policies in Git (e.g., HPA configurations).
    - Automate cost reports and alerts via GitOps-triggered jobs
- **Collaboration & Governance**:PR reviews, audit trails, and access controls.
  - Tools: GitHub CODEOWNERS, Open Policy Agent (OPA).
  - **GitOps Practices**: 
    - Enforce peer reviews via Git merge requests.
    - Audit changes via Git history and signed commits.

## How much Automation is too much Automation?

A good rule of thumb is to take the time to build an automation whenever you think you will perform a given manual operation 2 or more times a year. Even at that relatively infrequent level, productivity gains can be realized. Consider:

An engineer might spend 2 hours performing that manual operation. They might be able to build an automation in a day, so 8 hours of work to save 2 each time. Sure, that will mean that it will take 2 years, at a rate of 2 operations a year, for the gains to be realized, but consider hidden benefits:

- reduced context switching: on a good day it might take that engineer 2 hours, but on other days, especially if its been six months since they last did the operation, it may take them an extra hour or two to rebuild context on how to perform the automation, this magnifying the timeline
- reduced error rate: every time a operation is performed manually by a human operator, there is a chance of failure. Humans are good at building and understanding new things, but not so good at repetitive tasks 
- force multiply: the operation can effectively be abstracted away from the one engineer who knew how to perform it manually, thus eliminating knowledge silos, and empowering the team to ensure the success of the operation. An script is easier to audit and reverse engineer than sparse and outdated documentation.

Indeed, building an automation helps realize powerful gains in many ways. And the effects are more dramatic the larger your company and team is. The more complexities and overhead that can be abstracted, the more time engineers can focus on tasks they wish they could catch up on, like fundamental platform improvements, testing, refactoring, reducing tech debt, devops optimizations, etc.

