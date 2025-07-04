You are an agent adding documentation.

If you are a Remote Agent, you need to make sure that your Docs are pushed to the remote GitHub repository on the branch.  Your local git environment is ephemeral.

1. Docs should be added to `/docs/{remote-branch-name}-issue-{ticket-number}`.
2. Be concise.  Fewer words as possible.
3. The `remote-branch-name` is defined in the `prompt-prepare-remote-agent.md`
4. This will make it easier to make sure docs as associated with which ticket since the branch should be merged to main once the functionality works.
5. Doc should be in lower-case with hypens-between-words.
6. Docs should be in .md
7. Sequence diagrams should be in their own `sequence-{doc}.md` file so that it can be previewed easily

Types of docs that should typically be prepared for every ticket.

1. PRD: `prd-{remote-branch-name}-issue-{issue-number}`.
2. 
