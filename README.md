[中文版](README.zh-CN.md)

# Scientific Research Skills

Agent skills for scientific research work: reading papers deeply, writing life-sciences manuscripts, making publication-ready figures, and drafting Chinese patent disclosures.

These skills are designed for researchers who want an agent to do more than answer one-off questions. Each skill defines a workflow, quality checks, fallback behavior, and domain-specific judgment so the agent can work like a research assistant rather than a generic chatbot.

## Skills at a glance

| Skill | Best for | Main output |
| --- | --- | --- |
| `literature-mentor` | Understanding a paper deeply, especially figure by figure | Paper overview, figure-by-figure explanation, critique, and research ideas |
| `scientific-paper-writing` | Writing or revising life-sciences and omics manuscripts | Titles, abstracts, IMRAD sections, rebuttals, cover letters, polishing, self-review |
| `scientific-figure-making` | Producing publication-ready scientific figures | Figure plan, Python/R plotting code, export-ready figure guidance |
| `patent-disclosure-desktop` | Mining patent points and drafting Chinese technical disclosure documents | Patent-point list, prior-art comparison, disclosure draft, revision record |

## `literature-mentor`

### Summary

A mentor-style paper reading skill. It uses Zotero or web sources to retrieve papers, then helps the user understand the paper as if guided by a graduate supervisor: first the whole story, then each figure, then the methodological lessons and research inspiration.

### What it can help with

- Find a paper by title, DOI, or Zotero library search.
- Classify the paper's narrative type before reading: method/tool paper versus scientific-discovery paper.
- Give a structured overview: research question, background gap, main innovation, data scale, technical route, and the design logic behind key methodological choices.
- Explain each figure one by one instead of dumping a shallow full-paper summary.
- Combine three information sources for figure interpretation: figure legends, corresponding Results/Methods text, and tables or supplementary data.
- Detect when text is not enough and ask the user to upload the actual figure image.
- Mark evidence at three levels: direct evidence, reasonable inference, and speculation beyond the paper.
- Discuss methods, limitations, statistical choices, over-interpretation, and relevance to cattle genomics or population genetics.
- End with a compact synthesis: what problem the paper solves, how it solves it, what it found, and where it sits in the field.
- Generate research-oriented follow-up questions about hidden assumptions, boundary conditions, failure cases, and transferability to the user's own data.

### Typical prompts

```text
Use literature-mentor to explain this DOI figure by figure: ...
```

```text
Help me read this paper from Zotero like a supervisor. Focus on methods and reusable ideas.
```

### How it differs from similar paper-reading skills

