# Task Generation Guide

## Instructions
1. Create a task file in `docs/{issue-number}-{branch-name}/tasks-{issue-number}-{branch-name}.md` matching the GitHub issue number
2. The GitHub Issue should have a link to this document.
3. Include date and branch fields at the top of the doc
4. Break down the project into clear, actionable phases
5. Make each task concise, atomic, and simple.  Do not be verbose.
6. Put the specific tasks into their respective phase.  Each should have a checkmark `[]`.
7. Ask the User to review the Tasks.
8. Review GitHub Issue Comments for potential comments on the Tasks.
9. When Approved, Execute the Tasks.
10. Track progress by converting each task to `[x]`. This way you remember where you are.
11. If needed, clear your context window and continue where you left off in the Tasks List.
12. If issues come up, place them as Comments in the associated GitHub Issue.


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
