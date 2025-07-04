# Task Generation Guide

## Instructions
1. Create a task file in `docs/{branch-name}-{issue}-{issue-number}/tasks.md` matching the prompt number
2. Include date and branch fields at the top of the doc
4. Break down the project into clear, actionable phases
5. Make them concise, atomic, and simple.  Do not be verbose.
6. Put the specific tasks into their respective phase.  Each should have a checkmark `[]`.
7. Track progress by converting each task to `[x]`.
8. Track progress and document implementation decisions

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