| Compared with | Difference |
| --- | --- |
| Generic paper summarizers | Does not stop at abstract-level summaries; it pauses after each major figure and supports interactive questioning. |
| PDF chat tools | Explicitly checks whether figure legends and text are enough, and asks for images when visual evidence is required. |
| [`littleZ05/PaperLocus`](https://github.com/littleZ05/PaperLocus)-style paper positioning | Borrowed useful ideas such as narrative type, literature positioning, and claim/inference separation, but keeps a deeper figure-by-figure reading workflow. |

### References and lineage

The first version was built from scratch around the user's own workflow: Zotero-backed paper reading, mentor-style explanation, and population-genetics context. Later, [`littleZ05/PaperLocus`](https://github.com/littleZ05/PaperLocus) inspired several conceptual additions: narrative-type detection, literature-positioning summaries, and clearer separation between stated claims, causal inference, and extrapolation.

## `scientific-paper-writing`

### Summary

A life-sciences manuscript writing meta-skill. It covers the full manuscript lifecycle: ideation, title, abstract, introduction, methods, results, discussion, figures and tables, citation handling, cover letter, rebuttal, self-review, translation, and style polishing.

It is built for life-sciences and omics work, especially animal genomics, population genetics, domestication, adaptation, selection, introgression, landscape genomics, structural variation, pangenomes, imputation panels, and multi-omics integration.

### What it can help with

- Draft or revise manuscript sections with evidence-first logic.
- Improve titles, abstracts, introductions, methods, results, discussion, and figure captions.
- Polish paragraphs while preserving the user's meaning and avoiding AI-sounding prose.
- Check whether claims are supported by numbers, effect sizes, citations, or explicit evidence.
- Prepare rebuttals and cover letters with reviewer psychology in mind.
- Run manuscript self-review before submission.
- Translate between Chinese and English while preserving scientific precision.
- Route tasks into specialized reference files under `references/tasks/` and shared rules under `references/meta/`.

### Typical prompts

```text
Use scientific-paper-writing to revise this Results paragraph for a population-genomics paper.
```

```text
Help me write a conservative Discussion paragraph from these findings. Avoid over-claiming.
```

```text
Use this skill to draft a rebuttal to reviewer comment 2.
```

### How it differs from similar academic-writing skills

| Compared with | Difference |
| --- | --- |
| Generic academic-writing prompts | Focuses on life-sciences evidence chains, reviewer cognition, conservative claims, and concrete data support. |
| Field-agnostic polishing tools | Does not merely make text smoother; it checks logic, evidence, terminology, numbers, and over-claim risk. |
| Heavy multi-agent review systems | Keeps the workflow lightweight and task-routed instead of adding scoring rubrics or large review teams by default. |
| Philosophy or humanities-oriented academic skills | Built around IMRAD, data-driven claims, methods reproducibility, reviewer response, and omics manuscript conventions. |

### References and lineage

The first version began as a domain-specific `animal-popgen-paper-writing` skill. Its v1 rules were distilled from 14 animal population-genomics papers, then expanded into `life-sci-paper-writing` and finally `scientific-paper-writing`.

Selected ideas were later adapted from other sources:

| Reference source | Adapted ideas |
| --- | --- |
| Top-institution writing and figure-making resources | Stronger anti-AI-writing guidance, uncertainty phrasing, rhythm variation, and Discussion stance control. |
| [`Yuan1z0825/nature-skills`](https://github.com/Yuan1z0825/nature-skills) | Comment IDs, action tags for rebuttal, Hourglass checks, and section-move references. |
| [`Imbad0202/academic-research-skills`](https://github.com/Imbad0202/academic-research-skills) | Reviewer-comment decoding and Devil's Advocate self-check. |
| [`Galaxy-Dawn/claude-scholar`](https://github.com/Galaxy-Dawn/claude-scholar) | One-sentence argument checks and Claim Audit. |

Evaluated but not adopted: [`lishix520/academic-paper-skills`](https://github.com/lishix520/academic-paper-skills) because it was less aligned with life-sciences manuscript writing; broad numeric scoring rubrics, large multi-agent review teams, PPTX report generation, and generic Data Availability modules because they added weight without improving the core workflow.

## `scientific-figure-making`

### Summary

A publication-figure skill for scientific plots. It starts from the scientific claim, then decides the evidence hierarchy, chart type, backend, statistics, and export constraints before writing plotting code.

It supports both Python and R workflows. Python is used for matplotlib/seaborn-style figures; R is used when `ggplot2`, `patchwork`, `ComplexHeatmap`, `ggtree`, or population-genetics plotting conventions are a better fit.

### What it can help with

- Plan a figure around one core conclusion.
- Choose chart types based on evidence hierarchy, not habit.
- Generate grouped bars, trends, scatter plots, heatmaps, multi-panel layouts, Manhattan plots, XP-EHH regional plots, FST/pi heatmaps, PCA plots, ADMIXTURE/STRUCTURE bars, and phylogenetic trees with metadata.
- Decide whether Python or R is the right backend.
- Apply publication-oriented typography, palettes, layout, legends, vector export, and DPI rules.
- Use color-blind-safe palettes and grayscale checks.
- Check figures against submission requirements and common pitfalls.

### Typical prompts

```text
Use scientific-figure-making to design a multi-panel figure for this result.
```

```text
Draw a PCA figure, but first help me define the core conclusion and evidence hierarchy.
```

```text
Make an R ComplexHeatmap workflow for this annotated matrix.
```

### How it differs from similar visualization skills

| Compared with | Difference |
| --- | --- |
| Generic plotting helpers | Starts with the figure contract: conclusion, evidence hierarchy, chart type, backend, statistics, and export constraints. |
| Exploratory data analysis plotting | Focuses on publication-ready figures, not quick EDA screenshots. |
| Web visualization tools | Explicitly excludes Plotly, Altair, Bokeh, dashboards, and web-first interactive graphics. |
| Illustrator/Figma-first infographic workflows | Focuses on reproducible scientific plots and code-backed figure generation. |

### References and lineage

The original structure came from [`ChenLiu-1996/figures4papers`](https://github.com/ChenLiu-1996/figures4papers), especially the `scientific-figure-making/` folder and its reference-file layout. Later changes adapted ideas from:

| Reference source | Adapted ideas |
| --- | --- |
| [`ChenLiu-1996/figures4papers`](https://github.com/ChenLiu-1996/figures4papers) | Starting implementation, publication-figure references, demos, and plotting patterns. |
| [`Yuan1z0825/nature-skills`](https://github.com/Yuan1z0825/nature-skills) / `nature-figure` | R backend, Figure Contract, `figure-contract.md`, `r-backend.md`, and population-genetics figure types. |
| [`AcademicForge/scientific-visualization`](https://github.com/AcademicForge/scientific-visualization) | Okabe-Ito palette, grayscale checks, journal column-width references, and submission checklist. |

Evaluated but not adopted: large inline plotting snippets from [`AcademicForge/scientific-visualization`](https://github.com/AcademicForge/scientific-visualization), because they consumed context without adding decision structure; Flexoki colors, because they are better suited to UI/code aesthetics than scientific color-blind-safe figures.

## `patent-disclosure-desktop`

### Summary

A Chinese patent mining and technical disclosure drafting skill adapted for Claude Desktop on macOS. It helps turn project materials, code, design documents, or PPTs into candidate patent points and a structured technical disclosure draft.

### What it can help with

- Intake a technical topic, project materials, inventors, assignees, output path, and desensitization requirements.
- Scan design docs, code, Word files, PPTs, or pasted text.
- Extract candidate patent points and ask the user to confirm or merge them.
- Search prior art through CNIPA publication search and Google Patents.
- Draft a Chinese technical disclosure with background, invention content, technical solution, embodiments, figures, and claim skeleton.
- Generate Mermaid system and flow diagrams when appropriate.
- Save `.md` output and attempt `.docx` generation when tools are available.
- Recognize iteration intent, revise existing drafts, save new timestamped versions, and avoid overwriting older drafts.

### Typical prompts

```text
Use patent-disclosure-desktop to mine patent points from this project folder.
```

```text
Help me draft a Chinese technical disclosure for this algorithm.
```

```text
Revise section 3 of the existing disclosure and add one embodiment.
```

### How it differs from similar patent-writing workflows

| Compared with | Difference |
| --- | --- |
| Generic patent-writing prompts | Includes project scanning, patent-point mining, prior-art search, disclosure drafting, self-check, and iteration handling. |
| Claude Code-only patent workflows | Ported for Claude Desktop macOS with Desktop Commander and fallback behavior. |
| Manual disclosure templates | Helps reason through technical problems, technical effects, prior-art differences, and claim skeletons before drafting. |

### References and lineage

This skill has one clear external source: [`handsomestWei/patent-disclosure-skill`](https://github.com/handsomestWei/patent-disclosure-skill). The current version ports that Claude Code-oriented workflow to Claude Desktop macOS.

| Original Claude Code version | Desktop-adapted version |
| --- | --- |
| `cnipa_epub_search.py` with Playwright | Built-in web search over CNIPA and Google Patents. |
| Claude Code `Read` / `Write` / `Bash` | Desktop Commander-style file reading, writing, and shell fallback. |
| Python Office conversion scripts | Word MCP first, local scripts second, Markdown-only as final fallback. |
| Mermaid rendering through command-line tools | Mermaid code blocks by default, optional `npx mmdc` rendering. |
| Helper-script iteration logs | Desktop-friendly manual append/update flow. |

No other external skill repository was mixed into this one.

## Installation

### Option 1: Install the whole repository

Clone the repository and copy the skill directories into the skill folder used by your agent runtime.

```bash
git clone https://github.com/guoyingwei6/scientific-research-skills.git
```

Then copy one or more skill folders:

```bash
cp -R scientific-research-skills/literature-mentor ~/.codex/skills/
cp -R scientific-research-skills/scientific-paper-writing ~/.codex/skills/
cp -R scientific-research-skills/scientific-figure-making ~/.codex/skills/
cp -R scientific-research-skills/patent-disclosure-desktop ~/.codex/skills/
```

Replace `~/.codex/skills/` with the correct directory for your agent runtime.

Common locations:

| Runtime | Typical skill directory |
| --- | --- |
| Codex | `~/.codex/skills/` |
| Claude Code | `~/.claude/skills/` |
| Claude Desktop | Project Knowledge or user skill directory, depending on your setup |
| Gemini | `~/.gemini/skills/` |

Restart the agent after installing new skills.

### Option 2: Install only one skill

If your agent supports installing a GitHub subdirectory, install only the folder you need, for example:

```text
https://github.com/guoyingwei6/scientific-research-skills/tree/main/scientific-paper-writing
```

## Ask an agent to install it for you

You can also paste one of these instructions into an agent that has terminal or file access:

```text
Install the scientific-paper-writing skill from:
https://github.com/guoyingwei6/scientific-research-skills

Copy the scientific-paper-writing directory into your local skills directory, then verify that the skill is available after restart.
```

```text
Install all skills from:
https://github.com/guoyingwei6/scientific-research-skills

Copy literature-mentor, scientific-paper-writing, scientific-figure-making, and patent-disclosure-desktop into the current agent's skills directory. Do not copy unrelated files. Verify the installation.
```

For Claude Desktop, a practical prompt is:

```text
Use the skill folders from this repository as Project Knowledge:
https://github.com/guoyingwei6/scientific-research-skills

Install or import only the skill directories I need, and keep their SKILL.md files as the entrypoints.
```
