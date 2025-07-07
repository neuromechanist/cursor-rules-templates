# Development Workflow & Rule Templates

Proven, modular development workflow templates for modern software projects. Choose the components you need - from simple plan-driven development to AI-powered task management.

## 🎯 Who This Is For

- **Solo developers** and **small teams** starting new projects
- **Cursor AI users** wanting consistent, intelligent code assistance
- **Projects needing** established development standards and workflows

## 🚀 Quick Start

1. **Choose your approach:**
   - **Simple projects (< 10 tasks)**: Use `planning/simple/` with plan.md
   - **Complex projects (15+ tasks)**: Use `planning/taskmaster/` with AI task management

2. **Copy core rules:**
   ```bash
   mkdir -p .cursor/rules
   cp templates/core_rules/essential.mdc .cursor/rules/
   ```

3. **Copy planning templates:**
   ```bash
   # For simple planning
   cp templates/planning/simple/* ./
   
   # For complex planning  
   cp templates/planning/taskmaster/* ./
   ```

4. **Replace placeholders:** `{{PROJECT_NAME}}`, `{{YOUR_NAME}}`, etc.

## 📁 Template Structure

### Core Development Rules
Modular rules for Cursor AI - choose what you need:

- **`essential.mdc`** ⭐ **Start here** - Git workflow, code quality, basic development standards
- **`testing.mdc`** - Testing standards with pytest
- **`ci_cd.mdc`** - GitHub Actions workflows  
- **`documentation.mdc`** - MkDocs documentation standards
- **`cursor_rules.mdc`** - How to write effective Cursor rules
- **`self_improve.mdc`** - Continuous improvement process

### Planning Approaches
Choose based on project complexity:

- **`planning/simple/`** ✅ **< 10 tasks** - plan.md with markdown checkboxes
- **`planning/taskmaster/`** 🔧 **15+ tasks** - AI-powered task management with MCP integration

### Configuration Templates
Ready-to-use configs with placeholders:

- **`config/pyproject.toml`** - Python project with ruff, pytest, mypy
- **`config/mkdocs.yml`** - Documentation with Material theme
- **`github/workflows/`** - CI/CD templates (test, docs, release)

## 🎯 Use Cases & Examples

### Simple Python Project
```bash
mkdir -p .cursor/rules .github/workflows
cp templates/core_rules/essential.mdc .cursor/rules/
cp templates/planning/simple/* ./
cp templates/config/pyproject.toml ./
# Edit placeholders: PROJECT_NAME, YOUR_NAME, etc.
```

### Complex Multi-Feature Project
```bash
mkdir -p .cursor/rules
cp templates/core_rules/*.mdc .cursor/rules/
cp templates/planning/taskmaster/* ./
cp templates/config/pyproject.toml ./
# Use taskmaster init and parse-prd for task management
```

## 🔧 Customization

### Standard Placeholders
Replace these in all templates:
- `{{PROJECT_NAME}}` - Your project name
- `{{YOUR_NAME}}` - Your name/organization
- `{{YOUR_EMAIL}}` - Your email
- `{{GITHUB_USERNAME}}` - GitHub username
- `{{REPO_NAME}}` - Repository name

### Find and Replace
```bash
# Replace placeholders after copying files
find . -name "*.mdc" -o -name "*.md" -o -name "*.toml" -o -name "*.yml" | \
xargs sed -i 's/{{PROJECT_NAME}}/my-project/g'
```

## 📋 Template Overview

**Essential Rules:** Git workflow, code quality, development standards
**Testing Rules:** Pytest configuration, coverage, CI integration  
**CI/CD Rules:** GitHub Actions, security, deployment automation
**Documentation Rules:** MkDocs setup, API docs, writing standards
**Simple Planning:** plan.md with markdown checkboxes for task tracking
**TaskMaster Planning:** AI-powered task management with MCP integration

## 🚀 Using the Templates

### With Cursor AI
1. Copy `.mdc` files to `.cursor/rules/` in your project
2. Cursor automatically applies them during development
3. Modify rules based on your project needs

### Planning Systems
- **Simple planning**: Use plan.md for straightforward task tracking
- **TaskMaster planning**: Use AI-powered task management for complex projects
- Switch between approaches as your project grows

### Customization
Templates are modular and extensible:
- Start with essential.mdc, add others as needed
- Modify rules to match your team's practices
- Contribute improvements back to the project

---

**License:** MIT - Adapt freely for your projects 