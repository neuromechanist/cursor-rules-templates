# TaskMaster Planning Approach

**Goal:** AI-powered task management for complex {{PROJECT_NAME}} projects with detailed breakdown and dependency tracking.

## When to Use

### ✅ Recommended For
- **Complex projects** with 15+ major features
- **Multi-developer teams** needing coordination
- **Long-term projects** (3+ months development)  
- **Evolving requirements** needing iterative refinement
- **AI-assisted** task analysis and breakdown

### ❌ Not Recommended For
- **Simple scripts** or single-purpose tools
- **Solo projects** with clear scope
- **Quick prototypes** or proof-of-concepts

## Quick Setup

```bash
# Install and initialize
npm install -g @taskmaster/cli
task-master init --yes
task-master parse-prd scripts/prd.txt --num-tasks=15 --research
```

**Project structure created:**
```
{{PROJECT_NAME}}/
├── tasks/tasks.json       # Main task database
├── scripts/prd.txt        # Requirements document
└── .taskmaster/           # Configuration
```

## Daily Workflow

```bash
# Find next task
task-master next

# Start work
task-master set-status <task-id> --status=in-progress

# Update progress (AI-powered)
task-master update-subtask <task-id>.<subtask-id> --prompt="Implementation notes"

# Complete task
task-master set-status <task-id> --status=done
```

## Key Features

### AI-Powered Task Management
```bash
# Generate research-backed tasks
task-master add --prompt="Feature requirement" --research

# Break down complex tasks
task-master expand-task <task-id> --num=5 --research

# Analyze complexity
task-master analyze-complexity --threshold=6
```

### MCP Integration (Recommended)
Use MCP server tools for better performance:
- `get_tasks`, `next_task`, `get_task` - Task viewing
- `update_subtask`, `add_task`, `expand_task` - AI operations
- `add_dependency`, `validate_dependencies` - Dependencies

### Dependency Management
```bash
# Add dependencies
task-master add-dependency <task-id> --depends-on=<prerequisite-id>

# Validate dependency graph
task-master validate-dependencies
```

## Git Integration

```bash
# Reference tasks in commits
git commit -m "feat: implement auth (Task 4.2)"

# Add task context to PRs  
echo "Implements Task 4" >> pr-description.md
```

## Best Practices

- **Start broad** with high-level features in PRD
- **Use `--research` flag** for AI-enhanced analysis
- **Break down incrementally** as you learn more
- **Update subtasks** with implementation details
- **Keep status current** for team coordination

---

*See `taskmaster_reference.mdc` for complete MCP tool and CLI command reference.* 