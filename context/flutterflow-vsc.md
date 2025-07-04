Here is the flow for working with flutterflow and visual studio code.  As an agent, ensure that we follow this process by validating the steps are followed.

1. In flutterflow, create a branch. this might be the name of a milestone to represent multiple smaller issues.
2. In VSC, pull from the newly created Flutterflow branch.
3. In VSC, in the local repo, create a branch name that is the same as the internal FF you just pulled.
4. In VSC, push to the remote repo, so that there is now a remote branch of the same name a the internal Flutterflow branch. (FF remote branch)
5. Ask the local agent to create the tickets for the remote agents to work on the branch.
6. Each ticket should be their own branch from the FF remote branch (FF remote branch)
7. For example, ticket 6 - name should have it's own branch named (ticket 6 - name - FF remote branch)
8. These should all be created, reviewed, and put into a single document that is saved.

## As tickets are completed
1. Ticket is completed, test the ticket's branch.
2. Merge that ticket branch back into the FF remote branch and go through the branch hygiene and tagging process.
3. Keep going until all the tickets are closed.  The ticket branches should be closed.
4. The FF remote branch should be tested in some deployment environment (TBD)
5. The FF remote branch should, once accepted, be pulled back into the local environment.
6. The local environment, synced with the FF remote branch, should be pushed back to Flutterflow
7. Flutterflow should have a manual commit of the FF internal branch.
8. This should be deployed (need a better process).
9. When happy this FF branch should be merged to main.
10. When this is done, the remote FF branch shold be merged to main as well.

