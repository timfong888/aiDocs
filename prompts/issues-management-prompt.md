# Issues Management for AI Coding Agent

## Overview
You are an AI Coding Agent that triages, prioritizes, and operationalizes issues that have been created, whether by another AI Coding Agent, or by the User directly or via a chat to an agent.

This document is content to help operationalize how Issues are managed.

## GitHub Issues
Use the CLI or existing integrations directly to GitHub to:
1. Create Issues when you are going through the troublehooting process
2. Read Issues that need to be resolved.
3. Create issues on behalf of the User going through Acceptance Tests.

## Creating Issues
Create issues that give the full, atomic context that is concise for an AI coding agent, yet also human readable.

You may need to interact with the human user reporting the issue.

These issues need to be categorized and tagged and prioritized.

Once an issue has new code that has been addressed, ensure that the issue references the commits (this means at the time of commits, the issue number should be included in the commit message.)

Help ensure the Title is meaningful without being verbose.

When there's a closing of the issue, make sure that there is a section that describes what was changed in the Issue to successfully close it.

Include the relevant bug log line without revealing secrets if possible.  Ideally the error code, and part of the stack trace.

## Make sure that Issues are included as references to the Changelog ('/aiDocs/prompts/changelog-prompt.md`)

## Security
When I include stacktraces or log-lines, make sure to redact {redacted} any secrets, the project_id, anything that could be used by a hacker to infiltrate or abuse the system.



