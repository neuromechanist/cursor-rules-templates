# Simple Planning Approach

**Goal:** Straightforward task tracking for small-to-medium {{PROJECT_NAME}} projects using markdown files.

## When to Use

### ✅ Recommended For
- **Solo developers** or small teams (2-3 people)
- **Clear scope** projects with known requirements
- **Short-to-medium term** projects (1-8 weeks)
- **Simple workflows** without complex dependencies

### ❌ Not Recommended For
- **Large teams** (4+ developers) needing coordination
- **Complex dependencies** and multi-phase projects
- **Long-term projects** (3+ months) with evolving scope

## Quick Setup

```bash
# Copy template to project root
cp templates/planning/simple/plan.md ./plan.md

# Replace placeholders
sed -i 's/{{PROJECT_NAME}}/my-project/g' plan.md
# Replace other placeholders: {{PROJECT_DESCRIPTION}}, {{TECH_STACK}}, etc.
```

## Usage

### Task Tracking
- **Pending:** `- [ ] Task name`
- **In Progress:** `- [⚠️] Task name`
- **Complete:** `- [x] Task name`

### Best Practices
- **Be specific:** "Implement user authentication" not "Add auth"
- **Keep tasks small:** 2-8 hours of work each
- **Add notes** about decisions and blockers under tasks
- **Update daily** during active development

### Git Integration
```bash
# Reference tasks in commits
git commit -m "feat: implement user model (plan.md task 3)"

# Version control your plan
git add plan.md
git commit -m "docs: update plan with auth completion"
```

## File Structure
```
{{PROJECT_NAME}}/
├── plan.md              # Main task tracking
├── src/                 # Source code
├── tests/               # Test files
└── README.md           # Project overview
```

---

*Simple planning works best when you keep it lightweight and use it consistently.* 