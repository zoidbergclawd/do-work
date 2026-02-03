# Changelog

What's new, what's better, what's different. Most recent stuff on top.

---

## 0.8.0 — The Clarity Pass

The UR system was hiding in plain sight — documented everywhere but easy to miss if you weren't reading carefully. This release restructures the do action and skill definition so the UR + REQ pairing is unmissable, even for agents that skim. Also added agent compatibility guidance to CLAUDE.md so future edits keep the skill portable across platforms.

- Added "Required Outputs" section to top of do.md — UR + REQ pairing stated upfront as mandatory
- Restructured Step 5 Simple Mode — UR creation now has equal weight with REQ creation
- Added Do Action Checklist at end of workflow — mirrors the work action's orchestrator checklist
- Moved UR anti-patterns to general "What NOT To Do" section (was under complex-only)
- Updated SKILL.md with core concept callout about UR + REQ pairing
- Added Agent Compatibility section to CLAUDE.md — generalized language, standalone-prompt design, floor-not-ceiling

## 0.7.0 — The Nudge

Complex requests now get a gentle suggestion to run `/do-work verify` after capture. If your input had lots of features, nuanced constraints, or multiple REQs, the system lets you know verification is available — so you can catch dropped details before building starts. Simple requests stay clean and quiet.

- Verify hint added to do action's report step for meaningfully complex requests
- Triggers on: complex mode, 3+ REQ files, or notably long/nuanced input
- Two complex examples updated to show the hint in action
- No change for simple requests — no hint, no noise

## 0.6.0 — The Bouncer

Working and archive folders are now off-limits. Once a request is claimed by a builder or archived, nobody can reach in and modify it — not even to add "one more thing." If you forgot something, it goes in as a new addendum request that references the original. Clean boundaries, no mid-flight surprises.

- Files in `working/` and `archive/` are now explicitly immutable
- New `addendum_to` frontmatter field for follow-up requests
- Do action checks request location before deciding how to handle duplicates
- Work action reinforces immutability in its folder docs

## 0.5.0 — The Record Keeper

Now you can see what changed and when. Added this very changelog so the project has a memory. CLAUDE.md got updated with rules to keep it honest — every version bump gets a changelog entry, no exceptions.

- Added `CHANGELOG.md` with full retroactive history
- Updated commit workflow: version bump → changelog entry → commit

## 0.4.0 — The Organizer

The archive got a brain. New **cleanup action** automatically tidies your archive at the end of every work loop — closing completed URs, sweeping loose REQs into their folders, and herding legacy files where they belong. Also introduced the **User Request (UR) system** that groups related REQs under a single umbrella, so your work has structure from capture to completion.

- Cleanup action: `do work cleanup` (or automatic after every work loop)
- UR system: related REQs now live under UR folders with shared context
- Routing expanded: cleanup/tidy/consolidate keywords recognized
- Work loop exit now triggers automatic archive consolidation

## 0.3.0 — Self-Aware

The skill learned its own version number. New **version action** lets you check what you're running and whether there's an update upstream. Documentation got a glow-up too.

- Version check: `do work version`
- Update check: `do work check for updates`
- Improved docs across the board

## 0.2.0 — Trust but Verify

Added a **testing phase** to the work loop and clarified what the orchestrator is (and isn't) responsible for. REQs now get validated before they're marked done.

- Testing phase baked into the work loop
- Clearer orchestrator responsibilities
- Better separation of concerns

## 0.1.1 — Typo Patrol

Fixed a username typo in the installation command. Small but important — can't install a skill if the command is wrong.

- Fixed: incorrect username in `npx install-skill` command

## 0.1.0 — Hello, World

The beginning. Core task capture and processing system with do/work routing, REQ file management, and archive workflow.

- Task capture via `do work <description>`
- Work loop processing with `do work run`
- REQ file lifecycle: pending → working → archived
- Git-aware: auto-commits after each completed request
