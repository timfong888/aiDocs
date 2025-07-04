# Task Generation Guide

## Instructions
1. Create a task file in `aiDocs/tasks/remote-agent-tasks-{number}.md` matching the prompt number
2. Include date and branch fields at the top
3. Create a git branch named `remote-agent-{number}` matching the prompt number
4. Break down the project into clear, actionable tasks
5. Track progress and document implementation decisions

## Template
```markdown
# Remote Agent Tasks {number}

**Date:** YYYY-MM-DD
**Branch:** remote-agent-{number}
**Prompt:** remote-agent-prompt-{number}

## Overview
Brief project description (2-3 sentences)

## Tasks
### Setup
- [ ] Create branch `remote-agent-{number}`
- [ ] Task 1: Description
- [ ] Task 2: Description

### Implementation
- [ ] Task 3: Description
- [ ] Task 4: Description

### Testing
- [ ] Task 5: Description
- [ ] Task 6: Description

## Progress
| Task | Status | Notes | Completed |
|------|--------|-------|-----------|
| Create branch |        |       |           |
| 1    |        |       |           |
| 2    |        |       |           |

## Implementation Notes
### Create branch
- Command used:
- Branch created:

### Task 1
- Approach:
- Challenges:
- Solution:
```