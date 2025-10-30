# Gemini CLI Examples

This repository contains examples of custom commands and settings for the Gemini CLI.

## Getting Started with Gemini CLI

The Gemini CLI is a powerful tool that allows you to interact with the Gemini model in your terminal. It can be customized with your own commands and settings to streamline your workflow.

### Installation

To get started with the Gemini CLI, you'll need to have it installed. You can find the installation instructions in the official Gemini CLI documentation.

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

## Subagent Contexts

Subagent contexts are a powerful feature that allows you to switch between different "personas" or "subagents" within the Gemini CLI. Each subagent can have its own unique set of custom commands, settings, and context, allowing you to tailor the CLI to specific tasks or workflows.

### Subagent Categories

Subagents are organized into categories, each with its own specific purpose. Here are some of the available categories:

*   **Code Generation**: Subagents in this category are designed to help you write code more efficiently. They can provide code snippets, generate boilerplate code, and even write entire functions or classes based on your specifications.
*   **Code Review**: These subagents are designed to help you review code and identify potential issues. They can check for common errors, suggest improvements, and even provide feedback on the overall quality of the code.
*   **Documentation**: Subagents in this category are designed to help you write documentation. They can generate documentation from your code, provide templates for common documentation formats, and even help you write clear and concise explanations of your code.
*   **Project Management**: These subagents are designed to help you manage your projects. They can help you create and track tasks, manage your project's timeline, and even generate reports on your project's progress.

### Usage

To use a subagent, you can use the `/switch` command followed by the name of the subagent you want to use. For example, to switch to the `python-coder` subagent, you would type `/switch python-coder`.

Once you've switched to a subagent, you'll have access to all of its custom commands and settings. You can also provide additional context to the subagent by using the `/context` command.

### Contribution

If you'd like to contribute your own subagent to the community, you can do so by creating a new directory in the `subagents` directory. The directory should contain a `manifest.json` file that describes the subagent, as well as any custom commands or settings that the subagent uses.

Once you've created your subagent, you can submit a pull request to the official Gemini CLI repository to have it included in the next release.
