---
name: m365-file-edit-prompt
description: Use when the user asks for prompts, instructions, or steps for Copilot in Word, Excel, or PowerPoint to edit a file. Produces one copy-and-paste prompt that walks in-app Copilot through the agreed edits step by step.
category: Productivity / Document Editing
---

# M365 File Edit Prompt

## Purpose

Convert the agreed file edits from the current conversation into one prompt that the user pastes once into Microsoft 365
Copilot in the relevant app. That Copilot then applies the edits one step at a time, pausing after each step so the user
can review and make manual changes before continuing.

## Instructions

1. Identify the target Microsoft 365 app (Word, Excel, or PowerPoint) from the conversation or file type.
2. Capture every agreed content, data, structural, and formatting change.
3. Preserve the user's terminology, intent, constraints, and desired tone.
4. Specify edit locations when known, such as:
   - Word headings, sections, paragraphs, tables, or references
   - Excel worksheets, tables, columns, ranges, formulas, or charts
   - PowerPoint slides, layouts, speaker notes, or visual elements
5. Divide the work into small, independently reviewable steps.
6. Order steps so each change can be applied, reviewed, and manually adjusted before the next step is applied.
7. Keep content changes and formatting changes in separate steps.
8. Make every distinct change its own step; do not combine changes into one step.
9. Include enough context in each step for it to be executed on its own at its point in the sequence.
10. For substantial or destructive changes, instruct in-app Copilot to preview the proposed change before applying it.
11. Include relevant preservation requirements within each step, such as retaining unaffected content, formulas,
    styles, links, comments, or accessibility features.
12. Do not invent missing file details, content, locations, or requirements.
13. Do not claim that any edit has already been completed.

## Output Requirements

- Return exactly one fenced code block that opens with three backticks followed by `text`, and closes with three
  backticks. The whole response is that one block.
- Do not put any text before or after the block: no introduction, explanation, usage guidance, checklist, or closing
  note.
- Start the block with the preamble below, with `<APP>` replaced by the target app (Word, Excel, or PowerPoint) and
  `<M>` replaced by the total number of steps.
- After the preamble, list every step in execution order.
- Start each step with a heading line in the form `### Step N of M — <concise descriptive title>`.
- Separate steps with a line containing only `---`.
- Do not use backticks anywhere inside the block. No inline code and no nested code blocks. Write formulas, names, and
  ranges as plain text.
- Use direct, imperative language suitable for Microsoft 365 Copilot.

## Preamble

Use this text verbatim at the top of the block, replacing only `<APP>` and `<M>`:

```text
You are Copilot in <APP>. What follows is a series of <M> editing steps for the open file.

Apply only Step 1 now. Never apply more than one step per reply.
After each step, stop, show what changed, and wait for me.
If I reject the change, ask me what to do instead.
If I accept the change, ask me whether to continue before starting the next step. This lets me make any manual edits I need first.
```

## Output Format

The response must look like this, with every step following the same pattern:

```text
You are Copilot in Word. What follows is a series of 3 editing steps for the open file.

Apply only Step 1 now. Never apply more than one step per reply.
After each step, stop, show what changed, and wait for me.
If I reject the change, ask me what to do instead.
If I accept the change, ask me whether to continue before starting the next step. This lets me make any manual edits I need first.

### Step 1 of 3 — Descriptive step title

Complete instruction for this step, including location and preservation requirements.

---

### Step 2 of 3 — Descriptive step title

Complete instruction for this step.

---

### Step 3 of 3 — Descriptive step title

Complete instruction for this step.
```
