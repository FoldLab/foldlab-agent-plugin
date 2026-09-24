# Fold Viewer 0.1.0 capabilities and limitations

The current release targets Fold Spec `1.0.0-draft.1` and strict JSON documents. It is an early, pre-1.0 viewer; do not infer newer format or feature support from a later spec revision.

| Document content | Viewer behavior |
|---|---|
| `planned` | Text/metadata state; no model canvas claim. |
| `instructions` | Localized text-first lesson; no authored motion is invented. |
| `partial` | Plays only the declared resolved prefix; later instructions remain text. |
| `resolved` | Animates supported resolved operations. |
| Hinge, rigid, sampled operations | Uses authored operation geometry; sampled keys interpolate linearly. |
| Localized text and authored cameras | Supported within the current reader behavior. |
| Front/back colors and multiple sheets | Supported. |
| Unknown required playback extension | Animation is disabled with a diagnostic. |
| Full local layer relations | Geometry is shown with an explicit limitation; not a complete layer solver. |

Not supported in 0.1.0: `.foldlab` archives, external assets, textures/patterns, narration playback, authoring source compilation, a symbolic fold solver, collision simulation, print output, and decorative final presentation. Some unsupported data may remain in the input; preservation is not the same as rendering or validating it.

Structural validation and automated accessibility checks do not prove physical foldability, collision-free motion, human usability, screen-reader certification, or broad Fold Spec conformance. See the versioned [capability table](https://github.com/FoldLab/fold-viewer/blob/v0.1.0/docs/capabilities.md) and [roadmap](https://github.com/FoldLab/fold-viewer/blob/v0.1.0/ROADMAP.md) before promising behavior.
