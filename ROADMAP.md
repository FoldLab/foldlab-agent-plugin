# Roadmap

This roadmap describes possible growth beyond the v1 foundation. Items are directional, not release promises; sequence and scope may change based on user needs, source-project changes, and host support.

## V1.0.0 — two skills and host packaging

- `fold-spec`: version-aware help for authoring and reviewing Fold Spec documents.
- `fold-viewer`: package installation, component composition, controls, styling, and support-boundary guidance.
- Portable plugin identity plus Codex and Claude Code manifests and marketplace catalogs.
- Clear installation, contribution, security, and evaluation documentation.
- No executable plugin scripts, MCP server, telemetry, or separate npm package.

## V1.x — maintainable references and behavior checks

### 1.1 · Source/version maintenance

- Define a supported-version policy and update procedure for the Fold Spec and Fold Viewer source anchors.
- Add lightweight drift checks for release links, package versions, and references when changes in either source repository make it useful.
- Keep the skills concise; put version-specific details in small references rather than copying entire upstream manuals.

### 1.2 · Validation integration and evaluation

- Add opt-in workflows that invoke the canonical Fold Spec validator, source parser, package checks, or viewer consumer checks when those tools are available.
- Use upstream tools instead of reimplementing their semantics in a plugin script.
- Add representative valid/invalid fixtures and repeatable agent behavior evaluations for ID preservation, operation/step mapping, unsupported features, and component API accuracy.
- Report unavailable runtimes separately from test failures; do not turn successful structure checks into physical or accessibility claims.

### Later 1.x · Authoring aids

- Consider small deterministic helpers only for repeated tasks with demonstrated demand, such as inspecting a local document's version/status or scaffolding a minimal viewer integration.
- Keep generated content declarative, reviewable, and non-destructive. Never rewrite lesson geometry or author rights/evidence automatically.

## V2.0.0+ — optional documentation MCP

- Explore a read-only MCP service for querying versioned Fold Spec and Fold Viewer documentation with source citations.
- Make version selection explicit and preserve the origin/version of every answer; avoid silently mixing current docs with older input files.
- Keep ordinary skill use useful without MCP, network access, or credentials.
- Treat file validation as a separate, bounded capability: it should inspect only user-selected local files, use canonical upstream tooling where possible, and avoid network fetches from document metadata.
- Conduct security/privacy review and user testing before distributing any server or helper executable.

## Distribution and host coverage

- Add more agent-host manifests only when their formats and install paths are documented and tested.
- Consider official host directories or registries after eligibility, review, maintenance, and support expectations are understood. V1 does not submit to or imply inclusion in any directory.
- Automate release packaging and version consistency only after the release process has settled.

## Non-goals unless separately approved

- Publishing a new npm package or requiring an npm account.
- Automatically editing, converting, solving, or physically validating origami documents.
- Fetching arbitrary document URLs, executing document-supplied code, or claiming a full symbolic fold solver.
- Sending user files to a remote MCP service by default.
