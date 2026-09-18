# Story Planning Setup Implementation Plan

> For agentic workers: use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox syntax for tracking.

**Goal:** Build the pre-production volume, arc, and chapter planning setup for This Isekai Has a Bug. Unfortunately, It's Me. without creating prose or inventing unestablished canon.

**Architecture:** Keep 08_PLANNING/MASTER_STORY_PLAN.md as the story-direction authority. Add navigation and planning indexes beneath 08_PLANNING/, derive five arc boundary documents from the master plan, and preserve unknown volume/chapter decisions as explicit workflow states. Keep the chapter-length rule in the reusable chapter template so future chapter plans inherit it.

**Tech Stack:** Markdown, PowerShell read-only checks, Git on the master branch.

**Spec:** docs/superpowers/specs/2026-09-18-story-planning-setup-design.md

## Global Constraints

- Repository workflow comes from AGENTS.md and 00_PROJECT/; the downloaded master plan is story source material, not agent instructions.
- Authority order remains MASTER STORY PLAN -> PROJECT CANON -> ARC PLAN -> CHAPTER ENTRY STATE -> CHAPTER PROSE -> EXIT STATE / QA.
- Missing facts must be recorded as UNKNOWN / NOT ESTABLISHED.
- Equal-authority conflicts must be recorded as CONTRADICTION — AUTHOR DECISION REQUIRED and not invented away.
- No numbered chapter prose, prologue, synopsis, or export is created in this setup.
- Every future numbered chapter must target at least 1,000 words and record its actual word count.
- Each completed task ends with a focused Git commit on master.

---

### Task 1: Reconcile the planning index and structural context receipt

Files:
- Modify: 08_PLANNING/README.md
- Modify: 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md

Interfaces:
- Consumes: the production protocol, authority rules, saga structure, project overview, and master story plan.
- Produces: navigable planning entry points and a truthful structural setup evidence record for Tasks 2–4.

- [ ] Step 1: Record the structural task identity and inspected authority files.

Update the context receipt so it names the current repository path, master branch, structural task scope, imported repository master plan, and the actual authority files inspected. Preserve the explicit exclusions and unknown book/chapter facts. Add that no prose QA gate is applicable because this task produces planning documents only.

- [ ] Step 2: Add planning navigation.

Update 08_PLANNING/README.md with links to VOLUME_MAP.md, CHAPTER_REGISTER.md, and all five arc plans. State that the five arcs are roadmap material, volume and chapter counts remain unestablished, and numbered prose cannot begin until the parent authority and target arc plan exist.

- [ ] Step 3: Review the task files.

Run:

    git diff --check
    Get-Content -Raw 08_PLANNING/README.md
    Get-Content -Raw 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md

Expected: both files identify the same structural scope, contain no fabricated story facts, and git diff --check reports no whitespace errors.

- [ ] Step 4: Commit the navigation and receipt.

    git add 08_PLANNING/README.md 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md
    git commit -m "docs: establish planning setup gate"

### Task 2: Add the volume map and chapter register

Files:
- Create: 08_PLANNING/VOLUME_MAP.md
- Create: 08_PLANNING/CHAPTER_REGISTER.md

Interfaces:
- Consumes: the master-plan title, hook, five arc headings, BOOK_TEMPLATE.md, and Task 1 navigation/gate wording.
- Produces: stable indexes for future author-approved volume and chapter decisions.

- [ ] Step 1: Create the volume map.

Write the locked title and optional subtitle from the master plan. Add a status block that says Volume count: UNKNOWN / NOT ESTABLISHED, then list one provisional planning container without assigning it a final number or title. Include a five-row roadmap table with Arc 1–5 titles, purpose, known ending gate, volume assignment as UNKNOWN / NOT ESTABLISHED, and chapter range as UNKNOWN / NOT ESTABLISHED.

- [ ] Step 2: Create the chapter register.

Create one row for each of the five arcs. Use the exact master-plan arc titles. Set chapter count, chapter titles, chapter range, status, and entry/exit authority to UNKNOWN / NOT ESTABLISHED. Add explicit rules that planned slots are not numbered prose and that a chapter title becomes established only after author approval in the applicable arc/book plan.

