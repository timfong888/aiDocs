# Prompt Download FF

This is a prompt that should be performed right after downloading a new branch from FF internal.

1. Confirm with the User that the branch name is correct.  If possible, check what Flutterflow Extension believes the branch name is.  Do not hallucinate.
  a. Foe wxampke: "This is the name of the Flutterflow internal branch you pulled; {FF branch}.

2. Create a branch that matches that confirmed name.

3. Sync to the remote submodules to ensure this branch is up to date.
4. This should mean `git submodule update --remote --recursive`
5. Check if the submodules are there:
8. aiDocs: git submodule add https://github.com/timfong888/aiDocs
9. Google oAuth: git module add https://github.com/timfong888/googleOauth

10. Push this updated local branch to the remote Github repo.

11. If possible, ask for the creation of a PRD doc titled "prd-{branch}.md"

12. Once completed, push that to the branch.

13. Ask use `prompt-questions.md` to come up with questions.  Turn this into an issue associated with this branch.  Tag it and ask the User to answer them if there are questions.

14. ONce approved, use `prompt-tasks.md` to come up with a task list.

15. Once task list has been defined, use `prompt-issues-management.md` to create the tickets.
