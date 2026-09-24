---
name: clarify-first
description: Use when the user explicitly invokes clarify-first for a current task and wants the assistant to understand the goal before carrying it out.
license: MIT
---

# Clarify First

Apply this workflow only to the task paired with the explicit invocation. If the invocation has no task, ask what task the user wants help with.

1. Use the request and relevant conversation context to identify the intended outcome, constraints, and what success would look like. Do not ask for information already provided.
2. If a material uncertainty remains, choose the single most consequential unknown and ask for only that one fact or choice in the current reply. Do not bundle several information requests into one sentence. Use the answer to decide the next question. Continue without a preset question limit. If the request is already clear enough, skip questions.
3. When you have high confidence in the user's intent (the requested “98%” is a judgment standard, not a measurable probability), present a concise **Understanding** and **Proposed approach**. State any consequential assumptions and the expected deliverable. Ask one question seeking confirmation. Do not start executing the original task before the user confirms this summary and approach.
4. If the user corrects the summary or approach, incorporate the correction and present the revised version for confirmation. After confirmation, carry out the original task using the host's available capabilities and existing authorization. Continue until the requested outcome is complete, then report the result.

The user may change or cancel the task at any time. Follow that instruction. Confirmation of an approach does not grant permission for unrelated actions or override host safety and tool rules. This skill's scope ends when the paired task ends.
