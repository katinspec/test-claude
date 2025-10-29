# test-claude

This repository is used for testing Claude Code web UI.

## Purpose

This is a test repository created to validate and experiment with Claude Code's web interface functionality.

## What You Can Do with Claude Code Web UI

Claude Code web UI provides a browser-based coding experience where you can delegate complex development tasks to Claude. Here are some examples of what you can accomplish:

### Repository & Code Management
- **Connect GitHub repositories** directly from your browser without opening a terminal
- **Create and manage branches** for different features or experiments
- **Generate pull requests** automatically with clear summaries of changes
- **Run multiple tasks in parallel** across different repositories from a single interface

### Code Development Tasks
- **Implement new features** by describing what you need in natural language
- **Fix bugs and refactor code** with AI-assisted analysis and modifications
- **Write tests** for existing functionality
- **Add documentation** and comments to improve code clarity
- **Migrate code** between languages or frameworks

### Project Setup & Configuration
- **Initialize new projects** with proper structure and dependencies
- **Configure build tools** and development environments
- **Set up CI/CD pipelines** and GitHub Actions
- **Add linting and formatting** rules to maintain code quality

### Security & Environment
- **Isolated sandbox environments** for each task with configurable network access
- **Controlled filesystem restrictions** to ensure safe execution
- **Secure Git proxy** for repository interactions

### Mobile Development
- **Code on the go** using the iOS app early preview
- **Manage tasks** from your mobile device
- **Review and approve changes** remotely

## Getting Started

1. Visit [claude.com/code](https://claude.com/code) (requires Claude Pro or Max subscription)
2. Connect your GitHub repository
3. Describe your coding task in natural language
4. Review and approve the changes Claude suggests
5. Let Claude create pull requests automatically

## Example Use Cases

- "Add user authentication with JWT tokens"
- "Refactor the database layer to use TypeORM"
- "Write unit tests for the API endpoints"
- "Create a README with setup instructions"
- "Fix TypeScript errors in the components folder"
- "Add GitHub Actions for automated testing"

## Testing Notes & Observations

### Known Limitations
- **GitHub CLI not available**: The `gh` command is not available in the Claude Code web UI environment, which means Claude cannot directly fetch PR/MR comments or issue details. Users need to manually provide this information by copying and pasting comments or descriptions.
  - **Impact**: When asked to "follow up on MR comments," Claude cannot automatically retrieve them and must ask the user to share the feedback
  - **Workaround**: Copy the MR/PR comments and paste them directly in your message to Claude

### This Repository's Testing Focus
This repository serves as a testbed to document and validate Claude Code web UI functionality, including:
- Basic file operations (create, read, update)
- Git operations (commit, push, branch management)
- Following feedback and iterating on changes
- Identifying environment limitations and workarounds
