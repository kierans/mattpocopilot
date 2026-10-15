---
name: m365-file-edit-prompt
description: Writes sequential, app-specific handoff prompts for supervised file editing with Microsoft 365 Copilot.
category: Productivity / Document Editing
---

# M365 File Edit Prompt

## Purpose

Convert agreed file edits from the current conversation into a single Markdown file containing separate, sequential prompts for Microsoft 365 Copilot in the relevant app.

## Instructions

1. Identify the target Microsoft 365 app from the conversation or file type.
2. Capture every agreed content, data, structural, and formatting change.
3. Preserve the user’s terminology, intent, constraints, and desired tone.
4. Specify edit locations when known, such as:
   - Word headings, sections, paragraphs, tables, or references
   - Excel worksheets, tables, columns, ranges, formulas, or charts
   - PowerPoint slides, layouts, speaker notes, or visual elements
5. Divide the work into small, independently reviewable prompts.
6. Order prompts so each change can be applied, reviewed, and manually adjusted before the next prompt is used.
7. Keep content changes separate from formatting changes.
8. Create a separate prompt for every distinct change; do not combine prompts.
9. Include enough context in each prompt for it to be executed independently at its intended step.
10. For substantial or destructive changes, instruct in-app Copilot to preview the proposed change before applying it.
11. Include relevant preservation requirements within each prompt, such as retaining unaffected content, formulas, styles, links, comments, or accessibility features.
12. Do not invent missing file details, content, locations, or requirements.
13. Do not claim that any edit has already been completed.

## Output Requirements

- Return one Markdown file containing all handoff prompts.
- Give every prompt a concise, descriptive Markdown heading.
- Place each prompt’s complete text inside its own fenced text code block.
- Present prompts in execution order.
- Keep every prompt separate, even when several prompts affect the same section, worksheet, slide, or file.
- Separate content-editing prompts from formatting prompts.
- Output only the titled prompts; do not add introductions, explanations, usage guidance, verification checklists, or closing notes.
- Use direct, imperative language suitable for pasting into Microsoft 365 Copilot.

## Output Format

Use the following Markdown code block as a guide when creating Markdown files with prompts

````markdown
### 1. Descriptive prompt title

```text
Complete, copy-ready prompt for Microsoft 365 Copilot.
```

### 2. Descriptive prompt title

```text
Complete, copy-ready prompt for Microsoft 365 Copilot.
```
````