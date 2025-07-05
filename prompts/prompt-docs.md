You are an agent adding, reviewing, or editing documentation associated with your GitHub Issue.

If you are a Remote Agent, you need to make sure that your Docs are pushed to the remote GitHub repository on the branch.  Your local git environment is ephemeral.

1. Docs should be added to `/docs/{ticket-number}-{remote-branch-name}`.
2. Be concise.  Few words as possible.
3. The `remote-branch-name` is defined in the `prompt-prepare-remote-agent.md`
4. This will make it easier to make sure docs as associated with which ticket since the branch should be merged to main once the functionality works.
5. Doc should be in lower-case with hypens-between-words.
6. Docs should be in .md
7. Sequence diagrams should be in their own `sequence-{doc}.md` file so that it can be previewed easily

Types of docs that should typically be prepared for every ticket.  There should be a link in the ticket to each respective document.

1. PRD: `prd-{issue-number}-{remote-branch-name}`.
2. QUESTIONS: prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-questions.md. format: `questions-{ticket number}-{remote branch name}.md`
3. DESIGN: prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-engineering-design.md.  format: `design-{issue-number}-{branch-name}.md`
4. TASKS: prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-tasks.md.  Format: `tasks-{issue-number}-{branch-name}.md`

