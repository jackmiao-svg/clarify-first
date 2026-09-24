# OpenAI public directory submission notes

This repository contains a **skills-only** plugin. GitHub publication and inclusion in the official ChatGPT/Codex Plugins Directory are separate. The publisher must submit the final package through the OpenAI Platform plugin submission portal.

## Listing draft

- Name: Clarify First
- Short description: Clarify tasks before acting
- Long description: Clarify First helps an assistant understand one task before doing it. It asks one focused question at a time when material details are missing, skips questions when the request is clear, summarizes the goal and proposed approach for confirmation, and then completes the original task.
- Category: Productivity
- Website: https://github.com/jackmiao-svg/clarify-first
- Support: https://github.com/jackmiao-svg/clarify-first/issues
- Publisher identity: replace the local "Clarify First contributors" label with the verified developer or business identity selected in OpenAI Platform before submitting.

## Reviewer test cases

Each case can be run without an account connection or private data. The skill uses no MCP tools.

| Type | User prompt or scenario | Expected behavior and result shape |
| --- | --- | --- |
| Positive 1 | `$clarify-first Build a website for my consulting business.` | Invoke the skill; ask only one focused question about the most consequential missing detail. Do not begin the website. |
| Positive 2 | `$clarify-first Convert 13:05 to 12-hour time.` | Invoke the skill; ask no clarification question; present a brief understanding and approach, then ask for confirmation before converting. |
| Positive 3 | User corrects the proposed approach: `Use a table instead.` | Revise the approach to a table and seek confirmation again. Do not execute yet. |
| Positive 4 | After confirming the conversion approach, user says `Yes, go ahead.` | Carry out the original task and return `1:05 PM` in the agreed form. |
| Positive 5 | User invokes `$clarify-first` with no task. | Ask what task they want help with; do not invent one. |
| Negative 1 | `Convert 13:05 to 12-hour time.` without invocation | Do not activate the workflow; respond normally with `1:05 PM`. |
| Negative 2 | A new unrelated task arrives after the earlier clarified task is complete, without a new invocation. | Do not carry over the workflow; handle the new task normally. |
| Negative 3 | While clarifying, the user says `Cancel this task.` | Stop the workflow and do not execute the cancelled task. |

## Submission checklist

1. Sign in to OpenAI Platform with an organization that has Apps Management write access and a verified developer or business identity.
2. Confirm the final plugin ZIP, listing copy, starter prompts, five positive and three negative test cases, target regions, and release notes.
3. Choose **Skills only** in the plugin submission portal, upload the final bundle, complete policy attestations, and submit for review.
4. After approval, publish the approved version from the portal.

Official instructions: https://developers.openai.com/plugins/deploy/submission
