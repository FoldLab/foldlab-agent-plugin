---
name: fold-spec
description: Explain, author, edit, or review machine-readable Fold Spec documents and their source, library, or scene files. Use when a task concerns the Fold Spec format, not general origami advice.
---

# Fold Spec authoring and review

Use this skill for `.fold.json`, `.foldsrc`, `.foldlib.json`, and `.foldscene` work, or when explaining what the specification and its reference tools do. Start with the user's checked-out repository instructions and the exact `specVersion` in the document. The normative chapters, `SPEC.md`, and versioned schemas form one contract; do not rely on remembered or newer behavior without confirming it against that edition.

## Workflow

1. Inspect the local `AGENTS.md`, `SPEC.md`, relevant normative chapter, matching versioned schema, and the applicable guide or fixture. If the relevant checkout is unavailable, use the pinned [Fold Spec release](https://github.com/FoldLab/fold-spec/releases/tag/v1.0.0-draft.1-beta.1) and identify that version in the answer.
2. Identify the document's `status` and keep its layers separate: authoring intent, resolved geometry/motion, instructional steps, and final presentation are not substitutes for each other. Do not invent missing motion, text alternatives, rights, or validation evidence.
3. Preserve stable material/document IDs, exact operation-to-step ranges, per-side appearance, primary and localized text, source/rights metadata, and explicit limitations when editing. Change linked references together when an intentional rename or mapping change is required.
4. Treat disagreement between normative prose and a schema as a defect to report. Do not quietly choose the more permissive interpretation. Never broaden a format-version compatibility claim based on a parser accepting some fields.
5. For repository changes, follow its contributor instructions. In the current reference repository, schema edits start in `tools/schema_source.py`; regenerate schemas with `python tools/schema_source.py`, regenerate `docs/field-reference.md` with `python tools/field_reference.py`, add valid and invalid fixtures for new syntax or constraints, then run `python tools/check.py` and `python tools/build_site.py`. Keep `.foldsrc` parser examples exactly equivalent to their JSON ASTs.
6. Report what was checked and what remains unsupported. Structural validation is not proof of physical foldability, collision-free motion, human usability, assistive-technology certification, a complete symbolic solver, or complete player support.

Read [the format reference](references/format-and-authoring.md) for file/status distinctions and current source links. Read [validation boundaries](references/validation.md) before reporting conformance or test results.
