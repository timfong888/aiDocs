# Prompt Download FF

This is a prompt that should be performed right after downloading a new branch from FF internal.

1. Confirm with the User that the branch name is correct.  If possible, check what Flutterflow Extension believes the branch name is.  Do not hallucinate.

2. Create a branch that matches that confirmed name.

3. Sync to the remote submodules to ensure this branch is up to date.  This means going into the directory for the submodules.
  a. aiDocs
  b. Google oAuth

5. Push this updated local branch to the remote Github repo.

6. If possible, ask for the creation of a PRD doc titled "prd-{branch}.md"

7. Once completed, push that to the branch.

8. Ask use `prompt-questions.md` to come up with questions.  Turn this into an issue associated with this branch.  Tag it and ask the User to answer them if there are questions.

9. ONce approved, use `prompt-tasks.md` to come up with a task list.

10. Once task list has been defined, use `prompt-issues-management.md` to create the tickets.
