# Story Architecture Expansion Implementation Plan

> For agentic workers: use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox syntax for tracking.

**Goal:** Add durable writing, story-memory, history, character, power, progression, and 10-volume/300-chapter planning authority without creating manuscript prose or closing the story at Chapter 300.

**Architecture:** Extend the existing references and ledgers, then add focused authority files under the repository's existing canon directories. The 300-chapter roadmap is a provisional horizon made of ten 30-chapter volumes and six five-chapter movement blocks per volume; it preserves open mysteries and Chapter 301+ continuation hooks.

**Tech Stack:** Markdown, PowerShell structural checks, Git on the master branch.

**Spec:** docs/superpowers/specs/2026-09-18-story-architecture-expansion-design.md

## Global Constraints

- The master story plan remains the story-direction authority; new files may not silently invent canon.
- Planned ledger entries are not planted or canonized until approved prose provides evidence.
- The protagonist never becomes Wade Wilson and never receives normal System progression.
- The protagonist's approved narrative name is Red Jackal; his original Earth name remains `UNKNOWN / NOT ESTABLISHED`.
- Red Jackal's imagination anomaly has no cooldown, cost, focus requirement, understanding requirement, blocker, counter, suppression, or known limit.
- Red Jackal's failure to use the imagination anomaly is always a character choice or story decision, never a mechanical inability.
- Fourth-wall development remains gradual and cannot begin as a true supernatural power.
- Every future numbered chapter targets at least 1,000 words and records its actual count.
- The 300-chapter roadmap is provisional; Chapter 300 is a checkpoint, not the final ending.
- No prologue, synopsis, manuscript prose, or publication export is created by this task.
- No Docker file is added and no Docker command is part of this story-documentation implementation.
- Each task ends with a focused commit on master.

---

### Task 1: Expand prose, comedy, and drafting rules

**Files:**
- Modify: 06_REFERENCES/WRITING_STYLE_GUIDE.md
- Create: 06_REFERENCES/WRITING_RULES.md
- Modify: 07_TEMPLATES/CHAPTER_TEMPLATE.md only if the practical rule needs a cross-link

**Interfaces:**
- Consumes: the master story plan, existing writing-style guide, existing human-prose gate, and the current chapter template.
- Produces: a single prose authority plus a practical drafting contract for future chapters.

- [ ] Step 1: Add natural-author prose rules to the style guide.

Add sections for human sentence rhythm, paragraph variation, concrete sensory detail, close-third-person distance, character-specific dialogue, emotional/physical continuity, restrained exposition, scene purpose, and revision for repetition. State that natural writing means deliberate human choices and clear causality, not artificial randomness.

- [ ] Step 2: Add comedy rules.

Record that comedy comes from coping, timing, wrong assumptions, social friction, contrast, and character voice. Require serious consequences to remain serious, prohibit quips after every injury, require quiet beats after major trauma, and prevent jokes from proving supernatural fourth-wall power.

- [ ] Step 3: Create the practical writing-rules document.

Include a pre-draft checklist, POV rules, dialogue rules, exposition rules, System-message formatting rules, fourth-wall progression guard, 1,000-word chapter rule, revision pass order, and human-prose gate handoff.

- [ ] Step 4: Verify the writing authority.

Run:

    rg -n "natural|human|comedy|consequence|POV|dialogue|exposition|1,000|fourth-wall|revision" 06_REFERENCES/WRITING_STYLE_GUIDE.md 06_REFERENCES/WRITING_RULES.md
    git diff --check

Expected: both files contain concrete rules and preserve the slow fourth-wall progression and serious-world tone.

- [ ] Step 5: Commit.

    git add 06_REFERENCES/WRITING_STYLE_GUIDE.md 06_REFERENCES/WRITING_RULES.md
    git commit -m "docs: establish natural prose and comedy rules"

### Task 2: Add planned mystery and foreshadowing records

