---
name: drawing-docs
description: Use when technical documentation needs diagrams, charts, process visualizations, architecture maps, sequence diagrams, state transitions, ERDs, timelines, concept maps, or Markdown-compatible visuals for GitHub and Obsidian.
---

# Drawing Docs Skill

Create documentation diagrams that clarify technical content without reducing Markdown portability.

## Core Principle

Prefer text-native, reviewable diagrams first. Use image-based drawings only when Mermaid cannot express the concept clearly.

## When to Use

- A technical article needs a process, architecture, dependency, lifecycle, sequence, state, data model, timeline, or comparison visual
- Existing documentation has dense prose that would be clearer as a diagram
- User asks to beautify, supplement, or explain documentation with charts or visuals
- Target output must work in Markdown, especially GitHub and Obsidian

## Do Not Use

- Pure decoration with no explanatory value
- Data charts where the underlying data is missing or unverifiable
- Obsidian-only embeds when the document must render on GitHub
- Excalidraw when a simple Mermaid diagram is enough

## Diagram Selection

| Need | Use | Notes |
|---|---|---|
| Process, workflow, decision path | Mermaid flowchart | Keep nodes short; label important edges |
| API/service interaction over time | Mermaid sequenceDiagram | Show actors, request/response, failure paths |
| Lifecycle or mode changes | Mermaid stateDiagram | Use for state transitions, not general flow |
| Classes, modules, schemas | Mermaid classDiagram or erDiagram | Prefer exact names from the document/code |
| Project timeline | Mermaid gantt or timeline | Include dates only when verified |
| Concept map, layered architecture, metaphor | Excalidraw | Export SVG/PNG for portable Markdown |
| Hand-drawn explanation or visual analogy | Excalidraw | Keep source editable and exported asset linked |

## Execution Flow

1. Read the surrounding documentation before drawing.
2. Identify the single idea the visual must explain.
3. Choose the simplest compatible format from the table.
4. Draft the diagram using accurate labels from the source text.
5. Add a short caption explaining what the reader should notice.
6. Verify rendering in the target environment when possible.
7. If using Excalidraw, keep the editable source and insert an exported SVG/PNG for GitHub compatibility.

## Compatibility Rules

- Prefer fenced `mermaid` blocks for GitHub + Obsidian Markdown.
- Avoid experimental Mermaid syntax unless the target renderer is verified.
- For Excalidraw, do not rely on `.excalidraw` or Obsidian wikilinks alone when GitHub rendering matters.
- Insert exported assets with standard Markdown image syntax: `![alt](./path/diagram.svg)`.
- Use Obsidian backlinks or wikilinks only as an additional convenience, not the only display path.

## Style Rules

- One diagram should explain one idea.
- Use consistent naming, direction, colors, and abstraction level.
- Keep labels concise; move detail into the caption or surrounding prose.
- Prefer left-to-right flow for pipelines and top-down flow for hierarchy.
- Use color only to encode meaning, not decoration.
- Every diagram needs meaningful alt text or an adjacent caption.

## Common Mistakes

| Mistake | Fix |
|---|---|
| Choosing Excalidraw for simple flows | Use Mermaid flowchart |
| Diagram duplicates prose without adding structure | Remove it or focus it on relationships |
| Too many nodes in one visual | Split into stages or layers |
| Unverified dates, metrics, or dependencies | Verify or omit |
| Obsidian-only embed breaks on GitHub | Export SVG/PNG and use Markdown image syntax |
