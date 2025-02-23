# Development - Code

## Programming and Hacking 
The implementation phase, where abstract design specifications transform into tangible, working software. During this phase, teams focus on creating robust unit test suites from the project's inception, ensuring code reliability and maintainability. Equally important is establishing development environments that accurately mirror production conditions while protecting sensitive customer data.

Success in the coding phase hinges on several key elements. Teams must prioritize building comprehensive test suites early in development, maintain consistent development environments across the team, and leverage containerization for efficient dependency management. Additionally, adherence to team coding standards and implementation of automated quality checks ensure code consistency and reliability.

When executed properly, a well-structured development phase yields significant benefits. New team members can onboard faster with standardized environments and clear documentation. Production issues decrease through thorough testing and environment parity. Most importantly, automated testing and consistent practices help maintain high code quality across the entire development team.

## I wish I had
When developing a new service, I always push to have the local environment set up be as close as possible to the remote set up. This to reduce complexities and context switching when moving from environments, maintain manifests between environments, and promote environment parity. Often times bugs can be very challenging to fix if they can't be replicated in local environments, and vice versa. It's important to ensure the engineers can standup an idempotent and reliable environment to foster efficient development.

## Languages
In software development, code is written following different paradigms, primarily:
- **Functional Programming**: Languages like Haskell, Erlang
- **Object-Oriented Programming**: Java, C++, Python
- **Hybrid Approaches**: Scala, Kotlin

Common language ecosystems and common use cases:
- JavaScript/Node.js: Web, serverless
- Python: Data science, automation, web scraping
- Java: Enterprise applications
- [Golang](https://go.dev/) - [portfolio docs](./golang/README.md): produced by google, broad use cases including CLI apps, automation tooling, cloud tooling, systems requiring high concurrency
- Rust: Systems programming
- C/C++: Operating systems, embedded systems
- Ruby: Web development, scripting
- PHP: Web applications, CMS
- Swift/Kotlin: Mobile development
- TypeScript: Large-scale JavaScript applications
- R: Statistical computing
- SQL: Database management
- Scala: Big data processing
- Julia: Scientific computing
- Perl: Text processing, system administration

**Note** - languages aren't necessarily married to a use case, however some lend themselves better to certain task than others due to various language features. For example, python is often favored for data science since it essentially provides a human readable language wrapper around the c math library, allow for rapid development of performant applications.

Development Environment Essentials:
1. **Code Editors/IDEs**
  - VSCode, IntelliJ, Eclipse
  - Language-specific plugins
  - Git integration

2. **Testing Tools**
  - Test-Driven Development (TDD)
  - Unit testing libraries (developed with TDD to ensure most reliable testing suite)
  - Integration testing suites (running database queries to test system boundaries)
  - End to end testing frameworks (Selenium)

3. **Local Development Stack**
  - Docker containers
  - Docker Compose for building a simple stack of service container with additional data sources such as a relational database like mysql
  - Minikube for Kubernetes development

4. **Cloud Development**
  - Local-to-cloud connections
  - Environment parity
  - Secrets management using cloud provider profiles
  - Mock services, AWS localstack
  - click ops for rapid development

Best Practices:
- Mirror production environment locally
- Use generated test data that resembles live customer data (consider sanitizing production data, but this comes with risks)
- Implement CI/CD pipelines