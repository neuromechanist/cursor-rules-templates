# Simple Planning Approach

**Goal:** Documentation-driven development for {{PROJECT_NAME}} using multiple markdown files for comprehensive tracking and learning.

## When to Use

### ✅ Recommended For
- **Solo developers** or small teams (2-3 people)
- **Learning-oriented** projects needing documentation
- **Research-heavy** work with exploration phases
- **Short-to-medium term** projects (1-8 weeks)
- **Projects needing** decision tracking and rationale

### ❌ Not Recommended For
- **Large teams** (4+ developers) needing coordination
- **Complex dependencies** and multi-phase projects
- **Long-term projects** (3+ months) with evolving scope

## Quick Setup

```bash
# Copy all templates to project root
cp templates/planning/simple/*.md ./
cp templates/planning/simple/*.mdc ./

# Replace placeholders in all files
for file in *.md *.mdc; do
  sed -i 's/{{PROJECT_NAME}}/my-project/g' "$file"
done

# Add to .gitignore
echo "*.md" >> .gitignore
echo "!README.md" >> .gitignore
```

## Usage

### Task Tracking (plan.md)
- **Pending:** `- [ ] Task name`
- **In Progress:** `- [⚠️] Task name`  
- **Researching:** `- [🔬] Task name`
- **Complete:** `- [x] Task name`

### Documentation Files
- **plan.md:** Task lists and project phases
- **research.md:** Technical solutions and references
- **ideas.md:** Design concepts before implementation
- **scratch_history.md:** Failed attempts and lessons

### Best Practices
- **Start with ideas.md** for design exploration
- **Update research.md** when exploring solutions
- **Track failures** in scratch_history.md immediately
- **Keep tasks small:** 2-8 hours of work each
- **Cross-reference docs:** Use `(see research.md#section)`
- **Update daily** during active development

### Git Integration
```bash
# Concise commits without task references
git commit -m "feat: implement user model"

# Documentation stays local (in .gitignore)
# Only commit if sharing with team:
git add -f plan.md research.md
git commit -m "docs: update project documentation"
```

## File Structure
```
{{PROJECT_NAME}}/
├── dev_workflow.mdc    # AI workflow rules
├── plan.md             # Task tracking
├── research.md         # Technical research
├── ideas.md            # Design concepts
├── scratch_history.md  # Failed attempts
├── src/                # Source code
├── tests/              # Test files
└── README.md          # Project overview
```

## Workflow Example

1. **Ideation:** Write high-level concept in ideas.md
2. **Research:** Explore approaches in research.md
3. **Planning:** Break down into tasks in plan.md
4. **Development:** Implement while updating task status
5. **Learning:** Document failures in scratch_history.md
6. **Iteration:** Update all docs with insights

---

*Documentation-driven development helps you learn from every project.* 