# Production and Recheck Protocol

This is the mandatory workflow authority for planning, canon changes, arc work, chapter work, revision, rechecks, QA, and exports in this project.

## Required flow

`CLASSIFY TASK → LOAD AUTHORITY STACK → BUILD CONTEXT RECEIPT → BUILD ENTRY-STATE PACKET → CHECK UNKNOWN / CONTRADICTIONS → PLAN OR RECHECK → PERFORM APPROVED SCOPE → RECONCILE EXIT STATE → RUN QA → CERTIFY OR LEAVE UNCERTIFIED`

## Task classes

Use one or more of: `NEW_BOOK`, `NEW_ARC`, `NEW_CHAPTER`, `RECHECK_ARC`, `RECHECK_CHAPTER`, `LOCKED_PROSE_REVISION`, `CANON_CHANGE`, or `STRUCTURAL_CHANGE`.

## Context gate

Before substantive story work, complete `07_TEMPLATES/CONTEXT_RECEIPT_TEMPLATE.md` and record the actual files inspected. Load the master plan, applicable canon, progression/power authority, relevant character/world records, and surrounding prose when the task reaches manuscript level.

## Parent-to-child dependency

No numbered chapter prose before its parent book/serial authority, arc plan, and inherited entry state exist. No arc plan may silently contradict the master plan. No export is publication-ready merely because a file exists.

## Anti-hallucination rule

If a required fact is not established, write `UNKNOWN / NOT ESTABLISHED`. If equal-authority sources conflict, write `CONTRADICTION — AUTHOR DECISION REQUIRED` and stop the affected decision until resolved.

## Exit and QA

Reconcile location/time, characters, knowledge, abilities, injuries/resources, relationships, mysteries, objectives, and next-state requirements. Run the applicable editorial, continuity, progression, human-prose, Story Studio, and export checks before claiming certification.
