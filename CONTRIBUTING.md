# Contributing

Thanks for helping make FoldLab's agent guidance accurate and useful. Keep changes narrow and grounded in the source project or observed agent behavior.

## Before changing a skill

- Read the applicable source repository's current `AGENTS.md`, normative/versioned documentation, package types, and release notes.
- State which Fold Spec and Fold Viewer versions the guidance describes. Update links and the change log when those anchors intentionally change.
- Preserve exact technical distinctions and limitations. A Fold Spec structural check is not proof of physical foldability; the viewer's data preservation is not feature support.
- Keep the skill entrypoint focused. Move substantial reference detail into linked files under that skill's `references/` directory.
- Avoid copying upstream specification chapters or complete package documentation into this repository.

## Scope and review

V1 is static documentation and manifests. Do not add executables, hooks, MCP servers, auto-updaters, generated model files, package dependencies, or telemetry as an incidental cleanup. Propose such work against the [roadmap](ROADMAP.md) first and document its authority, data flow, failure modes, and user controls.

Before opening a pull request, run the available skill and plugin validators, `claude plugin validate --strict plugins/foldlab`, `claude plugin validate --strict .`, and inspect the rendered Markdown and all relative links. Report exact versions/commands and distinguish skipped checks from failures. Do not claim host installation or runtime behavior from a manifest-only validation.

Keep public manifests synchronized: plugin name and version must agree across portable, Codex, Claude, and both marketplace files. Use a changelog entry for user-visible changes. The `v1.0.0` release is not immutable in source, but published tags should not be moved or reused.

## Pull requests

Describe the user need, the changed source/version anchor, and how you checked it. Include manual evaluation cases for behavior changes. Do not include private lesson files, credentials, downloaded vendor pages, or build outputs.
