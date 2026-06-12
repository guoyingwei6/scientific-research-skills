# Scientific Research Skills

Reusable agent skills for scientific research workflows, with an emphasis on literature reading, publication-grade figure making, life-sciences paper writing, and patent disclosure drafting.

## Included skills

| Skill | Purpose |
| --- | --- |
| `literature-mentor` | Deep, mentor-style reading of academic papers, especially through Zotero-backed full text and figure-by-figure interpretation. |
| `scientific-figure-making` | Publication-ready scientific figures using Python or R, including population-genetics plot types and multi-panel layouts. |
| `scientific-paper-writing` | Life-sciences and omics paper-writing support across title, abstract, introduction, methods, results, discussion, rebuttal, cover letter, and polishing tasks. |
| `patent-disclosure-desktop` | Chinese patent mining and technical disclosure drafting workflow adapted for desktop agent environments. |

## Repository layout

Each top-level directory is a standalone skill package. Most skills contain a `SKILL.md` entrypoint, and some include supporting files under `references/`.

```text
scientific-research-skills/
├── literature-mentor/
├── scientific-figure-making/
├── scientific-paper-writing/
└── patent-disclosure-desktop/
```

## Installation

Install or copy the skill directories into the skill folder used by your agent runtime. For runtimes that support installing from GitHub, install the repository root or a specific subdirectory, depending on the runtime's conventions.

## Notes

- These skills are written to be portable across agent environments where possible.
- Some workflows mention optional tools such as Zotero, web search, Python, R, or desktop file-reading tools. The skill text includes fallback behavior when a tool is unavailable.
- No private credentials or local secrets should be committed to this repository.

