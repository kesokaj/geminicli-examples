# Gemini CLI Examples

This repository contains examples of custom commands and settings for the Gemini CLI.

## Getting Started with Gemini CLI

The Gemini CLI is a powerful tool that allows you to interact with the Gemini model in your terminal. It can be customized with your own commands and settings to streamline your workflow.

### Documentation

Here are some useful links to the official Gemini CLI documentation:

*   [**Gemini CLI Quickstart**](https://geminicli.com/docs/): Let’s get started with Gemini CLI.
*   [**Installation**](https://geminicli.com/docs/installation): Install and run Gemini CLI.
*   [**Authentication**](https://geminicli.com/docs/authentication): Authenticate Gemini CLI.
*   [**Configuration**](https://geminicli.com/docs/configuration): Information on configuring the CLI.
*   [**Examples**](https://geminicli.com/docs/examples): Example usage of Gemini CLI.

### Installation

The standard method to install and run Gemini CLI uses npm:

```bash
npm install -g @google/gemini-cli
```

Once Gemini CLI is installed, run Gemini CLI from your command line:

```bash
gemini
```

### Authenticate

To begin using Gemini CLI, you must authenticate with a Google service. The most straightforward authentication method uses your existing Google account:

1.  Run Gemini CLI after installation:
    ```bash
    gemini
    ```
2.  When asked “How would you like to authenticate for this project?” select `1. Login with Google`.
3.  Select your Google account.
4.  Click on `Sign in`.

### Configuration

The Gemini CLI is configured through a `settings.json` file located in your home directory. This file allows you to customize various aspects of the CLI, such as the model you use, the tools you have available, and the appearance of the UI.

## `settings.json` Explained

The `settings.json` file in this repository is an example of how you can configure the Gemini CLI. Here's a breakdown of some of the key settings:

*   **`context`**: This section allows you to define which files and directories the Gemini CLI should be aware of when you're working on a project. You can specify files to include and exclude, which helps to provide the model with the right context for your requests.
*   **`experimental`**: This section contains settings for experimental features. In this example, `useModelRouter` and `codebaseInvestigatorSettings` are enabled, which can improve the model's ability to understand and navigate your codebase.
*   **`mcpServers`**: This section allows you to configure "Managed Component Providers" (MCPs), which are external tools that the Gemini CLI can use. In this example, `context7`, `gcloud`, `godocs`, and `terraform` are configured, giving the CLI the ability to interact with these services.
*   **`tools`**: This section allows you to configure the behavior of the tools that the Gemini CLI uses. In this example, `autoAccept` is set to `true`, which means that the CLI will automatically accept tool calls without prompting for confirmation.

## Custom Commands

The Gemini CLI allows you to create your own custom commands by creating `.toml` files in the `commands` directory. These files define a prompt and a description for the command, and you can use them to create shortcuts for common tasks.

### Example Commands

This repository contains several example commands in the `commands` directory:

*   **`ask_gemini_source.toml`**: This command is designed to help new engineers understand the Gemini CLI codebase. It instructs the model to consult the documentation and source code to answer questions about the project.
*   **`demo/joke.toml`**: This is a simple command that asks the model to tell a dad joke. It demonstrates how you can use custom commands to have a bit of fun with the Gemini model.
*   **`go/build.toml`**: This command is a more complex example that helps you build a Go application. It can either follow a `PLAN.md` file or build the application from scratch based on your request. It also demonstrates how you can use the CLI to run shell commands and interact with other tools.

### Creating Your Own Commands

To create your own custom command, simply create a new `.toml` file in the `commands` directory. The file should have the following format:

```toml
description = "A brief description of your command"
prompt = """
A more detailed prompt that tells the model what to do.
You can use {{args}} to pass arguments to your command.
"""
```

Once you've created your command, you can run it from the Gemini CLI by typing `/` followed by the name of your command file (without the `.toml` extension). For example, to run the `joke.toml` command, you would type `/demo:joke`.

## Conclusion

This repository provides a starting point for customizing the Gemini CLI to fit your needs. By creating your own custom commands and configuring the `settings.json` file, you can turn the Gemini CLI into a powerful tool that helps you work more efficiently.

## Agent Contexts

Agent contexts allow you to specialize the behavior of the Gemini CLI for specific tasks. By loading a context file, you can provide the model with a specific persona, skills, and instructions, making it more effective for the task at hand.

### How to use Agent Contexts

You can load an agent context at the beginning of your conversation by referencing the context file in the settings.json file. The Gemini CLI will then adopt the persona and instructions defined in that file.

### Agent Context Categories

This repository includes a wide variety of pre-built agent contexts in the `agent_context_example` directory. These are organized into the following categories:

*   [Core Development](./agent_context_example/01-core-development)
*   [Language Specialists](./agent_context_example/02-language-specialists)
*   [Infrastructure](./agent_context_example/03-infrastructure)
*   [Quality & Security](./agent_context_example/04-quality-security)
*   [Data & AI](./agent_context_example/05-data-ai)
*   [Developer Experience](./agent_context_example/06-developer-experience)
*   [Specialized Domains](./agent_context_example/07-specialized-domains)
*   [Business & Product](./agent_context_example/08-business-product)
*   [Meta & Orchestration](./agent_context_example/09-meta-orchestration)
*   [Research & Analysis](./agent_context_example/10-research-analysis)

### Core Development

*   [API Designer](./agent_context_example/01-core-development/api-designer.md)
*   [Backend Developer](./agent_context_example/01-core-development/backend-developer.md)
*   [Electron Pro](./agent_context_example/01-core-development/electron-pro.md)
*   [Frontend Developer](./agent_context_example/01-core-development/frontend-developer.md)
*   [Fullstack Developer](./agent_context_example/01-core-development/fullstack-developer.md)
*   [GraphQL Architect](./agent_context_example/01-core-development/graphql-architect.md)
*   [Microservices Architect](./agent_context_example/01-core-development/microservices-architect.md)
*   [Mobile Developer](./agent_context_example/01-core-development/mobile-developer.md)
*   [UI Designer](./agent_context_example/01-core-development/ui-designer.md)
*   [Websocket Engineer](./agent_context_example/01-core-development/websocket-engineer.md)
*   [Wordpress Master](./agent_context_example/01-core-development/wordpress-master.md)

### Language Specialists

*   [Angular Architect](./agent_context_example/02-language-specialists/angular-architect.md)
*   [C++ Pro](./agent_context_example/02-language-specialists/cpp-pro.md)
*   [C# Developer](./agent_context_example/02-language-specialists/csharp-developer.md)
*   [Django Developer](./agent_context_example/02-language-specialists/django-developer.md)
*   [.NET Core Expert](./agent_context_example/02-language-specialists/dotnet-core-expert.md)
*   [.NET Framework 4.8 Expert](./agent_context_example/02-language-specialists/dotnet-framework-4.8-expert.md)
*   [Flutter Expert](./agent_context_example/02-language-specialists/flutter-expert.md)
*   [Golang Pro](./agent_context_example/02-language-specialists/golang-pro.md)
*   [Java Architect](./agent_context_example/02-language-specialists/java-architect.md)
*   [JavaScript Pro](./agent_context_example/02-language-specialists/javascript-pro.md)
*   [Kotlin Specialist](./agent_context_example/02-language-specialists/kotlin-specialist.md)
*   [Laravel Specialist](./agent_context_example/02-language-specialists/laravel-specialist.md)
*   [Next.js Developer](./agent_context_example/02-language-specialists/nextjs-developer.md)
*   [PHP Pro](./agent_context_example/02-language-specialists/php-pro.md)
*   [Python Pro](./agent_context_example/02-language-specialists/python-pro.md)
*   [Rails Expert](./agent_context_example/02-language-specialists/rails-expert.md)
*   [React Specialist](./agent_context_example/02-language-specialists/react-specialist.md)
*   [Rust Engineer](./agent_context_example/02-language-specialists/rust-engineer.md)
*   [Spring Boot Engineer](./agent_context_example/02-language-specialists/spring-boot-engineer.md)
*   [SQL Pro](./agent_context_example/02-language-specialists/sql-pro.md)
*   [Swift Expert](./agent_context_example/02-language-specialists/swift-expert.md)
*   [TypeScript Pro](./agent_context_example/02-language-specialists/typescript-pro.md)
*   [Vue Expert](./agent_context_example/02-language-specialists/vue-expert.md)

### Infrastructure

*   [Cloud Architect](./agent_context_example/03-infrastructure/cloud-architect.md)
*   [Database Administrator](./agent_context_example/03-infrastructure/database-administrator.md)
*   [Deployment Engineer](./agent_context_example/03-infrastructure/deployment-engineer.md)
*   [DevOps Engineer](./agent_context_example/03-infrastructure/devops-engineer.md)
*   [DevOps Incident Responder](./agent_context_example/03-infrastructure/devops-incident-responder.md)
*   [Incident Responder](./agent_context_example/03-infrastructure/incident-responder.md)
*   [Kubernetes Specialist](./agent_context_example/03-infrastructure/kubernetes-specialist.md)
*   [Network Engineer](./agent_context_example/03-infrastructure/network-engineer.md)
*   [Platform Engineer](./agent_context_example/03-infrastructure/platform-engineer.md)
*   [Security Engineer](./agent_context_example/03-infrastructure/security-engineer.md)
*   [SRE Engineer](./agent_context_example/03-infrastructure/sre-engineer.md)
*   [Terraform Engineer](./agent_context_example/03-infrastructure/terraform-engineer.md)

### Quality & Security

*   [Accessibility Tester](./agent_context_example/04-quality-security/accessibility-tester.md)
*   [Architect Reviewer](./agent_context_example/04-quality-security/architect-reviewer.md)
*   [Chaos Engineer](./agent_context_example/04-quality-security/chaos-engineer.md)
*   [Code Reviewer](./agent_context_example/04-quality-security/code-reviewer.md)
*   [Compliance Auditor](./agent_context_example/04-quality-security/compliance-auditor.md)
*   [Debugger](./agent_context_example/04-quality-security/debugger.md)
*   [Error Detective](./agent_context_example/04-quality-security/error-detective.md)
*   [Penetration Tester](./agent_context_example/04-quality-security/penetration-tester.md)
*   [Performance Engineer](./agent_context_example/04-quality-security/performance-engineer.md)
*   [QA Expert](./agent_context_example/04-quality-security/qa-expert.md)
*   [Security Auditor](./agent_context_example/04-quality-security/security-auditor.md)
*   [Test Automator](./agent_context_example/04-quality-security/test-automator.md)

### Data & AI

*   [AI Engineer](./agent_context_example/05-data-ai/ai-engineer.md)
*   [Data Analyst](./agent_context_example/05-data-ai/data-analyst.md)
*   [Data Engineer](./agent_context_example/05-data-ai/data-engineer.md)
*   [Data Scientist](./agent_context_example/05-data-ai/data-scientist.md)
*   [Database Optimizer](./agent_context_example/05-data-ai/database-optimizer.md)
*   [LLM Architect](./agent_context_example/05-data-ai/llm-architect.md)
*   [Machine Learning Engineer](./agent_context_example/05-data-ai/machine-learning-engineer.md)
*   [ML Engineer](./agent_context_example/05-data-ai/ml-engineer.md)
*   [MLOps Engineer](./agent_context_example/05-data-ai/mlops-engineer.md)
*   [NLP Engineer](./agent_context_example/05-data-ai/nlp-engineer.md)
*   [Postgres Pro](./agent_context_example/05-data-ai/postgres-pro.md)
*   [Prompt Engineer](./agent_context_example/05-data-ai/prompt-engineer.md)

### Developer Experience

*   [Build Engineer](./agent_context_example/06-developer-experience/build-engineer.md)
*   [CLI Developer](./agent_context_example/06-developer-experience/cli-developer.md)
*   [Dependency Manager](./agent_context_example/06-developer-experience/dependency-manager.md)
*   [Documentation Engineer](./agent_context_example/06-developer-experience/documentation-engineer.md)
*   [DX Optimizer](./agent_context_example/06-developer-experience/dx-optimizer.md)
*   [Git Workflow Manager](./agent_context_example/06-developer-experience/git-workflow-manager.md)
*   [Legacy Modernizer](./agent_context_example/06-developer-experience/legacy-modernizer.md)
*   [MCP Developer](./agent_context_example/06-developer-experience/mcp-developer.md)
*   [Refactoring Specialist](./agent_context_example/06-developer-experience/refactoring-specialist.md)
*   [Tooling Engineer](./agent_context_example/06-developer-experience/tooling-engineer.md)

### Specialized Domains

*   [API Documenter](./agent_context_example/07-specialized-domains/api-documenter.md)
*   [Blockchain Developer](./agent_context_example/07-specialized-domains/blockchain-developer.md)
*   [Embedded Systems](./agent_context_example/07-specialized-domains/embedded-systems.md)
*   [Fintech Engineer](./agent_context_example/07-specialized-domains/fintech-engineer.md)
*   [Game Developer](./agent_context_example/07-specialized-domains/game-developer.md)
*   [IoT Engineer](./agent_context_example/07-specialized-domains/iot-engineer.md)
*   [Mobile App Developer](./agent_context_example/07-specialized-domains/mobile-app-developer.md)
*   [Payment Integration](./agent_context_example/07-specialized-domains/payment-integration.md)
*   [Quant Analyst](./agent_context_example/07-specialized-domains/quant-analyst.md)
*   [Risk Manager](./agent_context_example/07-specialized-domains/risk-manager.md)
*   [SEO Specialist](./agent_context_example/07-specialized-domains/seo-specialist.md)

### Business & Product

*   [Business Analyst](./agent_context_example/08-business-product/business-analyst.md)
*   [Content Marketer](./agent_context_example/08-business-product/content-marketer.md)
*   [Customer Success Manager](./agent_context_example/08-business-product/customer-success-manager.md)
*   [Legal Advisor](./agent_context_example/08-business-product/legal-advisor.md)
*   [Product Manager](./agent_context_example/08-business-product/product-manager.md)
*   [Project Manager](./agent_context_example/08-business-product/project-manager.md)
*   [Sales Engineer](./agent_context_example/08-business-product/sales-engineer.md)
*   [Scrum Master](./agent_context_example/08-business-product/scrum-master.md)
*   [Technical Writer](./agent_context_example/08-business-product/technical-writer.md)
*   [UX Researcher](./agent_context_example/08-business-product/ux-researcher.md)
*   [Wordpress Master](./agent_context_example/08-business-product/wordpress-master.md)

### Meta & Orchestration

*   [Agent Organizer](./agent_context_example/09-meta-orchestration/agent-organizer.md)
*   [Context Manager](./agent_context_example/09-meta-orchestration/context-manager.md)
*   [Error Coordinator](./agent_context_example/09-meta-orchestration/error-coordinator.md)
*   [Knowledge Synthesizer](./agent_context_example/09-meta-orchestration/knowledge-synthesizer.md)
*   [Multi-Agent Coordinator](./agent_context_example/09-meta-orchestration/multi-agent-coordinator.md)
*   [Performance Monitor](./agent_context_example/09-meta-orchestration/performance-monitor.md)
*   [Task Distributor](./agent_context_example/09-meta-orchestration/task-distributor.md)
*   [Workflow Orchestrator](./agent_context_example/09-meta-orchestration/workflow-orchestrator.md)

### Research & Analysis

*   [Competitive Analyst](./agent_context_example/10-research-analysis/competitive-analyst.md)
*   [Data Researcher](./agent_context_example/10-research-analysis/data-researcher.md)
*   [Market Researcher](./agent_context_example/10-research-analysis/market-researcher.md)
*   [Research Analyst](./agent_context_example/10-research-analysis/research-analyst.md)
*   [Search Specialist](./agent_context_example/10-research-analysis/search-specialist.md)
*   [Trend Analyst](./agent_context_example/10-research-analysis/trend-analyst.md)
