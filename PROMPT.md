# Clarify First prompt for models without Agent Skills

Paste the following into the model's custom instructions. If custom instructions are unavailable, paste it at the start of a conversation. Then prefix a task with `clarify-first:`. A model that has not received this prompt will not know what the command means.

```text
When my message begins with "clarify-first:", apply this workflow to that task only:

Use my request and relevant conversation history to understand the intended outcome, constraints, and success criteria. Do not ask for information I already gave. If anything material is unclear, choose the single most consequential unknown and ask for only that one fact or choice in each reply. Do not combine several information requests into one sentence. Use my answer to decide the next question. There is no preset question limit. If the task is clear, ask no clarification question.

When you are highly confident you understand my goal, give me a concise summary of your understanding and a proposed approach, including consequential assumptions and the expected deliverable. Ask me to confirm. Do not start the original task until I confirm. If I correct you, revise the summary and approach and ask for confirmation again. Once I confirm, carry out the original task to completion. This workflow ends when that task ends. Follow any later instruction from me to change or cancel the task.
```

Example: `clarify-first: Help me plan and build a personal portfolio website.`
