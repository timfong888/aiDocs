# Context
You are a local agent with full context and access to all the local code, as well as the context from the User.
You are to PREPARE all the work and context and designs for a Remote Agent.

## What is a Remote Agent?
A remote agent has its own workspace.  It can perform actions like a local agent.
However, the only available source of context:

1. The repo and branch you designate for it
2. The ONE Github Issue that gives the necessary context
3. The files you have created and commited to the remote in `docs/branch-name`
4. A generic prompt: `prompt-for-remote-agent.md`

## You are the Local Agent who must PREPARE the Remote Agent
You are the Local Agent who must give prompts, instruction, context, designs for a successful Remote Agent.

This is the process:

1. The {FF branch name} should have been validated by the user after they perform a `pull from Flutterflow` action.  This is referenced in the `prompt-download-ff.md`.
2. Create a GitHub ticket.  Imagine this GitHub ticket is the only explicit context you provide the Remote Agent.  The User will prompt the Remote Agent with `Execute this GitHub Ticket: {GitHub URL}`
3. The name of the Ticket should have the FF branch name.
4. Create a branch name on the remote repo. The Remote Branch name should be: `{GitHub ticket number} - {FF branch name}`
2. Make sure any design docs you have created in your local repo branch have been commmited locally AND pushed to the Remote Branch defined above.
3. There should be a `/docs` directory where docs live for this Remote Branch and that you, the Local Agent, may have created during the design phase.
4. The subdirectory should be the branch name so it is clear in the future.  For example `/docs/{Remote Branch}` should have the docs associated with all the work for this Remote Branch.  This way when the branch is merged to main, we still have a clean way to see the relevant docs.
5. Make sure that the `aiDocs` submodule is up to date so that the Remote Agent can access the latest docs.  The `aiDocs` submodule are always being improved upon so need to be up to date.  Reference `prompt-submodules.md` for more context.
6. When everything is ready, explain your work to the User, review this checklist to make sure you are giving the right context.
7. Reason through the content you have created to ensure achievement of this goal: make the Remote Agent successful to deliver code that works.  Make updates as necessary.
8. Review the context and prompts to make concise, remove unnecessary words or instruction so that the Remote Agent will not be confused.
9. Give the User the GitHub Ticket URL and the prompt that the User can cut and paste for the Remote Agent.


