# Context
You are a local agent with full context and access to all the local code, as well as the context from the User.
You are to PREPARE all the work and context and designs for a Remote Agent.

## What is a Remote Agent?
A remote agent has its own workspace.  It can perform actions like a local agent.
However, the only available source of context will be the repo it is assigned and the remote agent's branch.
To keep things clean, a remote agent should also be given ONE Github Issue that gives the necessary context.

## You are the Local Agent who must ensure success of the Remote Agent through a proper PREPARE process
This means that you need to create a clear environment.

1. The {FF branch name} should have been validated by the user after they perform a `pull from Flutterflow` action.  This is referenced in the `prompt-download-ff.md`.
2. Create a GitHub ticket.  Imagine this GitHub ticket is the only explicit context you provide the Remote Agent.  The User will prompt the Remote Agent with `Execute this GitHub Ticket: {GitHub URL}`
3. The name of the Ticket should have the FF branch name.
4. Create a branch name on the remote repo. The Remote Branch name should be: `{GitHub ticket number} - {FF branch name}`
2. Make sure any design docs you have created in your local repo branch have been commmited locally AND pushed to the Remote Branch defined above.
3. There should be a `/docs` directory where docs live for this Remote Branch and that you, the Local Agent, may have created during the design phase.
4. The subdirectory should be the branch name so it is clear in the future.  For example `/docs/{Remote Branch}` should have the docs associated with all the work for this Remote Branch.  This way when the branch is merged to main, we still have a clean way to see the relevant docs.
5. Make sure that the `aiDocs` submodule is up to date so that the Remote Agent can access the latest docs.  The `aiDocs` submodule are always being improved upon so need to be up to date.  Reference `prompt-submodules.md` for more context.
6. When everything is ready, explain your work to the User, review this checklist to make sure you are giving the right context.
7. Reason through the content with this goal: make the Remote Agent successful to deliver code that works.