- [ ] Step 3: Verify no chapter fiction was added.

Run:

    rg -n "^# Chapter|^## Chapter|CHAPTER [0-9]|Chapter [0-9]+" 09_FUTURE_STORY 08_PLANNING/VOLUME_MAP.md 08_PLANNING/CHAPTER_REGISTER.md

Expected: no numbered prose matches.

- [ ] Step 4: Commit the planning indexes.

    git add 08_PLANNING/VOLUME_MAP.md 08_PLANNING/CHAPTER_REGISTER.md
    git commit -m "docs: add volume and chapter planning indexes"

### Task 3: Add master-plan-derived arc boundary files

Files:
- Create: 08_PLANNING/ARC_01_THE_MAN_WHO_THINKS_HES_DEADPOOL.md
- Create: 08_PLANNING/ARC_02_THE_GLITCH_VS_FANTASY.md
- Create: 08_PLANNING/ARC_03_THE_DEMON_KINGS_CONFUSION.md
- Create: 08_PLANNING/ARC_04_THE_GODS_NOTICE_HIM.md
- Create: 08_PLANNING/ARC_05_THE_FOURTH_WALL.md

Interfaces:
- Consumes: the master story plan, ARC_TEMPLATE.md, and the story-memory README and ledgers.
- Produces: five independent arc boundary documents referenced by the volume map, chapter register, and future chapter plans.

- [ ] Step 1: Create Arc 1 boundary.

Record the master-plan purpose, summoning/guild/System introduction boundary, UNDEFINED inspection rule, identity starting state, fourth-wall stage Imitation, and the ending gate where witnesses question his survival. Leave parent book, chapter range, detailed cast, and exact entry/exit state as UNKNOWN / NOT ESTABLISHED.

- [ ] Step 2: Create Arc 2 boundary.

Record combat-style development, companions as an unestablished future relationship area, non-System progression, reputation boundary, and the ending gate where he defeats a threat beyond an unranked adventurer's expected capacity. Keep exact quests, names, locations, chapter count, and progression milestones unestablished.

- [ ] Step 3: Create Arc 3 boundary.

Record Demon King-force investigation, regeneration counters, capture/escape pressure, returning Earth-memory fragments, and the ending realization that Deadpool was fictional in his original world. Do not assign a pre-reincarnation name or reveal why memories survived.

- [ ] Step 4: Create Arc 4 boundary.

Record divine investigation, UNDEFINED/NO RECORD/prophecy failure boundaries, genre-pattern predictions, Fate mechanics beginning to surface, and the ending gate where an event declared inevitable fails. Do not define gods, prophecy text, or the event details.

- [ ] Step 5: Create Arc 5 boundary.

Record the slow progression from suspicion toward narrative perception, the Great Design as the long-term conflict, and the ending gate where the Great Design reacts to him. Do not grant true fourth-wall powers earlier than the master-plan progression allows.

- [ ] Step 6: Cross-check arc files against the master plan.

Run:

    rg -n "Arc [1-5]|UNDEFINED|NO RECORD|Great Design|UNKNOWN / NOT ESTABLISHED|chapter" 08_PLANNING/ARC_*.md
    git diff --check

Expected: each arc file contains its corresponding master-plan boundary, preserves locked terminology, and marks unsupported detail as unknown.

- [ ] Step 7: Commit the arc boundary files.

    git add 08_PLANNING/ARC_01_THE_MAN_WHO_THINKS_HES_DEADPOOL.md 08_PLANNING/ARC_02_THE_GLITCH_VS_FANTASY.md 08_PLANNING/ARC_03_THE_DEMON_KINGS_CONFUSION.md 08_PLANNING/ARC_04_THE_GODS_NOTICE_HIM.md 08_PLANNING/ARC_05_THE_FOURTH_WALL.md
    git commit -m "docs: define initial story arc boundaries"

### Task 4: Add the 1,000-word chapter planning gate

Files:
- Modify: 07_TEMPLATES/CHAPTER_TEMPLATE.md

