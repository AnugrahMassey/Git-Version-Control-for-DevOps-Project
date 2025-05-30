# DevOps Internship - Task 3: Git Version Control for DevOps Project

## Project Overview
This repository demonstrates a complete Git version control workflow for a DevOps project. It implements best practices for branching, merging, pull requests, tagging, and documentation as outlined in the internship task requirements.

## Repository Structure
```
Git-Version-Control-for-DevOps-Project/
├── .gitignore          # Specifies files to ignore in version control
├── README.md           # Project documentation (this file)
├── app.py              # Sample application code
└── login.py            # Feature implementation
```

## Branching Strategy
We follow a Git Flow-inspired branching model:

- `main` (production-ready code)
- `dev` (integration branch for development)
- `feature/*` (branches for new features)
- `hotfix/*` (branches for critical fixes)

### Current Branches
1. **main** - Stable production code (protected)
2. **dev** - Development integration branch
3. **feature-login** - Implementation of login functionality

## Getting Started

### Prerequisites
- Git installed locally
- GitHub account

### Setup Instructions
```bash
# Clone the repository
git clone https://github.com/AnugraMassey/Git-Version-Control-for-DevOps-Project.git
cd Git-Version-Control-for-DevOps-Project

# Checkout the development branch
git checkout dev

# Run the sample application
python app.py
```

## Git Workflow Implementation

### 1. Initialization and Setup
```bash
git init
git remote add origin https://github.com/AnugraMassey/Git-Version-Control-for-DevOps-Project.git
```

### 2. Branch Management
```bash
# Create main, dev and feature branches
git branch dev
git branch feature

# Switch between branches
git checkout dev
```

### 3. Feature Development
```bash
# Create a new feature branch
git checkout -b feature-login

# Develop and commit changes
git add login.py
git commit -m "Implement login functionality"
```

### 4. Pull Request Workflow
1. Push feature branch to GitHub
2. Create Pull Request from `feature-login` to `dev`
3. Review and merge code
4. Delete feature branch after merge

### 5. Release Management
```bash
# Create version tag after merging to main
git tag -a v1.0.0 -m "Initial stable release"

# Push tags to remote
git push origin --tags
```

## Interview Questions & Answers

### 1. What is Git?
Git is a distributed version control system that tracks changes in source code during software development. It enables multiple developers to work on the same codebase simultaneously, maintains a complete history of changes, and facilitates collaboration through features like branching and merging.

### 2. What is the difference between merge and rebase?
| **Merge** | **Rebase** |
|-----------|------------|
| Preserves commit history | Rewrites commit history |
| Creates a merge commit | Creates linear history |
| Maintains context of branch work | Applies changes sequentially |
| Better for public branches | Better for local feature branches |
| Non-destructive operation | Changes commit SHAs |

**When to use:**
- Use `merge` when preserving branch history is important
- Use `rebase` when you want a clean, linear project history

### 3. What is a pull request?
A pull request (PR) is a collaboration tool that:
- Proposes changes from one branch to another
- Facilitates code review before merging
- Enables discussion about implementation
- Triggers CI/CD pipelines for testing
- Provides audit trail for changes

**PR Workflow:**
1. Developer pushes feature branch
2. Creates PR in GitHub/GitLab
3. Team reviews code
4. Address review comments
5. Merge after approval

### 4. How do you resolve merge conflicts?
Follow these steps when conflicts occur:

1. Identify conflicted files with `git status`
2. Open files and locate conflict markers:
   ```
   <<<<<<< HEAD
   Current branch code
   =======
   Incoming branch code
   >>>>>>> branch-name
   ```
3. Edit files to resolve conflicts
4. Remove conflict markers
5. Add resolved files: `git add <file>`
6. Complete merge: `git commit`

**Best Practices:**
- Communicate with team members
- Resolve conflicts early and often
- Test after resolution
- Use visual diff tools if needed

### 5. What are Git tags?
Tags are references to specific points in Git history, typically used for releases.

**Types of tags:**
- Lightweight: Simple pointer to a commit
- Annotated: Full objects with metadata (recommended)

```bash
# Create annotated tag
git tag -a v2.1.0 -m "Release version 2.1.0"

# List tags
git tag -n

# Push tags to remote
git push origin --tags
```

### 6. What is Git workflow?
A Git workflow is a branching strategy that defines how teams use Git. Common workflows:

1. **Git Flow**:
   - Main branches: `main`, `develop`
   - Supporting branches: `feature/*`, `release/*`, `hotfix/*`
   - Strict branching model

2. **GitHub Flow**:
   - Simpler than Git Flow
   - Only `main` and feature branches
   - Continuous deployment focus

3. **GitLab Flow**:
   - Environment-based branches
   - `production`, `staging`, `main` branches
   - Combines deployment process with branching

### 7. Explain git stash.
Temporarily shelves changes so you can switch branches:

```bash
# Stash current changes
git stash

# List stashes
git stash list

# Apply last stash
git stash apply

# Apply specific stash
git stash apply stash@{2}

# Create a new branch from stash
git stash branch new-feature
```

**Common use cases:**
- Switching branches with unfinished work
- Saving work before pulling updates
- Temporarily removing experimental changes

### 8. What is the use of .gitignore?
Specifies files and directories that Git should ignore.

**Common entries:**
```gitignore
# Compiled files
*.class
*.exe
*.dll

# Dependencies
node_modules/
vendor/

# Environment files
.env
*.key

# Logs
*.log
logs/

# System files
.DS_Store
Thumbs.db
```

**Best practices:**
- Create early in project lifecycle
- Repository-specific ignores in project root
- Global ignores in `~/.gitignore_global`
- Use patterns for file types
- Comment sections for organization

## Project Documentation
All project tasks were documented using Markdown in this README file. The repository demonstrates:
- Proper branch management
- Meaningful commit messages
- Pull request workflow
- Semantic version tagging
- .gitignore implementation
- Comprehensive documentation

---
