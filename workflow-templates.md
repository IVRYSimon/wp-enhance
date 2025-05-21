```markdown
# Developer Workflow & Templates

## 1. Commit Message Convention  
Follow **Conventional Commits**:
- `feat:` new feature  
- `fix:` bug fix  
- `docs:` documentation  
- `style:` formatting  
- `refactor:` code change  
- `test:` adding/updating tests  
- `chore:` maintenance  

_Example:_  
feat(api): implement listPackages() in EnhanceApiClientInterface



## 2. Pull Request Template (`.github/PULL_REQUEST_TEMPLATE.md`)
```markdown
## Description
Summarize changes and link to issue.

## Types of changes
- [ ] fix
- [ ] feat
- [ ] docs
- [ ] refactor
- [ ] perf
- [ ] test
- [ ] chore

## Checklist
- [ ] Code follows PSR-12 and WP standards.
- [ ] Tests added/updated.
- [ ] Documentation updated.
- [ ] PHPStan & PHPCS pass locally.
- [ ] `.pot` regenerated if needed.

## How to test
Steps to reproduce and verify.
´´´