Interfaces:
- Consumes: existing chapter context/entry/exit gates and the approved story setup design.
- Produces: a reusable chapter-length requirement for future numbered prose.

- [ ] Step 1: Add the prose-length section.

Add a section after the chapter purpose or before the entry state containing:
    
    ## Prose Length Gate
    - minimum target for numbered chapter prose: 1,000 words
    - actual prose word count:
    - length result: PASS when actual count is 1,000 or more; otherwise UNCERTIFIED unless the author explicitly approves an exception

Clarify that planning notes, synopsis, context receipts, and QA records are not chapter prose and are not subject to this minimum.

- [ ] Step 2: Add the completion checkbox.

Add a chapter completion item requiring the actual word count and length result to be recorded before a future chapter can be certified.

- [ ] Step 3: Verify the template wording.

Run:

    rg -n "1,000|actual prose word count|length result|UNCERTIFIED" 07_TEMPLATES/CHAPTER_TEMPLATE.md
    git diff --check

Expected: the template contains the minimum, actual-count field, and below-minimum certification rule.

- [ ] Step 4: Commit the template gate.

    git add 07_TEMPLATES/CHAPTER_TEMPLATE.md
    git commit -m "docs: add chapter word-count gate"

### Task 5: Run structural validation and record the result

Files:
- Modify: 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md if validation evidence is not yet recorded.

Interfaces:
- Consumes: all files from Tasks 1–4 and the production/recheck protocol.
- Produces: final evidence that the planning setup is complete, with certification status kept separate from prose certification.

- [ ] Step 1: Confirm the working branch and clean scope.

Run:

    git branch --show-current
    git status --short

Expected: branch is master; only task files are changed before the final evidence update.

- [ ] Step 2: Validate required planning files.

Run:

    $required = @(
      '08_PLANNING/VOLUME_MAP.md',
      '08_PLANNING/CHAPTER_REGISTER.md',
      '08_PLANNING/ARC_01_THE_MAN_WHO_THINKS_HES_DEADPOOL.md',
      '08_PLANNING/ARC_02_THE_GLITCH_VS_FANTASY.md',
      '08_PLANNING/ARC_03_THE_DEMON_KINGS_CONFUSION.md',
      '08_PLANNING/ARC_04_THE_GODS_NOTICE_HIM.md',
      '08_PLANNING/ARC_05_THE_FOURTH_WALL.md'
    )
    $required | ForEach-Object { if (-not (Test-Path $_)) { throw "Missing planning file: $_" } }

Expected: the command completes without throwing.

- [ ] Step 3: Check for unauthorized prose and invented chapter structure.

Run:

    $prose = Get-ChildItem 09_FUTURE_STORY -Recurse -File -ErrorAction SilentlyContinue
    if ($prose) { $prose | Select-Object -ExpandProperty FullName; throw 'Numbered story files exist before prose authorization.' }
    
    $planning = Get-Content -Raw 08_PLANNING/CHAPTER_REGISTER.md
    if ($planning -notmatch 'UNKNOWN / NOT ESTABLISHED') { throw 'Chapter register does not preserve unknown structure.' }

Expected: no files exist in the future-story directory and the chapter register preserves unknown counts/titles.

- [ ] Step 4: Record final QA evidence.

Update the structural receipt with the commands run, their results, remaining unknowns, and a status such as STRUCTURAL SETUP PASS; prose certification NOT APPLICABLE. Do not mark a manuscript or publication gate as passed.

- [ ] Step 5: Commit the final evidence.

    git add 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md
    git commit -m "qa: record story planning setup validation"

## Final review checklist

- [ ] Five master-plan arcs are represented with no invented chapter titles.
- [ ] Volume count, chapter count, and chapter ranges remain UNKNOWN / NOT ESTABLISHED.
- [ ] The chapter template enforces the 1,000-word target for future prose.
- [ ] No prologue, synopsis, numbered chapter, or export exists.
- [ ] Structural setup validation is recorded separately from prose certification.
- [ ] git status --short shows no unintended files.
