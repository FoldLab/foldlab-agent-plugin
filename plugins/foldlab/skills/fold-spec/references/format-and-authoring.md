# Fold Spec format and authoring reference

This skill targets Fold Spec `1.0.0-draft.1`, released as a beta implementer draft. Confirm the input document's `specVersion` and the user's local repository before applying these links to another edition.

## File and status map

| File | Meaning |
|---|---|
| `.fold.json` | A structured Fold Spec document containing metadata, paper sheets, accessibility/instructions, and optional authoring, resolved geometry, assets, narration, history, presentation, and print data. |
| `.foldsrc` | Readable source syntax for declarative construction intent. Parsing produces an authoring graph; it is not a symbolic-to-animation compiler. |
| `.foldlib.json` | A versioned, data-only construction library. Do not imply arbitrary code imports, runtime execution, or a fully implemented expander. |
| `.foldscene` | A reusable presentation scene with explicitly declared assets; it is not a lesson or replacement for motion. |
| `.foldlab` | A portable ZIP package with manifest and declared payloads. It is not the legacy FoldLab format. |
| `.fold` | Reserved for the established FOLD geometry interchange ecosystem; Fold Spec does not redefine it. |

Document status is one of `planned`, `instructions`, `partial`, or `resolved`. Planned records have no lesson steps or geometry; instruction-only documents have steps but no resolved motion; partial documents only animate their resolved prefix; resolved documents provide motion for all physical instructions. `resolved` does not mean physically validated, collision-free, or user-tested.

## Canonical sources

- [Specification index](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/SPEC.md)
- [Normative chapters](https://github.com/FoldLab/fold-spec/tree/v1.0.0-draft.1-beta.1/spec)
- [Versioned schemas](https://github.com/FoldLab/fold-spec/tree/v1.0.0-draft.1-beta.1/schemas/1.0.0-draft.1)
- [Fold Source grammar](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/grammar/fold-source.ebnf)
- [Authoring guide](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/docs/authoring-guide.md)
- [Quick start and CLI](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/docs/quickstart.md)
- [Implementation coverage](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/IMPLEMENTATION-STATUS.md)
- [Crane example notes](https://github.com/FoldLab/fold-spec/blob/v1.0.0-draft.1-beta.1/examples/crane/README.md)

## Authoring cautions

- Keep instruction, geometry, appearance, and final presentation as distinct layers. Do not use a decorative final mesh or image as a substitute for missing physical operations.
- A text alternative is part of the lesson, not merely a fallback label. Preserve the canonical step text, localization/fallback language, tactile details, and explicit review status.
- Preserve original IDs and exact step-to-operation ranges. A camera orbit is not a physical turnover; mountain/valley labeling alone does not define hinge direction.
- Named geometric constraints can have multiple solutions. A unique-branch request is a check; when needed, retain an explicit witness rather than choosing the first solution.
- Keep rights/source attribution and limitations attached to the material they describe. Do not invent provenance or claim evidence that is absent.
- Never load remote media or metadata as a side effect of reading a document. Resource limits, package paths, and hashes are part of security and integrity behavior.
