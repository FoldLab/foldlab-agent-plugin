# Repository guidance for implementation agents

- Keep this project a small, host-packaged set of instructions; do not turn it into the Fold Spec implementation or Fold Viewer application.
- Treat the canonical Fold Spec release and Fold Viewer package/repository version as authoritative. Confirm versions against user checkouts or published release artifacts before changing references.
- Preserve document semantics, stable IDs, operation-to-step mappings, appearance per side, text alternatives, rights, and explicit capability limits in Fold Spec guidance.
- Treat viewer layout as host-owned and composable. Keep installation, API, and feature support claims pinned to an actual package version.
- Report contradictions among normative prose, schemas, generated references, and implementation behavior; do not silently select the convenient interpretation.
- Keep v1 free of executable scripts, hooks, MCP servers, generated meshes, copied vendor manuals, and dependency/application build output. Propose future runtime features explicitly and account for user control, privacy, and security.
- Keep portable, Codex, and Claude metadata aligned with the marketplace catalogs and package version. Validate each supported host format before release; do not infer compatibility from file naming alone.
- Never describe structural or automated accessibility checks as physical validation, collision simulation, screen-reader certification, a full symbolic solver, or conformance beyond the documented implementation.
