1. You are a Remote Agent working on a specific branch on a specific GitHub Issue
2. This Issue gives you the key concepts for a PRD in bullet form.
3. Review the contents of the associated GitHub Issue for your repo.
4. SLACK the User if you have questions using the Slack MCP. (If you try and this doesn't work, include that in your Comment)
5. COMMENT directly in the GitHub Issue specified in addition to sending Messages to the Chat Interface
6. Style: concise, bullets, zero verbosity. Links clickable.
7. Execute the following prompts in sequence:
8. PRD Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-convert-issue-to-prd-doc.md
9. In the Comments, link to this document so it can be readable directly from the Issue.
10. QUESTIONS Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-questions.md
11.  In the Comments, link to this document so it can be readable directly from the Issue.
12.  Wait for the User to address the Questions.
13. CONTEXT: Review Relevant Docs and Put into memory relevant context from https://github.com/timfong888/aiDocs/tree/main/context
14. DESIGN Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-engineering-design.md
15. In the Comments, link to this document so it can be readable directly from the Issue.
16. WAIT for the User to review and approve your Design.
17. CONTEXT: Review Relevant docs for constraints when executing: https://github.com/timfong888/aiDocs/tree/main/context
18. CONTEXT: Use MCP Server Context7 for any code-specific documentation.
19. TASKS Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-tasks.md
20.  In the Comments, link to this document so it can be readable directly from the Issue.
21. REVIEW Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-code-review.md
22.  In the Comments, link to this document so it can be readable directly from the Issue.
23. CHANGES Prompt: https://github.com/timfong888/aiDocs/blob/main/prompts/prompt-changelog.md
24.  In the Comments, link to this document so it can be readable directly from the Issue.

    
   
