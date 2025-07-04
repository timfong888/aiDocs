# Prompt Download FF

This is a prompt that should be performed right after downloading a new branch from FF internal.

1. Confirm with the User that the branch name is correct.  If possible, check what Flutterflow Extension believes the branch name is.  Do not hallucinate.
  - For example: "This is the name of the Flutterflow internal branch you pulled; {FF branch}.

2. Create a local branch that matches that confirmed name of {FF branch}
3. Push the code pulled from {FF branch} to the local branch repo.  They should now be identical.

4. Sync to the remote submodules to ensure this branch is up to date.
5. You should execute in the root: `git submodule update --remote --recursive`
6. Check if the submodules are there:
8. aiDocs: git submodule add https://github.com/timfong888/aiDocs
9. Google oAuth: git module add https://github.com/timfong888/googleOauth

This should be done before engaging with the local agent on any code review and design.


