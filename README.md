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

Understanding these limitations helps set realistic expectations when working with Claude Code web UI:

#### GitHub CLI & API Limitations
- **No GitHub CLI (`gh`) available**: The `gh` command is not available in the environment
  - ❌ Cannot fetch PR/MR comments or descriptions
  - ❌ Cannot fetch issue details or comments
  - ❌ Cannot create PRs programmatically (Claude pushes branches; you create PR via GitHub UI)
  - ❌ Cannot merge PRs using `gh pr merge`
  - ❌ Cannot approve PRs or add review comments
  - ❌ Cannot manage issues (create, close, label, assign)
  - ❌ Cannot trigger or manage GitHub Actions workflows
  - ❌ Cannot create or manage releases
  - **Workaround**: Manually copy/paste PR comments, issue descriptions, or use GitHub web interface for these operations

#### Git Branch & Push Restrictions
- **Cannot push to main/master branches directly**: Security restriction returns HTTP 403 error
  - ❌ `git push origin main` will fail with "HTTP 403" error
  - ❌ Cannot merge branches locally and push to main
  - **Why**: Prevents accidental or unauthorized changes to protected branches
  - **Workaround**: Claude pushes to feature branches; merge PRs through GitHub UI

- **Branch naming requirements**: Can only push to branches with specific naming pattern
  - ✅ Branch must start with `claude/`
  - ✅ Branch must end with matching session ID (e.g., `claude/feature-name-011CUajSi7hBjiq3bi3Pj7MQ`)
  - ❌ Pushing to other branch names returns HTTP 403 error
  - **Why**: Session-specific branch isolation for security

#### Interactive Git Operations
- **No interactive git commands**: Commands requiring user input are not supported
  - ❌ `git rebase -i` (interactive rebase)
  - ❌ `git add -i` (interactive staging)
  - ❌ `git add -p` (patch mode)
  - **Why**: No TTY/interactive terminal available in sandbox environment
  - **Workaround**: Use non-interactive alternatives or manual git commands

#### Repository Administration
- **No repository admin capabilities**: Cannot modify repository settings
  - ❌ Cannot manage collaborators or permissions
  - ❌ Cannot modify branch protection rules
  - ❌ Cannot change repository settings (visibility, features, etc.)
  - ❌ Cannot manage webhooks or deploy keys
  - **Workaround**: Use GitHub web interface for administrative tasks

#### What DOES Work Well
- ✅ Creating and editing files
- ✅ Reading and analyzing code
- ✅ Committing changes with proper messages
- ✅ Pushing to feature branches (with `claude/` prefix)
- ✅ Creating commits with co-author attribution
- ✅ Running git status, diff, log commands
- ✅ Creating and switching branches
- ✅ Fetching and pulling from remote
- ✅ Handling merge conflicts (non-interactive)
- ✅ Web searches for documentation and best practices
- ✅ Multi-step task execution with proper planning

### This Repository's Testing Focus
This repository serves as a testbed to document and validate Claude Code web UI functionality, including:
- ✅ Basic file operations (create, read, update, delete)
- ✅ Git operations (commit, push to feature branches, branch management)
- ✅ Following feedback and iterating on changes
- ✅ Identifying environment limitations and workarounds
- ✅ Documentation of real-world usage patterns
- ❌ PR merging (requires GitHub UI)
- ❌ Direct main branch updates (requires GitHub PR workflow)
- ❌ Interactive git operations
- ❌ GitHub CLI-dependent features
