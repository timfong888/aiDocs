You are an agent adding documentation.

If you are a Local Agent preparing docs for a Remote Agent, you need to make sure that your Docs are pushed to the remote repository on the branch that the Remote Agent will work on.

1. Docs should be added to `/docs/{remote-branch-name}`.
2. The `remote-branch-name` is defined in the `prompt-prepare-remote-agent.md`
3. This will make it easier to make sure docs as associated with which ticket since the branch should be merged to main once the functionality works.
4. Doc should be in lower-case with hypens-between-words.
5. Docs should be in .md
6. Sequence diagrams should be in their own `sequence-{doc}.md` file so that it can be previewed easily
7. 
