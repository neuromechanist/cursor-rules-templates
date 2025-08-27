# CI/CD Workflow Standards

## Purpose: Automated Quality Gates
**Why CI/CD?** Catch issues before users do.
**Think:** Every pipeline failure is a production bug prevented.
**Goal:** Fast feedback, high confidence, zero surprises.

## Essential Workflows

### 1. Testing (`test.yml`)
**Triggers:** `on: [push, pull_request]` to main branches  
**Jobs (in order):**
- **Lint:** `ruff check` / `eslint` (fails fast)
- **Test:** Real tests only, matrix for versions
- **Build:** Verify compilation if applicable
- **Coverage:** Optional reporting to Codecov

### 2. Documentation (`docs.yml`)
**Triggers:** `on: push: branches: [main]`  
**Jobs:** Build with MkDocs → Deploy to GitHub Pages

### 3. Release (`release.yml`)
**Triggers:** Tag creation or manual  
**Jobs:** Build → Create release → Publish packages

## Minimal Python Example
```yaml
name: CI
on: [push, pull_request]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - uses: actions/setup-python@v4
      with: { python-version: '3.11', cache: 'pip' }
    - run: pip install ruff && ruff check .

  test:
    needs: lint
    runs-on: ubuntu-latest
    strategy:
      matrix: { python-version: ['3.10', '3.11', '3.12'] }
    steps:
    - uses: actions/checkout@v4
    - uses: actions/setup-python@v4
      with: { python-version: '${{ matrix.python-version }}', cache: 'pip' }
    - run: pip install .[test]
    - run: pytest --cov=src
```

## Key Practices (Think About Pipeline Flow)
- **Pin versions:** `actions/checkout@v4` (reproducibility)
- **Cache deps:** Speed matters for developer happiness
- **Fail fast:** Lint→Test→Build→Deploy (catch cheap failures first)
- **Matrix testing:** Test all supported versions
- **Secrets:** Never commit credentials
- **Conditional:** Deploy only from protected branches

## Pipeline Philosophy
**Fast feedback:** Developers should know in <5 min
**Clear failures:** Error messages should guide fixes
**No surprises:** If it passes CI, it works in production

**Ask yourself:**
- Will this catch real issues?
- Is the feedback loop fast enough?
- Are we testing what actually matters?
