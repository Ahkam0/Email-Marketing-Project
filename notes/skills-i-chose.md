# Skills I chose

Searched skills.sh on 22 November 2026 with `npx skills find` for: email marketing, email sequence, campaign plan, resend. Star counts come from GitHub on the same day. Nothing is installed yet.

## Use these

**1. For writing campaigns: `anthropics/knowledge-work-plugins`**
- Skills: `campaign-plan` (3.5K installs) and `email-sequence` (3.1K installs).
- Published by Anthropic, the company that makes Claude. It is an official organization account.
- The repository has about 36,700 stars and was updated yesterday.
- It covers both halves of what I need: planning a campaign, then writing the emails in order. This is also where the `/marketing:email-sequence` skill my course uses comes from.

**2. For sending email: `resend/resend-skills`**
- Skills: `resend` (25K installs). Also `send-email` and `resend-cli`.
- Published by Resend, the email service I'll be sending through. It is their official organization account.
- Only about 216 stars, but that's normal for a small company's own tools. Who publishes it matters more here than popularity: Resend knows its own service best.
- Related: `resend/email-best-practices` (148 stars) is a good, safe extra for deliverability tips.

## Avoid these

**1. `caffeinelabs/skills@extension-email-marketing`**
- It was the top result for "email marketing" with 33K installs, but its GitHub repository has only **2 stars** and no description.
- That gap is a warning sign. Real popularity usually shows up as stars. Install counts can be inflated by automated installs, so a high count with almost no stars means I can't tell who is really using it or why.

**2. `claude-office-skills/skills@email-marketing`**
- The name sounds official, but it is **not** made by Anthropic. It's an unrelated account that uses "Claude" in its name.
- It hasn't been updated since January 2026, about ten months ago.
- A name that borrows a trusted brand, plus no recent upkeep, is a reason to pick the real publisher instead.

## How I decided

Before installing any skill, check these three things:

1. **Who publishes it.** Look at the part before the slash (for example `anthropics/` or `resend/`). Prefer the official account of the company behind the tool. Watch out for names that only *sound* official.
2. **Whether the numbers agree.** Compare the install count on skills.sh with the GitHub stars and the date it was last updated. A big gap, like thousands of installs but almost no stars, or no updates for months, is a red flag.
3. **What it actually does.** Open the skill's page and read its `SKILL.md` before installing. Check for anything that runs commands, sends email, or asks for API keys. A skill is instructions that Claude will follow, so only install ones you've read and trust.