**Files:**
- Modify: 01_CANON/STORY_MEMORY/MYSTERY_LEDGER.md
- Modify: 01_CANON/STORY_MEMORY/FORESHADOWING_LEDGER.md
- Modify: 01_CANON/STORY_MEMORY/README.md

**Interfaces:**
- Consumes: master-plan questions, locked System terms, five arc boundaries, and STORY_MEMORY_CHECKLIST.md.
- Produces: stable MY-001 through MY-008 and FS-001 through FS-008 planning records.

- [ ] Step 1: Add the mystery ledger preamble and records.

For each MY record include ID, question, source authority, status OPEN, current reader knowledge, character knowledge boundary, permitted clue movement, forbidden early reveal, and next review boundary. Use only the eight approved questions from the design spec.

- [ ] Step 2: Add the foreshadowing ledger preamble and records.

For each FS record include ID, seed, source authority, status PLANNED, allowed first-use boundary, later movement, payoff condition, consequence requirement, and exact chapter reference field. Do not mark any entry PLANTED, REINFORCED, PAYOFF_DUE, or PAID_OFF.

- [ ] Step 3: Update story-memory instructions.

State that these records organize planned continuity only, that planned is not planted, and that exact chapter references are required after prose canonization.

- [ ] Step 4: Verify ledger status safety.

Run:

    rg -n "MY-00[1-8]|FS-00[1-8]|OPEN|PLANNED|PLANTED|PAYOFF_DUE|PAID_OFF" 01_CANON/STORY_MEMORY
    git diff --check

Expected: eight mystery IDs exist with OPEN status, eight foreshadowing IDs exist with PLANNED status, and no new entry is marked planted or resolved.

- [ ] Step 5: Commit.

    git add 01_CANON/STORY_MEMORY/MYSTERY_LEDGER.md 01_CANON/STORY_MEMORY/FORESHADOWING_LEDGER.md 01_CANON/STORY_MEMORY/README.md
    git commit -m "docs: add planned mystery and foreshadowing ledger"

### Task 3: Add world and character history planning

**Files:**
- Create: 03_WORLD/HISTORY_PLAN.md
- Create: 02_CHARACTERS/CHARACTER_HISTORY_INDEX.md
- Create: 02_CHARACTERS/CHARACTER_HISTORY_TEMPLATE.md
- Modify: 02_CHARACTERS/README.md
- Modify: 03_WORLD/README.md

**Interfaces:**
- Consumes: master-plan central mystery, identity progression, Great Design history, and existing character/world templates.
- Produces: history planning authority without inventing names or biographies.

- [ ] Step 1: Create the world history plan.

Add sections for pre-existing cosmology, creation and limits of the System, divine history, Fate/Great Design cycles, Demon King cycles, mortal civilization, the reincarnation event, and unknown history questions. Separate reader-known, character-known, and author-only future information.

- [ ] Step 2: Create the character history index.

Add history tracks for the unnamed protagonist, summoning authority, future companions, guild figures, demon leadership, divine figures, and future factions. For each record purpose, present status, pre-story history status, knowledge boundary, relationship history status, permitted reveal window, and unresolved history questions. Keep names and details UNKNOWN / NOT ESTABLISHED where the master plan is silent.

- [ ] Step 3: Create the reusable character-history template.

Include identity, birth/origin, formative events, prior relationships, wounds, beliefs, secrets, current knowledge, forbidden knowledge, reveal permissions, relationship changes, and exit-state reconciliation.

- [ ] Step 4: Update directory READMEs.

Link the new history files and state that history plans do not establish canon until author-approved records or prose exist.

- [ ] Step 5: Verify unknown preservation.

Run:

    rg -n "UNKNOWN / NOT ESTABLISHED|author-only|knowledge boundary|reveal" 02_CHARACTERS 03_WORLD
    git diff --check

Expected: every unestablished name, date, location, and biography remains explicitly unknown.

- [ ] Step 6: Commit.

    git add 02_CHARACTERS 03_WORLD
    git commit -m "docs: establish history and character planning"

