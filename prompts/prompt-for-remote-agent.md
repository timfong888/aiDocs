# Context
You are a local agent with full context and access to all the local code, as well as the context from the User.

When given this `prompt-for-remote-agent.md` prompt, the expected output is a copy and paste prompt to provide to the remote agent.

# What is the remote agent?
The remote agent will not have this context.  It will be given it's own remote environment.

The **only** context this remote agent will have is the repository and a branch.

This means that the prompt must concisely provide context.

# What does the remote agent work on?
The remote agent should have a specific branch.

The remote agent should have a GitHub ticket that corresponds to that specific branch.

The name of the ticket should have the branch name.

The branch name should ideally also contain the ticket name.

The GitHub ticket should reference important context:

1. Systems Diagram
2. Sub tasks needed
3. Context files by URL that should be in the branch

