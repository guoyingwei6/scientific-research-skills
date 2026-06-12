---
created: 2026-06-12 16:15
updated: 2026-06-12 18:08
---
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

## Origin and evolution

### `literature-mentor`

The `literature-mentor` skill was created from scratch rather than copied from an external GitHub repository. Its first version was built from a requirements discussion about how an agent should help read papers through Zotero MCP: retrieve full text when possible, explain the paper like a graduate supervisor, and guide the user through the article figure by figure.

The original design focused on a mentor-style reading workflow for life-sciences and population-genetics papers. It emphasizes an overall paper overview first, then detailed figure-by-figure interpretation based on three information sources: figure legends, corresponding Results or Methods text, and related tables or supplementary data. Because Zotero MCP may not extract PDF images directly, the skill explicitly checks whether text evidence is sufficient and asks for uploaded images when visual interpretation would otherwise be unreliable.

| Reference source | What was adopted or adapted |
| --- | --- |
| No external repository in the first version | The initial workflow was generated from the user's own requirements: Zotero-backed literature reading, mentor-like explanation, figure-by-figure pacing, and domain-aware critique for cattle genomics and population genetics. |
| `littleZ05/PaperLocus` | Inspired later conceptual additions: narrative-type detection for method/tool papers versus scientific-discovery papers, a literature-positioning summary item, and clearer separation between claims, causal inference, and extrapolation. |

Most of the core workflow remained unchanged after reviewing `PaperLocus`. The three-source synthesis framework, figure-by-figure stopping points, and information-sufficiency checks were kept because they were already stronger for deep paper reading than a more generic paper-location workflow. The resulting skill is therefore mainly original, with one later layer of conceptual refinement from `PaperLocus`.

Its practical strength is the reading rhythm: it does not dump a full-paper summary and stop. It first builds a paper-level map, then pauses after each major figure so the user can ask methodological or conceptual questions before moving on. At the end, it produces a compact three-part synthesis: what problem the paper addresses, what solution or method it uses, and what it actually found. The skill also keeps a three-dimensional reading stance: learning the method, criticizing the evidence, and extracting reusable ideas for the user's own genomics projects.

### `scientific-paper-writing`

The `scientific-paper-writing` skill was not copied from a generic academic-writing prompt. It began as a domain-specific writing skill for animal population genomics, originally named `animal-popgen-paper-writing`. The first version was built around the user's own research context: cattle genomics, population genetics, breed identification, genomic breed composition, selection, introgression, adaptation, imputation panels, structural variants, pangenomes, and life-sciences omics papers.

The v1 version was distilled from 14 high-level animal population-genomics papers, with examples spanning cattle domestication, landscape genomics, multi-omics, structural variation, pangenomes, goats, sheep, phylogeny, and population-genomics methods. The skill was later renamed to `life-sci-paper-writing` and then to `scientific-paper-writing`. Those name changes reflected a broader scope, but the core design stayed the same: start from the evidence logic of life-sciences research rather than from a universal essay-writing template.

Over time, the skill absorbed useful ideas from several public or community skill repositories and writing resources. The goal was not to merge everything, but to selectively borrow mechanisms that improved review-readiness, claim discipline, and manuscript workflow.

| Reference source | What was adopted or adapted |
| --- | --- |
| Top-institution writing and figure-making resources | Added stronger anti-AI-writing guidance in `references/meta/ai_artifacts.md`, including more concrete uncertainty phrasing, rhythm variation, stance expression in Discussion, and first-person judgment where appropriate. |
| `Yuan1z0825/nature-skills` | Inspired improvements in reviewer-response and polishing workflows: Comment ID tracking, action tags in `rebuttal.md`, Hourglass checks, and section-move references in `style_polish.md`. |
| `Imbad0202/academic-research-skills` | Inspired the Step 0 reviewer-comment decoding workflow in `rebuttal.md` and a Devil's Advocate self-check in `self_review.md`. |
| `Galaxy-Dawn/claude-scholar` | Inspired a one-sentence argument check in `outline.md` and a Claim Audit workflow in `self_review.md`. |

Some references were explicitly evaluated but not adopted. For example, `lishix520/academic-paper-skills` was judged less suitable because it focused more on philosophy and Claude Code conventions than on life-sciences manuscript work. Some mechanisms from other repositories, such as broad numeric scoring rubrics, multi-agent review teams, PPTX report generation, or generic Data Availability modules, were also left out because they would have made this skill heavier without improving the core writing workflow.

The resulting skill is therefore a hybrid: originally rebuilt for a concrete life-sciences research domain, then refined by selectively integrating good ideas from other skill systems. Its main difference from generic academic-writing skills is that it treats paper writing as an evidence-routing and reviewer-cognition problem: every title, abstract, result paragraph, discussion claim, figure caption, cover letter, and rebuttal should reduce reviewer effort while staying conservative about what the data can actually support.