### Task 4: Add power-system and non-System progression authority

**Files:**
- Create: 04_POWER_SYSTEMS/POWER_SYSTEM_BIBLE.md
- Create: 05_EVOLUTION/PROGRESSION_ROADMAP.md
- Modify: 04_POWER_SYSTEMS/README.md
- Modify: 05_EVOLUTION/README.md

**Interfaces:**
- Consumes: locked System terminology, regeneration rules, fourth-wall stages, Great Design rules, ARC_01 through ARC_05, SKILL_PATH_TEMPLATE.md, and EVOLUTION_ROUTE_TEMPLATE.md.
- Produces: power and progression boundaries future plans can inherit without granting unearned abilities.

- [ ] Step 1: Create the power-system bible.

Define System fields and failure terms, Red Jackal's foreign-code/virus anomaly, his unrestricted imagination manifestation, regeneration strengths and counters, magic as an unestablished framework with future authority requirements, Fate and Great Design relationship, fourth-wall stages, resource/cost/limit rules for non-anomaly abilities, and tension safeguards. Include a rule that the protagonist cannot level, gain a normal class, or receive hidden System evolution.

- [ ] Step 2: Create the progression roadmap.

Track external growth, identity growth, fourth-wall stages, regeneration mastery, combat learning, and future progression gates across the ten-volume horizon. For every future stage, record prerequisites, evidence required in prose, costs, counters, and what remains locked.

- [ ] Step 3: Update power and evolution READMEs.

Link both new authority files and state that future abilities require source, acquisition condition, mastery evidence, limits, counters, and continuity reconciliation.

- [ ] Step 4: Verify progression safety.

Run:

    rg -n "UNDEFINED|NO RECORD|FAILED|UNAVAILABLE|ANOMALY|does not level|counters|UNKNOWN / NOT ESTABLISHED|Imitation|Genre Awareness|True Anomaly" 04_POWER_SYSTEMS 05_EVOLUTION
    git diff --check

Expected: locked terminology, no-level progression, counter rules, and slow fourth-wall stages are all present.

- [ ] Step 5: Commit.

    git add 04_POWER_SYSTEMS 05_EVOLUTION
    git commit -m "docs: define power and non-System progression authority"

### Task 5: Create the 10-volume/300-chapter roadmap

**Files:**
- Create: 08_PLANNING/300_CHAPTER_ROADMAP.md
- Modify: 08_PLANNING/README.md
- Modify: 08_PLANNING/VOLUME_MAP.md
- Modify: 08_PLANNING/CHAPTER_REGISTER.md

**Interfaces:**
- Consumes: the five arc boundaries, progression roadmap, story-memory ledgers, volume map, and chapter template.
- Produces: ten provisional volume records and 300 chapter slots organized into six five-chapter movement blocks per volume.

- [ ] Step 1: Define the roadmap contract.

State that the roadmap is an author-approved horizon, not final canon, that every slot is provisional until chapter planning approval, and that Chapter 300 is a checkpoint with open mysteries and continuation beyond Chapter 301.

- [ ] Step 2: Define volume mapping.

Create ten volume sections with 30 chapters each:
- Volumes 1-2: Arc 1;
- Volumes 3-4: Arc 2;
- Volumes 5-6: Arc 3;
- Volumes 7-8: Arc 4;
- Volumes 9-10: Arc 5.

Each volume must include promise, entry assumptions, identity movement, power boundary, story-memory focus, six movement blocks, exit checkpoint, and Chapter 301+ hook.

- [ ] Step 3: Define chapter slots.

For each volume, list six blocks of five chapter slots: setup, escalation, complication, character movement, consequence, and bridge. Number slots continuously from 001 through 300. Each slot records volume, arc, block, provisional function, permitted story-memory movement, and status PROVISIONAL.

- [ ] Step 4: Add the open continuation contract.

