# Rule Templates Repository

## Purpose
This repository contains development rule templates for AI-assisted coding workflows. It provides standardized, battle-tested rules for Cursor, Claude, and other AI development tools.

## Repository Structure
```
rule_templates/
├── .context/              # This repo's development context (gitignored)
│   ├── research.md       # Technical decisions and exploration
│   ├── ideas.md          # Design concepts
│   └── scratch_history.md # Failed attempts and lessons
└── templates/
    ├── core_rules/        # Essential development standards
    ├── planning/          # Task management approaches
    │   ├── simple/        # Documentation-driven workflow
    │   │   └── .context/  # Template context files
    │   └── taskmaster/    # AI-powered task management
    ├── config/           # Pre-commit hooks and configs
    └── github/           # GitHub Actions workflows
```

## Core Principles

### 1. Documentation-Driven Development (.context/)
All workflow documentation lives in `.context/` directory:
- **.context/plan.md**: Task tracking and project phases
- **.context/research.md**: Technical solutions and references
- **.context/ideas.md**: Design concepts and exploration
- **.context/scratch_history.md**: Failed attempts and lessons learned

### 2. Strict NO MOCK Testing Policy
- Never use mocks, stubs, or fake datasets
- Real tests with real data only
- If real testing isn't possible, don't write tests
- Ask for sample data or test environment setup instead

### 3. Concise Atomic Commits
- Messages under 50 characters
- No emojis in commits or PRs
- Feature branches for multi-step work
- Direct commits to main for small fixes

### 4. Learning from Experience
- Document failures immediately in scratch_history.md
- Extract patterns from research.md into rules
- Rules should enable creativity, not constrain it
- Every failure teaches something valuable

## Working with This Repository

### When Adding New Templates
1. Keep rules concise but complete
2. Include the "why" not just the "what"
3. Add practical examples from real code
4. Cross-reference related rules
5. Test that rules are actionable
6. Place workflow docs in .context/ structure

### When Updating Templates
1. Review .context/scratch_history.md for patterns to avoid
2. Check .context/research.md for proven solutions
3. Ensure NO MOCK policy is maintained
4. Keep descriptions factual (not philosophical)
5. Preserve thoughtful guidance in content
6. Update all references to use .context/ path

### Rule Quality Standards
- **Actionable**: Clear what to do
- **Specific**: No ambiguity
- **Compact**: Concise but complete
- **Thoughtful**: Treats AI as skilled developer
- **Practical**: Real examples and commands

## Template Usage

### For New Projects
1. Choose planning approach (simple or taskmaster)
2. Copy relevant templates including .context/ structure
3. Replace placeholders ({{PROJECT_NAME}}, etc.)
4. Use gitignore-template or add `.context/` to .gitignore
5. Configure AI tool to read .mdc files and .context/

### For Existing Projects
1. Review current practices vs templates
2. Adapt templates to project needs
3. Extract project-specific patterns
4. Update templates with learnings
5. Share improvements back to this repo

## Development Workflow for This Repo

### Making Changes
1. Create issue and feature branch
2. Make atomic commits with clear messages
3. Test templates in real projects
4. Document rationale in .context/research.md
5. Create PR with comprehensive description

### Quality Checks
- Templates should work across languages
- Rules must be AI-tool agnostic where possible
- Examples should be realistic
- NO MOCK policy must be preserved
- Guidance should encourage thinking

## Key Files to Maintain

### Core Rules (Keep Compact but Thoughtful)
- `cursor_rules.mdc`: Main AI workflow guidance
- `testing.mdc`: NO MOCK testing standards
- `ci_cd.mdc`: Pipeline automation
- `documentation.mdc`: MkDocs standards
- `self_improve.mdc`: Rule evolution process

### Planning Templates (Keep Synchronized)
- Simple and TaskMaster should share core concepts
- Both must support multi-document workflow
- Update both when improving either

## Remember
- Rules are collective wisdom, not arbitrary constraints
- Good rules enable better development
- Every project teaches something
- Document learnings in .context/ for future benefit
- AI assistants are skilled developers who benefit from context and encouragement
- The .context/ directory provides a clean, organized home for workflow documentation

---
*This repository evolves with experience. Contribute your learnings.*