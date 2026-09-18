# Story Planning Setup Design

**Date:** 2026-09-18  
**Task class:** `STRUCTURAL_CHANGE`  
**Status:** Approved in chat; implementation follows after this design record

## Goal

Create the pre-production planning foundation for *This Isekai Has a Bug. Unfortunately, It's Me.* before any prologue, synopsis, numbered chapter prose, or publication export is created.

## Authority boundary

The repository instructions in `AGENTS.md` and `00_PROJECT/` control workflow. The imported `08_PLANNING/MASTER_STORY_PLAN.md` controls story direction. The downloaded document at `C:/Users/PK/Downloads/This_Isekai_Has_a_Bug_FINAL_Master_Plan.md` is source material only; its embedded prose or formatting is not repository workflow unless separately approved.

The setup must preserve the authority order:

`MASTER STORY PLAN -> PROJECT CANON -> ARC PLAN -> CHAPTER ENTRY STATE -> CHAPTER PROSE -> EXIT STATE / QA`

When the master plan does not establish a fact, the setup must write `UNKNOWN / NOT ESTABLISHED`. In particular, the number of volumes, number of chapters, chapter titles, protagonist's pre-reincarnation name, and detailed cast are not established by the current authority.

## Approved design

### 1. Planning index

Extend `08_PLANNING/README.md` with the current planning status, authority boundary, and links to the volume map, arc plans, and chapter register. The index must clearly state that the five arcs are roadmap material and that no numbered prose exists.

### 2. Context and structural gate

Complete or reconcile `10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md` as the evidence record for this setup. It must identify this work as `STRUCTURAL_CHANGE`, list the inspected authority files, record the imported master plan, mark unsupported facts as unknown, and leave prose certification as not applicable because no prose is produced.

### 3. Volume map

Create `08_PLANNING/VOLUME_MAP.md`. It will define the currently approved planning containers without silently assigning canon:

- series title and optional subtitle from the master plan;
- one initial planning container marked `Volume count: UNKNOWN / NOT ESTABLISHED`;
- the five master-plan arcs listed as roadmap arcs;
- volume assignment, chapter ranges, volume title, and volume ending state marked unknown until author approval;
- the gate that a book/volume authority must exist before numbered chapter prose.

The map is a planning index, not a new story authority that can override the master plan.

### 4. Arc plans

Create one file for each master-plan arc under `08_PLANNING/`:

- `ARC_01_THE_MAN_WHO_THINKS_HES_DEADPOOL.md`
- `ARC_02_THE_GLITCH_VS_FANTASY.md`
- `ARC_03_THE_DEMON_KINGS_CONFUSION.md`
- `ARC_04_THE_GODS_NOTICE_HIM.md`
- `ARC_05_THE_FOURTH_WALL.md`

Each file will use the existing arc-template fields, but only fill facts directly established by the master plan. It will include purpose, known plot boundary, arc ending gate, identity movement, System/progression boundary, fourth-wall stage, mystery obligations, and an explicit unknown chapter map. No chapter title or event will be invented.

### 5. Chapter register and template rule

Create `08_PLANNING/CHAPTER_REGISTER.md` as the single planning index for future chapter slots. It will list each arc and use `UNKNOWN / NOT ESTABLISHED` for chapter count, chapter titles, chapter ranges, and status until the author approves a volume/arc breakdown.

Update `07_TEMPLATES/CHAPTER_TEMPLATE.md` with a prose-length requirement: every future numbered chapter must target at least 1,000 words, record the actual word count, and remain uncertified if it falls below that target unless the author explicitly approves an exception. The length rule applies to chapter prose, not planning files, synopsis, or context receipts.

## Files and responsibilities

| File | Responsibility |
| --- | --- |
| `08_PLANNING/README.md` | Navigation and planning status |
| `10_QA/STRUCTURAL_SETUP_CONTEXT_RECEIPT.md` | Evidence and go/no-go record for this setup |
| `08_PLANNING/VOLUME_MAP.md` | Provisional volume/arc container map |
| `08_PLANNING/ARC_01_*.md` through `ARC_05_*.md` | Master-plan-derived arc boundaries |
| `08_PLANNING/CHAPTER_REGISTER.md` | Future chapter slots and title/status register |
| `07_TEMPLATES/CHAPTER_TEMPLATE.md` | Required chapter planning and 1,000-word gate |
| `docs/superpowers/plans/2026-09-18-story-planning-setup.md` | Executable implementation checklist |

No files will be created under `09_FUTURE_STORY/` because no chapter prose is authorized yet.

## Validation

The setup is valid when:

1. Every new planning file identifies its authority and does not invent missing canon.
2. Each of the five arcs matches the corresponding master-plan purpose and ending boundary.
3. The chapter register contains no fabricated chapter number or title.
4. The chapter template contains the explicit 1,000-word minimum and actual-count field.
5. The structural context receipt records inspected sources and the remaining unknowns.
6. A repository text check finds no numbered chapter prose under `09_FUTURE_STORY/`.
7. The applicable QA/check scripts pass, or the result is reported as uncertified with the exact reason.

## Out of scope

- Prologue, synopsis, or chapter prose.
- Final volume count or chapter count.
- Invented character names, locations, factions, or detailed world mechanics.
- New canon not present in the master plan.
- Publication exports.
- Copying files or canon from the companion bat-saga repository.
