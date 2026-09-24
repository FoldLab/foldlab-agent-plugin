# Fold Spec validation and evidence boundaries

For the reference repository, install its declared Python requirements, then run `python tools/foldspec.py validate <document>`. `python tools/check.py` runs the repository's broader checks; `python tools/build_site.py` regenerates the offline docs. Read the repository's `AGENTS.md`, `CONTRIBUTING.md`, and release checklist for current source-generation commands and contribution requirements.

Validation is layered:

1. JSON parsing and JSON Schema check structural shape.
2. Semantic checks validate IDs, references, state/status rules, and other cross-field constraints.
3. Geometry checks cover the implementation's documented topology, continuity, and strain invariants.
4. Package checks validate declared archive entries and hashes against path/resource rules.
5. Human review is still needed for physical folding, instructional clarity, cultural/provenance context, and assistive-technology usability.

Use precise wording in reports: name the exact command, file, and result. A schema-only check explicitly skips semantic/geometry/asset checks. Passing the full reference checks does not certify physical foldability, collision-free motion, screen-reader support, accessibility, or conformance profiles not listed as implemented. Missing runtime tooling is different from a failed check; report which case occurred.
