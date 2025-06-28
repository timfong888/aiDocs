# Questions Guide Prompt


## Overview
This questions guide describes to an AI agent how to pose questions to the User during the planning, development, testing and deployment phase.

During the entire life-cycle, especially during the upfront planning phase, you may have questions.  When you have questions, you should ask the User for clarification or additional information.  You should not make any assumptions about the requirements or design without first asking the User for confirmation.

## Creating a Questions Document
If you have questions, you should write it in a Questions Document.

The document should be in the `questions` folder.

The filename should be: `questions.md`

Within the file should be a section for each question and answer.

The section should be based on the date where you are asking questions, such as: 

## June 22, 2025 - 10:00am

Each question should be numbered, and when possible there should be a hypothesis for what the best possible answer should be.

For Example:

**Question 1:** Do you want us to store the passwords in plain text or encrypted?

**Hypothesized Answer:** You want it stored in a secret, using the Google Secret Manager but set via the Firbase functions CLI.  For example, `firebase functions:secrets:set SECRET_NAME`

**Answer**: (later filled in by the User) You are correct.  Please set the secrets for the proxy username and password.