Internally, it is organized as a meta skill rather than a single prompt. `SKILL.md` routes tasks such as title, abstract, introduction, methods, results, discussion, cover letter, rebuttal, self-review, style polishing, translation, and outline work into task-specific reference files. Cross-cutting rules live under `references/meta/`, including writing workflow, citation and naming conventions, over-claim control, reviewer psychology, and AI-artifact cleanup. This makes the skill easier to maintain than a flat, monolithic writing prompt.

### `scientific-figure-making`

The `scientific-figure-making` skill has a different origin. Its first version was based on the `scientific-figure-making/` skill folder from `ChenLiu-1996/figures4papers`, which provided the initial structure: `SKILL.md` plus reference files such as `api.md`, `design-theory.md`, `common-patterns.md`, `demos.md`, and `tutorials.md`.

That original version was useful as a publication-figure skill, but it was later reshaped for life-sciences and population-genetics use cases. The current skill is no longer just a matplotlib style helper; it is a figure-planning workflow that begins with the scientific claim, chooses the appropriate evidence hierarchy, and then selects the backend and chart type.

| Reference source | What was adopted or adapted |
| --- | --- |
| `ChenLiu-1996/figures4papers` | Served as the starting implementation and file structure, including the original publication-figure references and demo-oriented workflow. |
| `Yuan1z0825/nature-skills` / `nature-figure` | Inspired a major redesign: R backend support with `ggplot2`, `patchwork`, and `ComplexHeatmap`; the Figure Contract philosophy; `figure-contract.md`; `r-backend.md`; rewritten `SKILL.md`, `design-theory.md`, `api.md`, and `common-patterns.md`; and population-genetics chart types such as PCA scatter plots, ADMIXTURE bars, and XP-EHH regional plots. |
| `AcademicForge/scientific-visualization` | Inspired targeted additions: Okabe-Ito color-blind-safe palette guidance, grayscale testing rules, journal column-width references, and `references/submission-checklist.md` with general checks, population-genetics checks, and common pitfalls. |

Some evaluated ideas were intentionally not adopted. Large inline code snippets from `AcademicForge/scientific-visualization` were left out because they consumed context without adding much decision structure. The Flexoki color palette was also evaluated and rejected because it was designed more for UI/code aesthetics than for color-blind-safe scientific figures.

The resulting skill combines practical figure-generation patterns from `figures4papers` with a stronger scientific-design layer. Its emphasis is not merely "make a nice plot"; it asks what claim the figure must support, which panel carries the primary evidence, whether Python or R is the right backend, how the figure will survive print/export constraints, and whether domain-specific population-genetics conventions are being respected.

The skill also defines what it should not handle: interactive dashboards, exploratory-only plots without a publication target, and Illustrator/Figma-first infographics are deliberately out of scope. This keeps it focused on reproducible, publication-grade figures that can survive peer review, print/export requirements, and domain-specific interpretation.

### `patent-disclosure-desktop`

The `patent-disclosure-desktop` skill has a single clear external source: `handsomestWei/patent-disclosure-skill`. It was ported from that original Claude Code-oriented patent disclosure workflow and adapted for Claude Desktop on macOS. The skill itself keeps this credit in `SKILL.md`.

The core eight-step workflow was inherited from the original version: intake, project scan, patent-point mining, user confirmation, novelty search, outline, disclosure drafting, and self-review. The main changes were environment adaptations rather than a change in the patent-writing logic.

| Original Claude Code version | Desktop-adapted version |
| --- | --- |
| `cnipa_epub_search.py` with Playwright-based search | Built-in web search against sources such as `epub.cnipa.gov.cn` and Google Patents. |
| Claude Code file and shell tools | Desktop Commander-style file reading/writing with explicit fallback behavior. |
| Python scripts for Office document conversion | Tiered fallback: Word MCP if available, local scripts if available, or Markdown-only output. |
| Mermaid rendering through local command-line tooling | Mermaid code blocks by default, with optional rendering through `npx mmdc` if the environment supports it. |
| Iteration logs through helper scripts | Desktop-friendly manual append/update flow. |

No other external skill repository was mixed into this one. Its value is mainly in the port: it preserves the original patent-disclosure structure while making the workflow usable in a desktop agent environment that may not have Claude Code's exact toolchain.

The desktop version also adds practical guardrails for real drafting work: it recognizes iteration intent without requiring the user to say "iteration", saves revised drafts as new timestamped files rather than overwriting old versions, keeps a revision record, and runs an internal self-check for claim consistency, prior-art distinctions, terminology, Mermaid references, and desensitization before handing over the final disclosure.

## Installation

Install or copy the skill directories into the skill folder used by your agent runtime. For runtimes that support installing from GitHub, install the repository root or a specific subdirectory, depending on the runtime's conventions.

## Notes

- These skills are written to be portable across agent environments where possible.
- Some workflows mention optional tools such as Zotero, web search, Python, R, or desktop file-reading tools. The skill text includes fallback behavior when a tool is unavailable.
- No private credentials or local secrets should be committed to this repository.
