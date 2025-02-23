# Operations - Deploy

## Deployment 

Deployment and continuous delivery are essential practices in modern DevOps environments. Deployment refers to the process of releasing software to production environments, while continuous delivery ensures that code changes are automatically built, tested, and prepared for release.

Key aspects of deployment include:
- Version control
- Environment management
- Release strategies
- Rollback procedures

The deployment pipeline enables:
- Automated testing
- Infrastructure as code
- Continuous integration
- Monitoring and feedback

## Continuous Deployment

Continuous Deployment (CD) is an advanced DevOps practice where code changes are automatically deployed to production after passing automated tests. This approach eliminates manual intervention in the deployment process.

Key characteristics of CD include:
- Fully automated release process
- Immediate deployment of validated changes
- Zero-touch deployment pipeline
- Real-time monitoring and validation

Benefits of Continuous Deployment:
- Faster time to market
- Reduced deployment risks
- Immediate customer feedback
- Lower operational costs
- Improved developer productivity

CD requires:
- Robust automated testing
- Strong monitoring and alerting
- Feature flags for risk management
- Reliable rollback mechanisms
- High-quality test coverage

## Cloud Strategy

### GitOps
GitOps is a modern software delivery approach that leverages Git repositories as the single source of truth for defining and managing infrastructure, configuration, and application code. In a GitOps release strategy, all changes to the system, including infrastructure provisioning, configuration updates, and application deployments, are made through Git commits and pull requests. The core principles of GitOps include declarative configuration, version control, automation, and continuous delivery.**

- **Declarative configuration**: Express the desired system state in a declarative manner using configuration files by using tools such as PowerShell Desired State Configuration (DSC) or Ansible. Configuration files define how the system should behave, including environment variables, application settings, and service configurations.
- **Infrastructure as Code (IaC)**: Use the declarative configuration approach to define infrastructure components as code by using tools such as Bicep and Azure Resource Manager templates.
- **Version control**: Store all configuration files, infrastructure definitions, and application code, in Git repositories, enabling versioning, change tracking, and collaboration among team members. Use branching strategies and pull requests for managing changes and enforcing code review processes.
- **Continuous Deployment (CD)**: Implement continuous deployment pipelines that automatically deploy changes to the system based on Git commits and pull requests. CI/CD services such as Azure Pipelines or GitHub Actions trigger pipeline executions in response to Git events, such as code merges or branch updates.
- **Automated synchronization**: Deployments are triggered automatically whenever changes are pushed to the Git repository. GitOps tools such as Flux or Argo CD continuously monitor Git repositories for changes and synchronize the desired state of the system with the configuration stored in Git.
- **Immutable infrastructure**: Adopt an immutable infrastructure approach where infrastructure components and application containers are treated as disposable artifacts. Each deployment creates a new immutable instance of the system, reducing configuration drift and ensuring consistency across environments.
- **Rollback and recovery**: Use Git-based workflows to manage rollbacks and recovery procedures in case of deployment failures or unexpected issues. As a result, reverting changes in Git repositories should trigger automatic rollback actions in the CI/CD pipeline, restoring the system to a previous known good state.
- **Observability and Monitoring**: Implement monitoring, logging, and observability practices to track system health, performance metrics, and deployment status. Integrate monitoring tools such as AWS Cloudwatch, Azure Monitor, Datadog, Prometheus, or Grafana with GitOps workflows to gain visibility into system behavior and detect anomalies in real-time.

### Provision and configure target environments
When we focus on the deployment of the Infrastructure, we should first consider the differences between the target environments that we can deploy to:
- On-Premises servers.
- Cloud servers or Infrastructure as a Service (IaaS). For example, Virtual machines or networks.
- Platform as a Service (PaaS) and Functions as a Service (FaaS). For example, Azure SQL Database in both PaaS and serverless options.
- Clusters.
- Service Connections.



### Design and Implementation of Access Control in Cloud-Based DevOps Platforms

- Plan identity provider groups: Leverage your cloud provider’s identity management system (e.g., IAM groups, directory services) to manage user access instead of assigning users directly to DevOps platform groups. Create groups aligned with team roles, project requirements, and access tiers. Structure these groups to reflect the permissions required for distinct teams or workflows.

- Automate group associations: Use automation tools or APIs provided by the DevOps platform to dynamically map identity provider groups to platform-specific groups. Configure rules to synchronize identity groups with project or organization-level groups in the DevOps platform, ensuring appropriate access levels are inherited automatically.

- Leverage default platform groups: Prioritize the use of built-in groups provided by the DevOps platform unless they lack necessary permissions. Avoid modifying default group permissions. If custom groups are required, minimize explicit "Deny" rules to simplify permission management.

- Delegate responsibilities strategically:

- For users managing project-level resources (e.g., repositories, pipelines, service integrations), assign them to project administrator roles or equivalent groups.

- For users overseeing organization/account-level configurations (e.g., policies, processes, shared infrastructure, extensions), assign them to organization/account administrator roles or equivalent groups.

- Review and validate permissions: Conduct periodic access reviews to ensure alignment with least-privilege principles. Use the DevOps platform’s auditing tools to analyze permissions, identify over-provisioned access, and remediate gaps. Incorporate security assessments to detect vulnerabilities.

- Monitor and audit access: Enable the DevOps platform’s native logging and monitoring features to track user activity, permission changes, and resource access. Integrate audit logs with centralized monitoring systems to detect anomalies, investigate incidents, and maintain compliance with security policies.

- This approach ensures consistent access control practices across cloud providers while adapting to platform-specific capabilities.

## Why it Matters