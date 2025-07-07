# Simple Planning Approach

**Goal:** Straightforward task tracking for small-to-medium {{PROJECT_NAME}} projects using markdown files.

## When to Use Simple Planning

### ✅ Recommended For
- **Solo developers** or small teams (2-3 people)
- **Clear scope** projects with known requirements
- **Short-to-medium term** projects (1-8 weeks)
- **Simple workflows** without complex dependencies
- **Quick prototypes** and MVPs

### ❌ Not Recommended For
- **Large teams** (4+ developers) needing coordination
- **Complex dependencies** and multi-phase projects
- **Long-term projects** (3+ months) with evolving scope
- **Enterprise projects** requiring detailed tracking

## Quick Start

1. **Copy the template:**
   ```bash
   cp templates/planning/simple/plan.md ./plan.md
   ```

2. **Customize placeholders:**
   - Replace `{{PROJECT_NAME}}` with your project name
   - Replace `{{PROJECT_DESCRIPTION}}` with brief description
   - Add your specific tasks to the template

3. **Start planning:**
   - Break your project into 10-25 concrete tasks
   - Use the status tracking (`- [ ]` → `- [x]`)
   - Update progress as you work

## Template Structure

The `plan.md` template provides:
- **Project overview** section
- **Task breakdown** with checkboxes
- **Priority levels** (High/Medium/Low)
- **Progress tracking** built into markdown
- **Notes section** for decisions and blockers

## Best Practices

### Task Writing
- **Be specific:** "Implement user authentication" not "Add auth"
- **Keep tasks small:** 2-8 hours of work each
- **Use action verbs:** "Create," "Implement," "Test," "Deploy"
- **Include acceptance criteria** when helpful

### Progress Tracking
- **Check off completed tasks:** `- [x] Task name`
- **Add notes** about decisions made
- **Update estimates** if tasks take longer than expected
- **Track blockers** in the notes section

### File Management
- **Keep in project root** for easy access
- **Version control** your plan.md file
- **Update regularly** (daily for active projects)
- **Archive** completed sections to maintain focus

## Example Usage

```markdown
## Week 1 Tasks
- [x] Set up project structure
- [x] Create database schema
- [ ] Implement user model
- [ ] Add authentication endpoints

## Current Focus
Working on user authentication system.

**Blocker:** Need to decide between JWT vs sessions.
**Decision:** Going with JWT for stateless API.
```

## Integration with Development

### Git Workflow
```bash
# Reference tasks in commits
git commit -m "feat: implement user model (plan.md task 3)"

# Update plan with completed work
git add plan.md
git commit -m "docs: update plan with auth completion"
```

### Code Reviews
- Reference plan tasks in PR descriptions
- Use plan context to guide review focus
- Update plan based on review feedback

---

*Simple planning works best when you keep it lightweight and actually use it daily.* 