# Context
This prompt is to be run when the GitHub ticket has been completed and changes have been pushed to the remote repository by the Remote Agent.

1. Pull from the remote github branch
2. push to the Flutterflow branch
3. Update the associated GitHub ticket giving the date and time for each action taken. 

## Repository Verification Protocol

### Before Starting Work:
- [ ] Check GitHub repository content via API/web interface
- [ ] Fetch latest: `git fetch origin && git pull origin <branch>`
- [ ] Verify local state matches remote expectations

### After Implementation:
- [ ] Commit and push all changes
- [ ] Verify via GitHub API that changes are in remote repository
- [ ] Check file contents are complete (not placeholders)
- [ ] Confirm all required files exist in remote repository

### Before Declaring Ready for FlutterFlow:
- [ ] Verify complete implementation exists in remote repository
- [ ] Test that user can pull the complete code locally
- [ ] Only then declare ready for FlutterFlow deployment

### If Sync Issues Occur:
- [ ] Acknowledge the problem immediately
- [ ] Re-implement and verify against remote repository
- [ ] Prioritize remote repository state over local assumptions

