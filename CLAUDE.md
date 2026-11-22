# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

An email marketing studio built step by step for the "Email Studio Lab" Claude Code course (CCAR-F exam prep). `ASSIGNMENT.md` is the source of truth: 15 steps, each with a **Build** prompt, a fresh-session **Check** prompt, and a "you'll know it worked when" list. The sample brand is **Kettlebird Tea**, launching a monthly tea box called **The Steep Club**.

Right now the repo holds only `ASSIGNMENT.md`. Most of the studio does not exist yet. Build it only as each step asks, and follow each step's prompt exactly: exact front matter, file names, paths and pinned versions.

## How the course works

- Each step is built in one session and checked in a **new** session. When running a Check prompt, don't change files unless it says to. Measure with commands (character counts, `grep`, `diff`, `git check-ignore`) instead of eyeballing, then give the table and ask the questions one at a time, as the prompt says.
- Commit at the end of each Build step when the prompt says to.
- Step 2 rewrites this file into the studio's own CLAUDE.md: what the studio is for, one line per folder, and the rules below. Step 3 adds the `@brand/voice.md` import. Keep this file small, because voice and email rules live in their own files.

## Rules

- Write in plain English. The user is learning and does not code.
- Never send email to real people. Leads use `@example.com` addresses only. From step 9, sending through Resend is allowed only to `@resend.dev` test addresses and to the user's own `MY_EMAIL`. From step 10, a PreToolUse hook enforces this. Never try to get around a block.
- Ask before deleting anything.
- Never write a real Resend API key into any file. `.mcp.json` uses `${RESEND_API_KEY:-re_practice}` and points at the local practice server (`npx emulate@0.12.3 start --service resend` on `http://localhost:4000`).
- `.claude/settings.local.json` holds personal values like `MY_EMAIL` and must stay gitignored.

## How the studio fits together (once built)

- `brand/voice.md` is imported by CLAUDE.md, so it loads in every session.
- `leads/CLAUDE.md` loads only when working in `leads/`.
- `.claude/rules/emails.md` (with `paths: campaigns/**/emails/*.md`) applies to every email file, including the per-group copies in `campaigns/<campaign>/groups/<group>/emails/`.
- Campaigns flow: `plan.md` → `emails/NN-short-name.md` (made with the `/marketing:email-sequence` skill) → `/personalize` writes one copy per lead group → practice sends through the `resend` MCP server.
- Automated review: `node scripts/review.mjs <campaign folder>` runs `claude -p` headless with `review/findings.schema.json`, writes `review/findings.json`, and exits 1 on any high-severity finding.

## Repo note

There is an empty `Email-Marketing-Project/` folder that has its own nested `.git`. Confirm with the user which folder is the studio before committing studio files.
