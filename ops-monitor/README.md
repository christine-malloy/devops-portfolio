# Operations - Monitor

## Monitoring for Success
Monitoring and observing is perhaps the single most important phase in the process, arguably ahead of the **plan** which I would put as a close second. This is because the monitoring phase is where you collect data on the system to determine one, its operational health and performance, but more importantly how well the system is addressing the customers' problems. Customer Success must be the chief concern of a DevOps Engineer, as it is certainly the chief concern. of the IT shop. 

## Key Components

### 1. Tooling
- Prometheus
- Grafana
- Nagios
- Datadog
- New Relic

### 2. Logs
- Log aggregation
- Log analysis
- Common logging patterns
- ELK Stack (Elasticsearch, Logstash, Kibana)

### 3. Metrics
- System metrics
- Application metrics
- Business metrics
- SLIs (Service Level Indicators)
- Performance metrics

### 4. Alerts
- Alert definitions
- Alert thresholds
- On-call rotations
- Incident response
- Alert fatigue management

## Best Practices
- Define clear monitoring objectives
- Implement proper alerting thresholds
- Maintain monitoring documentation
- Regular review and updates
- Automate where possible

## Custom Instrumentation

# Traceability, auditability, and security
- four-eyes principle
    - Does at least one other person review the deployed artifact?
    - Is the person that deploys another person the one that writes the code?
- Traceability
    - Can we see where the released software originates from (which code)?
    - Can we see the requirements that led to this change?
    - Can we follow the requirements through the code, build, and release?
- Auditability
    - Can we see who, when, and why the release process changed?
    - Can we see who, when, and why a new release has been deployed?
When looking at an appropriate Release Management tool, you can consider the following:
  - Does it integrate with your company's Active Directory?
  - Can you set up roles and permissions?
  - Is there a change history of the release pipeline itself?
  - Can you ensure the artifact didn't change during the release?
  - Can you link the requirements to the release?
  - Can you link source code changes to the release pipeline?
  - Can you enforce approval or the four-eyes principle?
  - Can you see the release history and the people who triggered the release?
