# Fold Viewer component API reference

This is the API for `@foldlab/fold-viewer@0.1.0`. Confirm the exact version in the host project's lockfile and the [versioned package README](https://github.com/FoldLab/fold-viewer/blob/v0.1.0/packages/fold-viewer/README.md); pre-1.0 APIs may change.

## Install and render

```sh
npm install @foldlab/fold-viewer three
```

React and React DOM are peer dependencies (`>=18.2 <20`). Reuse compatible versions already installed by the application; do not install duplicate React runtimes. Node.js `>=20.19` is the viewer repository's development/build requirement.

```tsx
import { FoldViewer } from '@foldlab/fold-viewer';
import '@foldlab/fold-viewer/styles.css';

<FoldViewer
  source={{ kind: 'url', url: '/lessons/crane.fold.json' }}
  width="100%"
  height={560}
  theme={{ accent: '#5b5bd6', radius: '18px' }}
  onStepChange={(step, index) => console.log(step.id, index)}
/>
```

Supported `source` variants:

- `{ kind: 'document', document }` for a `FoldDocument` value.
- `{ kind: 'file', file, name? }` for a browser `File` or `Blob`.
- `{ kind: 'url', url, fetchOptions? }` for an explicit application-selected URL.

The component validates JSON and relevant references. URLs embedded inside Fold Spec documents are not automatically fetched.

## Composition and state

For app-owned layout, wrap custom elements in `FoldViewerProvider` and arrange `FoldViewport`, `FoldInstructions`, `FoldControls`, and `FoldSettings`. `useFoldViewer()` exposes the snapshot/actions for a design-system control panel. The default `<FoldViewer>` combines viewport, instruction card, playback controls, and announcer.

`stepId` and `playing` are controlled values when supplied with their corresponding callbacks; `defaultStepId` and `defaultPlaying` initialize internal state. Other current props include `locale`, `playbackRate` (`0.5`, `1`, `1.5`, `2`), `autoAdvance`, `viewMode`, and preference overrides. Callbacks include `onError`, `onLoad`, `onStepChange`, `onPlayingChange`, and `onProgressChange`.

The forwarded `FoldViewerHandle` exposes `getSnapshot`, `play`, `pause`, `togglePlayback`, `seek`, `next`, `previous`, `reset`, `setStep`, `setPlaybackRate`, `setViewMode`, and `setPreferences`.

## Sizing and appearance

`width` and `height` accept React CSS values. `theme` supports `accent`, `background`, `panel`, `foreground`, `muted`, and `radius`. Use root `className`/`style`, documented `.fold-*` selectors and `--fold-*` custom properties, or omit the optional preset CSS. Keep UI tokens separate from the source document's front/back paper colors.

See the [customization guide](https://github.com/FoldLab/fold-viewer/blob/v0.1.0/docs/customization.md) for examples and composition notes.
