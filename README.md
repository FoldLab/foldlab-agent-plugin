# FoldLab Agent Plugin

Two focused skills that help AI coding agents work accurately with [Fold Spec](https://github.com/FoldLab/fold-spec) documents and the [Fold Viewer](https://github.com/FoldLab/fold-viewer) React component.

**V1 vision:** make FoldLab's format and component easier for people to use with their existing agents and projects, while keeping the canonical specification and package documentation authoritative. The plugin gives agents concise, version-aware guidance; it does not replace those projects, execute a validator, or grant a model new permissions.

| Skill | Use it for |
|---|---|
| `fold-spec` | Explain, author, edit, or review `.fold.json`, `.foldsrc`, `.foldlib.json`, and `.foldscene` files. |
| `fold-viewer` | Install, embed, control, theme, or compose `@foldlab/fold-viewer` in an existing React app. |

V1 is documentation-only: Markdown skills and small host manifests/catalogs. It includes no executable scripts, MCP server, telemetry, or separate npm package. Skills are host-neutral instructions, but plugin installation remains host-specific. The portable Agent Plugins manifest records a standard package identity; it does not imply that every agent client supports the same plugin behavior.

## Install

### Codex

In Codex CLI, add the public GitHub repository as a marketplace and install its plugin:

```sh
codex plugin marketplace add FoldLab/foldlab-agent-plugin
codex plugin add foldlab@foldlab
```

### Claude Code

In Claude Code, add the marketplace and install the plugin:

```sh
claude plugin marketplace add FoldLab/foldlab-agent-plugin
claude plugin install foldlab@foldlab
```

These commands add the marketplace/plugin to the respective local agent installation. Start a fresh agent session after installation so the new skills are discovered. To remove it later, use the matching host's plugin uninstall and marketplace remove commands.

### From a local checkout

Clone this repository, change to its root, then use the same marketplace name with the local path:

```sh
git clone https://github.com/FoldLab/foldlab-agent-plugin.git
cd foldlab-agent-plugin
codex plugin marketplace add .
codex plugin add foldlab@foldlab
```

For Claude Code, use `claude plugin marketplace add .` followed by `claude plugin install foldlab@foldlab`.

## V1 scope and version anchors

The skills are grounded in the following published versions and must not imply broader support:

| Project | V1 reference | Important boundary |
|---|---|---|
| Fold Spec | [`1.0.0-draft.1` beta](https://github.com/FoldLab/fold-spec/releases/tag/v1.0.0-draft.1-beta.1) | Implementer draft, not a ratified standard; reference tools implement documented subsets. |
| Fold Viewer | [`@foldlab/fold-viewer@0.1.0`](https://www.npmjs.com/package/@foldlab/fold-viewer/v/0.1.0) · [release source](https://github.com/FoldLab/fold-viewer/tree/v0.1.0) | Pre-1.0 component; only strict JSON for the pinned Fold Spec version and its documented subset. |

The viewer does not currently accept `.foldlab` archives or compile `.foldsrc`; it is not a symbolic solver, collision simulator, or proof of physical foldability. Read its [capability limits](https://github.com/FoldLab/fold-viewer/blob/v0.1.0/docs/capabilities.md) before promising animation or rendering. A passing structural/accessibility check is not physical validation or assistive-technology certification.

The skills include pinned links for offline repository work. If a project has a local checkout, follow its current `AGENTS.md`, versioned normative sources, schemas, package types, and lockfile first. If those sources contradict each other, report the mismatch rather than silently preferring one.

## Repository layout

```text
.
├── README.md
├── ROADMAP.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── AGENTS.md
├── .agents/plugins/marketplace.json       # Codex marketplace
├── .claude-plugin/marketplace.json        # Claude Code marketplace
├── docs/evaluation-cases.md               # Manual behavior checks for v1
└── plugins/foldlab/
    ├── plugin.json                        # Portable Agent Plugins manifest
    ├── LICENSE
    ├── .codex-plugin/plugin.json          # Codex presentation metadata
    ├── .claude-plugin/plugin.json         # Claude Code plugin metadata
    └── skills/
        ├── fold-spec/
        │   ├── SKILL.md
        │   └── references/
        └── fold-viewer/
            ├── SKILL.md
            └── references/
```

## Development and release checks

The CI workflow checks manifest JSON, the Claude plugin and marketplace, and skill metadata. Before a release, run:

```sh
for manifest in plugins/foldlab/plugin.json plugins/foldlab/.codex-plugin/plugin.json plugins/foldlab/.claude-plugin/plugin.json .agents/plugins/marketplace.json .claude-plugin/marketplace.json; do
  python -m json.tool "$manifest" >/dev/null
done
claude plugin validate --strict plugins/foldlab
claude plugin validate --strict .
```

The JSON checks verify syntax only. Claude Code's strict validator checks its plugin/marketplace structure and skill metadata. Maintainers can additionally run the Codex plugin creator's validator when that authoring tool is available; the repository does not vendor a separate validator. CI does not duplicate Fold Spec semantic validation or Fold Viewer runtime testing. See [evaluation cases](docs/evaluation-cases.md), [contributing](CONTRIBUTING.md), and the [roadmap](ROADMAP.md).

## License

MIT. See [LICENSE](LICENSE) and the plugin's included [license](plugins/foldlab/LICENSE).
