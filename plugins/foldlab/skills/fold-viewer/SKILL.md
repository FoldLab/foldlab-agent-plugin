---
name: fold-viewer
description: Install, integrate, configure, or customize the Fold Viewer React component in an application. Use for @foldlab/fold-viewer API and capability questions, not for authoring Fold Spec semantics.
---

# Fold Viewer integration

Help the user integrate the published `@foldlab/fold-viewer` package into their existing React application. Treat it as an embeddable component/library, not a standalone application: preserve the host application's layout, routing, design system, and package manager unless asked to change them.

## Integration workflow

1. Inspect the project's package manager, React version, bundler, existing styling conventions, and data-loading path. Check those against the versioned package requirements before changing dependencies. Do not replace or downgrade a host dependency just to match an example.
2. For the current `0.1.0` release, the package targets Fold Spec `1.0.0-draft.1`, React `>=18.2 <20`, Three.js `^0.180.0`, and Node.js `>=20.19` for development/build tooling. The API is pre-1.0 and can change. Prefer the checked-in package version and types when available; otherwise use the pinned [viewer release](https://github.com/FoldLab/fold-viewer/tree/v0.1.0) and [package reference](references/api.md).
3. Reuse the application's existing React and React DOM installations. Add `@foldlab/fold-viewer` and the required compatible Three.js peer if missing. Import `@foldlab/fold-viewer/styles.css` for the preset styling, or intentionally omit it when supplying a full custom composition/style layer.
4. Choose a source explicitly: validated in-memory document, browser `File`/`Blob`, or an application-selected URL. Do not fetch a URL merely because it appears in Fold Spec metadata. Keep document loading and trust decisions visible to the host application.
5. Start with `<FoldViewer>` and its built-in instruction/playback/settings controls. For a host-owned layout, compose `FoldViewerProvider`, `FoldViewport`, `FoldInstructions`, `FoldControls`, and `FoldSettings`, or use `useFoldViewer()` for custom controls. Use controlled props and callbacks only where the app needs to own state; otherwise prefer the package's internal state.
6. Preserve flexible sizing and theming: use CSS-compatible `width`/`height`, the `theme` tokens or `--fold-*` variables, standard root `className`/`style`/DOM props, or your own layout around the primitives. Keep viewer chrome colors separate from the source document's paper materials.
7. Verify the real integration in the host app (typecheck/build and, where available, a browser test). Include loading/error states and test a text-only or partial document when the app consumes varied lessons.

Read [the component API](references/api.md) for current exports and props. Read [capabilities and limits](references/capabilities.md) before claiming a file will animate or a feature is supported.
