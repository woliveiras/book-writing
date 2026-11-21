# Book Writing

`book-writing` is a Codex skill for planning, drafting, and revising technical books. It helps you define what readers will be able to do, build chapters around real prerequisites, and make material easy to find again at the point of use.

## Install for Codex

The skills CLI requires Node.js 22.20 or later. Run this from the project where you keep your manuscript. [Skills CLI reference](https://www.skills.sh/docs/cli)

```sh
npx skills add woliveiras/book-writing --skill book-writing --agent codex
```

That installs the skill in the current project. To install from a local checkout, pass its path as the source.

```sh
npx skills add /path/to/book-writing --skill book-writing --agent codex
```

Confirm the installation with `npx skills list --agent codex`. To use the skill across projects, add `--global` to both the installation and verification commands.

## Use in Codex

Invoke `$book-writing` and tell Codex which deliverable you want. For planning, provide the reader, prerequisites, and a task the book should prepare them for. For drafting, include the outline, adjacent chapters if available, and the technical material. For revision, include the manuscript and say whether you want an editorial report or revised prose.

### Plan a book

```text
Use $book-writing to plan a technical book for archive staff who can
handle paper maps and operate a flatbed scanner. By the end, they
should be able to produce a scan that another staff member can trace
to the original sheet and verify.

Write an annotated table of contents. For each chapter, say what the
reader learns, how they can check their work, and which later chapter
uses the result. Identify sections staff can look up at the scanner.
```

### Draft a chapter

```text
Use $book-writing to draft the chapter on checking a map scan, using
the attached outline and the archive's inspection procedure. Readers
already know how to capture a scan and assign its record ID.

Open with a scan that looks complete until the reader checks the map
border. Explain what to inspect and what evidence calls for a new
scan. Close with a short practice check and show what readers should
carry into the handover chapter.
```

### Review a manuscript

```text
Use $book-writing to review my draft about digitizing paper maps.
Test whether each chapter teaches what later chapters assume.
Then enter through the table of contents as a staff member trying
to decide whether to rescan a map.

For each issue, give the passage, the effect on the reader, a proposed
revision, and a way to verify the repair. Check whether the glossary
entries and appendix forms are easy to find from the relevant steps.
```

## Limits

- **Technical accuracy.** Supply the technical facts, constraints, and examples the book should use. Verify technical claims, commands, and code before publication.
- **Editorial scope.** The skill works on book structure, chapter prose, and manuscript revision. Final fact-checking, rights clearance, typesetting, and production of print or ebook files are separate publishing tasks.
- **Source material.** The package contains general editorial guidance and original examples. Bring a brief or manuscript, plus any approved material the book needs to teach from.

## Repository layout

```text
skills/
└── book-writing/
    ├── SKILL.md
    └── references/
        ├── planning.md
        ├── drafting.md
        └── revision.md
```

The entry point directs Codex to the guide for the requested task. [Skill entry point](skills/book-writing/SKILL.md) · [Planning](skills/book-writing/references/planning.md) · [Drafting](skills/book-writing/references/drafting.md) · [Revision](skills/book-writing/references/revision.md)

Run `npx skills add . --list` from the repository root to check discovery.
