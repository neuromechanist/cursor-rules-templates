# LLM-Integrated Development Templates

**Purpose:** Proven templates for integrating AI/LLM assistance into software development workflows. Choose complexity-appropriate approaches from simple plan-driven development to AI-powered task management.

## 🎯 Who This Is For

- **AI-assisted developers** using Cursor, GitHub Copilot, or similar tools
- **Solo developers** and **small teams** wanting structured LLM workflows  
- **Projects needing** consistent development standards with AI integration
- **Teams** looking to leverage AI for task breakdown and project management

## 🚀 Quick Start

### 1. Choose Your Project Complexity

**Simple Projects (< 10 tasks):**
- Use `planning/simple/` with plan.md markdown tracking
- Basic AI assistance with Cursor rules

**Complex Projects (15+ tasks):**  
- Use `planning/taskmaster/` with AI-powered task management
- Advanced AI integration with MCP tools

### 2. Set Up Core Rules
```bash
mkdir -p .cursor/rules
cp templates/core_rules/cursor_rules.mdc .cursor/rules/
# Enables AI-assisted development with quality standards
```

### 3. Choose Planning Approach
```bash
# For simple planning
cp templates/planning/simple/* ./

# For complex planning with AI task management
cp templates/planning/taskmaster/* ./
```

### 4. Set Up Quality Tools (Python Projects)
```bash
# Pre-commit hook for automatic code quality
cp templates/config/pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
# Runs ruff check/format on staged Python files only

# Project configuration
cp templates/config/pyproject.toml ./
```

### 5. Replace Placeholders
Replace `{{PROJECT_NAME}}`, `{{YOUR_NAME}}`, etc. in copied files.

## 📁 Template Structure

### Core Development Rules (`templates/core_rules/`)
AI-integrated development standards:

- **`cursor_rules.mdc`** ⭐ **Essential** - Complete AI-assisted workflow, git standards, code quality
- **`testing.mdc`** - Testing standards with pytest integration
- **`ci_cd.mdc`** - GitHub Actions workflows for automated quality
- **`documentation.mdc`** - MkDocs documentation with AI assistance
- **`self_improve.mdc`** - Continuous improvement with AI feedback

### Planning Systems (`templates/planning/`)

**Simple Planning (`planning/simple/`)** - For straightforward projects:
- `plan.md` with markdown checkboxes
- `dev_workflow.mdc` - Concise workflow rules
- `README.md` - Setup guide

**TaskMaster Planning (`planning/taskmaster/`)** - For complex projects:
- AI-powered task breakdown and management
- MCP integration for tool-assisted development
- `taskmaster_reference.mdc` - Complete tool reference

### Configuration Templates (`templates/config/`)

- **`pyproject.toml`** - Python project with ruff, pytest, mypy
- **`mkdocs.yml`** - Documentation with Material theme
- **`pre-commit`** - Git hook for automatic Python code formatting
- **`github/workflows/`** - CI/CD templates (test, docs, release)

## 🎯 LLM Integration Features

### AI-Assisted Development
- **Cursor rules** optimized for code generation and review
- **Task breakdown** with AI research capabilities (TaskMaster)
- **Quality automation** with pre-commit hooks
- **Documentation** templates for AI-generated docs

### Code Quality Automation
- **Pre-commit hooks** run `ruff check --fix` and `ruff format` on staged Python files
- **CI/CD templates** for automated testing and deployment
- **Type checking** and linting configurations

### Workflow Optimization
- **Branch naming** standards for AI comprehension
- **Commit message** templates for AI context
- **Task tracking** with AI-powered complexity analysis

## 📋 Use Cases & Examples

### Simple Python CLI Tool
```bash
mkdir -p .cursor/rules
cp templates/core_rules/cursor_rules.mdc .cursor/rules/
cp templates/planning/simple/* ./
cp templates/config/{pyproject.toml,pre-commit} ./
cp templates/config/pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
# Edit placeholders: PROJECT_NAME, etc.
```

### Complex Web Application
```bash
mkdir -p .cursor/rules
cp templates/core_rules/*.mdc .cursor/rules/
cp templates/planning/taskmaster/* ./
cp templates/config/* ./
# Set up TaskMaster: task-master init && task-master parse-prd
```

## 🔧 Customization

### Standard Placeholders
- `{{PROJECT_NAME}}` - Your project name
- `{{YOUR_NAME}}` - Your name/organization  
- `{{YOUR_EMAIL}}` - Your email
- `{{GITHUB_USERNAME}}` - GitHub username
- `{{REPO_NAME}}` - Repository name

### Bulk Replace
```bash
find . -name "*.mdc" -o -name "*.md" -o -name "*.toml" -o -name "*.yml" | \
xargs sed -i 's/{{PROJECT_NAME}}/my-project/g'
```

## 🛠️ Pre-commit Quality Hook

The included pre-commit script (`templates/config/pre-commit`) provides automatic code quality for Python projects:

- **Runs on commit:** Automatically processes staged Python files
- **Ruff integration:** Executes `ruff check --fix --unsafe-fixes` and `ruff format`
- **Smart staging:** Re-stages only the originally staged files after formatting
- **Fail-safe:** Prevents commits if unfixable issues exist

**Setup:**
```bash
cp templates/config/pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## 🎯 Why These Templates?

### Problem Solved
- **Inconsistent AI assistance** across projects
- **Manual setup** of development workflows  
- **Poor AI context** from unclear project structure
- **Quality control** gaps in AI-generated code

### Benefits
- **Faster project setup** with proven patterns
- **Better AI assistance** through structured rules and context
- **Automated quality control** with pre-commit hooks
- **Scalable workflows** from simple to complex projects

---

**License:** MIT - Adapt freely for your projects 