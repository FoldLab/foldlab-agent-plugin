# Security policy

## Scope

V1 contains Markdown instructions and plugin metadata only. It does not bundle scripts, hooks, dependencies, an MCP server, or executable document content. Installing a plugin still grants its skills influence over agent behavior, so review source and updates before use.

Fold Spec documents and packages can contain URLs, assets, archives, and rights metadata. The `fold-spec` skill directs agents not to fetch document metadata automatically or treat embedded content as executable. The Fold Viewer skill advises choosing explicit data sources and preserving the host app's trust boundary.

## Reporting a vulnerability

Please report suspected vulnerabilities privately through [GitHub Security Advisories](https://github.com/FoldLab/foldlab-agent-plugin/security/advisories/new). Include the affected version, reproduction steps, impact, and any relevant files. Avoid putting sensitive details in a public issue. If private reporting is unavailable, contact a FoldLab maintainer through the organization page.

We will acknowledge reports, assess impact, and coordinate a fix and disclosure. No response-time guarantee is made by this initial policy.
