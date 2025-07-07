# TaskMaster Planning Approach

**Goal:** AI-powered task management for complex {{PROJECT_NAME}} projects with detailed breakdown and dependency tracking.

## When to Use TaskMaster

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
- **Short-term projects** (< 2 weeks)

## Quick Setup

1. **Initialize TaskMaster:**
   ```bash
   npm install -g @taskmaster/cli
   task-master init
   task-master parse-prd scripts/prd.txt --num-tasks=15
   ```

2. **Project structure created:**
   ```
   {{PROJECT_NAME}}/
   ├── tasks/tasks.json       # Main task database
   ├── scripts/prd.txt        # Requirements document
   └── .taskmaster/           # Configuration
   ```

## Core Workflow

### Daily Development
```bash
# Find next task
task-master next

# Start work
task-master set-status <task-id> --status=in-progress

# Update progress
task-master update-subtask <task-id>.<subtask-id> --prompt="Implementation notes"

# Complete task
task-master set-status <task-id> --status=done
```

### Task Management
```bash
# Add tasks
task-master add --prompt="Feature requirement"

# Break down complex tasks
task-master expand-task <task-id> --num=5 --research

# Manage dependencies
task-master add-dependency <task-id> --depends-on=<prerequisite-id>
```

## Best Practices

### Task Creation
- **Start broad** with high-level features
- **Use `--research` flag** for AI-enhanced analysis
- **Break down incrementally** as you learn
- **Add dependencies** for proper sequencing

### Progress Tracking  
- **Update subtasks** with implementation details
- **Log key decisions** and architectural choices
- **Keep status current** for team coordination
- **Reference task IDs** in commits and PRs

## Advanced Features

### AI Research Integration
```bash
# Generate research-backed tasks
task-master parse-prd --research scripts/prd.txt
task-master expand-task <id> --research --prompt="Security best practices"
```

### Complexity Analysis
```bash
# Analyze task complexity
task-master analyze-complexity --threshold=6
task-master complexity-report
```

## Git Integration

```bash
# Reference tasks in commits
git commit -m "feat: implement auth (Task 4.2)"

# Add task context to PRs  
echo "Implements Task 4" >> pr-description.md
```

## Troubleshooting

- **Tasks too complex:** Use `expand-task` to break down
- **Circular dependencies:** Run `validate-dependencies`
- **Lost context:** Update subtasks regularly
- **Performance:** Use MCP server over CLI when possible

---

*See `taskmaster_reference.mdc` for complete MCP tool and CLI command reference.* 