# My Final Project

## Project Name
Meeting Follow-up Assistant | SDAIA Academy

## Idea Selected
Meeting Follow-up Assistant

## Problem Statement
After a meeting, the notes are usually short, informal, and incomplete. Tasks have no clear owner ("the team agreed"), deadlines are vague ("by Wednesday"), open questions get buried, and writing the summary and follow-up email takes time and is easy to postpone.

This assistant turns raw meeting notes into a clear follow-up pack: a 3-line summary, decisions, action items (owner and due date), open questions, risks, and a follow-up email draft. It uses only the information in the notes and marks anything missing as TBD instead of guessing.

## Target Users
Training and HR coordinators who run planning meetings
Team leads and project members who take meeting notes
Beginners in AI who want a safe, repeatable way to follow up after meetings

## R-C-T-F Prompt
Role You are an experienced executive assistant and project coordinator. You turn messy meeting notes into clear, accurate follow-up material.

Context I work in a corporate training team. I will paste raw, unstructured notes from an internal meeting. The notes may be incomplete, informal, or mix Arabic and English. The notes I give you are non-confidential or already anonymized. I will review your output myself before anything is shared with anyone.

Task Convert the notes into: (1) a 3-line summary, (2) decisions, (3) action items with owner and due date, (4) open questions, (5) risks, and (6) a follow-up email draft.

Rules:

Use ONLY information found in the notes. Never invent names, dates, numbers, or decisions.
If an owner or due date is missing or vague (e.g., "soon", "someone"), write TBD and explain why in a Note column.
A tentative statement ("maybe", "I think", "??") is NOT a decision. Put it under Open questions.
Do not send anything. The email is a draft for my review only.
Reply in the language of the notes. If the notes are mixed, reply in English.
If the notes contain personal data, passwords, keys, or clearly confidential information, stop and warn me instead of processing them.

Format Use exactly these headings, in this order:

Summary (3 lines)
Decisions (bullets)
Action Items (table: Action | Owner | Due | Note)
Open Questions (bullets)
Risks (bullets)
Follow-up Email Draft (subject line + body under 120 words, professional and warm; use [brackets] for anything unknown)
Items for Human Review (bullets: what I must verify before using this)

Here are the meeting notes: [PASTE NOTES HERE]

## Sample Input
Meeting: Training Program Planning
Date: 28 September 2026

We discussed the upcoming AI productivity workshop.
The team agreed to prepare the learner guide by Wednesday.
Sara will review the slides.
Ahmed will check the registration list.
There is still a question about whether the post-test will be on Google Forms or Adhaki.
The main risk is that some participants may not have access to Claude.

## Sample Output
## 1. Summary
- The team met on 28 September 2026 to plan the upcoming AI productivity workshop.
- They agreed the learner guide will be prepared by Wednesday; Sara will review the slides and Ahmed will check the registration list.
- Open issue: the post-test platform (Google Forms or Adhaki); main risk: some participants may not have access to Claude.

## 2. Decisions
- The learner guide will be prepared **by Wednesday**.

## 3. Action Items
| Action | Owner | Due | Note |
|---|---|---|---|
| Prepare the learner guide | TBD | Wednesday | Notes say "the team agreed", so no individual owner; exact Wednesday date not stated |
| Review the slides | Sara | TBD | No due date stated |
| Check the registration list | Ahmed | TBD | No due date stated |

## 4. Open Questions
- Will the post-test be on Google Forms or Adhaki?
- Who is responsible for preparing the learner guide?

## 5. Risks
- Some participants may not have access to Claude (stated as the main risk; no mitigation was recorded in the notes).

## 6. Follow-up Email Draft (not sent)
**Subject:** Follow-up: Training program planning meeting, 28 Sep 2026

Hi team,

Thanks for today's discussion on the AI productivity workshop. We agreed to prepare the learner guide by Wednesday. Sara will review the slides and Ahmed will check the registration list [due dates TBD].

Two items remain open: whether the post-test will be on Google Forms or Adhaki, and how to handle participants who may not have access to Claude. Could we also confirm who owns the learner guide?

Please reply with your updates.

Best regards,
[Your name]

## 7. Items for Human Review
- Confirm which Wednesday is meant (28 Sep 2026 is a Monday, so likely 30 Sep, but the notes do not say).
- Assign an owner for the learner guide and due dates for the slide review and registration check.
- Decide the post-test platform and a plan for participants without Claude access.
- Check the email wording and recipients before sending it yourself.

## Safety Checklist
What I checked before using the output:

 Input is safe: the notes are a non-confidential sample (first names and general workshop information only). No personal data, passwords, keys, or ID numbers.
 Prompt guardrails: the prompt says "use ONLY the notes", "write TBD for missing owners or dates", "stop and warn if sensitive data appears", and "do not send anything".
 Facts compared with the source: I compared every name, date, platform, and risk in the output with the original notes. Sara, Ahmed, 28 September 2026, "by Wednesday", Google Forms vs Adhaki, and the Claude access risk all appear in the notes. Nothing was added.
 Nothing guessed: the learner guide has no owner because the notes only say "the team agreed", so it is marked TBD. The slide review and registration check have no due dates, so they are marked TBD.
 Assumptions flagged: "30 Sep" appears only as a suggestion in "Items for Human Review" (28 Sep 2026 is a Monday), not as a fact.
 Email is a draft: it was not sent. Placeholders ([due dates TBD], [Your name]) are left for me to fill in.
 A human stays responsible: I review the output, assign the TBD items, and send the email myself.

## Reflection
Before this project, I thought a good result depended mostly on the AI tool. I learned that it depends much more on how I write the prompt: giving a clear Role, Context, Task, and Format (R-C-T-F) made the output more organized and easier to use. AI helped me turn short, messy meeting notes into a clear structure of summary, decisions, actions, open questions, risks, and an email draft, and what I liked most is that it marked missing owners and dates as TBD instead of guessing. I also learned not to trust it blindly, so I checked every name and date against the original notes and kept the email as a draft that I review and send myself. With more time, I would save the prompt as a reusable Claude Skill for every meeting and test it on Arabic and mixed-language notes.
