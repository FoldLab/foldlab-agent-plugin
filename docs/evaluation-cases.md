# V1 manual evaluation cases

These prompts are a small qualitative checklist for reviewing skill behavior. They are not a benchmark, automated conformance suite, or certification. Record the model/host and source versions when using them.

## Fold Spec skill

1. **Preserve exact mappings:** Ask for a change to one instruction in a resolved document. Pass when the agent inspects operation ranges and preserves unrelated IDs, mappings, appearance, rights, localized text, and limitations.
2. **Text-only lesson:** Ask to add a missing animation to an `instructions` document that has no resolved geometry. Pass when it does not invent mesh/motion and instead keeps the status honest or asks for authored resolved data.
3. **Normative/schema mismatch:** Provide conflicting chapter and schema requirements. Pass when the agent identifies the contradiction and points to both locations rather than weakening the document to pass one check.
4. **Validation claim:** Ask whether passing `python tools/check.py` proves a model physically foldable or screen-reader certified. Pass when the answer distinguishes structural/geometric checks from human/physical review and names actual evidence.
5. **Legacy file ambiguity:** Ask whether a `.fold` file is a Fold Spec document. Pass when the agent does not infer this from the suffix and checks the declared format/version.

## Fold Viewer skill

6. **Existing React application:** Ask to embed the viewer into an app with its own CSS and controls. Pass when the agent checks React/Three.js compatibility, retains host layout, and offers `<FoldViewer>` versus primitives without imposing a fixed page design.
7. **Unsupported archive:** Ask to load a `.foldlab` package with viewer `0.1.0`. Pass when the agent states this release does not accept the archive and does not suggest that an arbitrary extraction or conversion is supported.
8. **Accessibility overclaim:** Ask whether automated checks certify a viewer for screen-reader users. Pass when the agent describes the tested behaviors precisely and recommends human assistive-technology review rather than claiming certification.

## Cross-skill routing

9. **Boundary selection:** Ask how to write a `.foldsrc` parser and then how to embed a supported JSON file in React. Pass when format semantics route to `fold-spec`, component integration routes to `fold-viewer`, and both references agree on the pinned format version.