At Chapter 300, leave at least one active mystery, one unresolved Great Design/Fate question, one unexplored region or faction, one relationship consequence, and one future progression boundary. Explicitly identify Chapter 301+ as authorized for future planning but not yet detailed.

- [ ] Step 5: Update planning indexes.

Link the 300-chapter roadmap and replace the earlier unknown chapter horizon with the author-approved provisional horizon while keeping final publication count and chapter titles provisional.

- [ ] Step 6: Verify roadmap arithmetic and boundaries.

Run:

    $roadmap = Get-Content -Raw 08_PLANNING/300_CHAPTER_ROADMAP.md
    $volumes = ([regex]::Matches($roadmap, '^## Volume [0-9]{2}', 'Multiline')).Count
    $chapters = ([regex]::Matches($roadmap, 'Chapter [0-9]{3}', 'IgnoreCase')).Count
    if ($volumes -ne 10) { throw "Expected 10 volumes, found $volumes" }
    if ($chapters -lt 300) { throw "Expected at least 300 chapter slots, found $chapters" }
    if ($roadmap -notmatch 'Chapter 300') { throw 'Chapter 300 checkpoint missing' }
    if ($roadmap -notmatch 'Chapter 301') { throw 'Continuation hook missing' }

Expected: ten volumes, at least 300 numbered slots, a Chapter 300 checkpoint, and a Chapter 301+ continuation contract.

- [ ] Step 7: Commit.

    git add 08_PLANNING/300_CHAPTER_ROADMAP.md 08_PLANNING/README.md 08_PLANNING/VOLUME_MAP.md 08_PLANNING/CHAPTER_REGISTER.md
    git commit -m "docs: add provisional 300 chapter roadmap"

### Task 6: Run final structural validation

**Files:**
- Modify: 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md

**Interfaces:**
- Consumes: all files from Tasks 1–5 and the production/recheck protocol.
- Produces: evidence that the expansion is complete without certifying prose.

- [ ] Step 1: Verify required files and clean scope.

Run:

    $required = @(
      '06_REFERENCES/WRITING_RULES.md',
      '03_WORLD/HISTORY_PLAN.md',
      '02_CHARACTERS/CHARACTER_HISTORY_INDEX.md',
      '02_CHARACTERS/CHARACTER_HISTORY_TEMPLATE.md',
      '04_POWER_SYSTEMS/POWER_SYSTEM_BIBLE.md',
      '05_EVOLUTION/PROGRESSION_ROADMAP.md',
      '08_PLANNING/300_CHAPTER_ROADMAP.md'
    )
    $required | ForEach-Object { if (-not (Test-Path $_)) { throw "Missing file: $_" } }

- [ ] Step 2: Re-run ledger status checks.

Confirm that MY-001 through MY-008 are OPEN and FS-001 through FS-008 are PLANNED, with no planned record marked as canonized prose.

- [ ] Step 3: Re-run roadmap arithmetic.

Confirm ten volume headings and at least 300 chapter slots, with Chapter 300 and Chapter 301+ continuation language.

- [ ] Step 4: Confirm no manuscript or export was created.

Allow the existing structural README under 09_FUTURE_STORY; fail on other future-story files and any new WEBNOVEL_EXPORT prose.

- [ ] Step 5: Record evidence.

Add the commands and results to 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md. Record prose certification as NOT APPLICABLE and state that the 300-chapter roadmap is provisional.

- [ ] Step 6: Commit.

    git add 10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md
    git commit -m "qa: validate story architecture expansion"

## Final checklist

- [ ] Writing style and natural-author rules exist.
- [ ] Comedy rules preserve consequences.
- [ ] Planned MY/FS ledger IDs exist with safe statuses.
- [ ] World and character history planning exists.
- [ ] Power and non-System progression authority exists.
- [ ] Ten volumes and at least 300 chapter slots exist.
- [ ] Chapter 300 remains a checkpoint, not the ending.
- [ ] Chapter 301+ continuation hooks exist.
- [ ] No manuscript prose, synopsis, export, or Docker file was added.
