# UI Improvements

[Chinese README](./README.zh-CN.md)

UI Improvements is a Codex++ tweak for the Codex desktop app. It is a local
fork of [`b-nnett/codex-plusplus-bennett-ui`](https://github.com/b-nnett/codex-plusplus-bennett-ui)
that keeps Bennett's quality-of-life tweaks and adds sidebar, composer,
project-list, and responsive layout refinements.

## Changes From Upstream

- Fork metadata is separated from the upstream package and points at this fork.
- Adds `main-sidebar-layout` to keep Codex++ tweak entries out of the main app
  sidebar while preserving Settings navigation.
- Adds responsive main-content spacing for narrower windows with visible
  sidebars, including fixes for root attribute selectors and layout churn.
- Stops layout flicker by avoiding the MutationObserver feedback loop caused by
  observing inline `style` mutations that this tweak writes itself.
- Refines the composer/session loading state with a compact animated spinner
  that is positioned for both normal and narrow layouts.
- Extends project sidebar polish with local color preference migration,
  grouped project backgrounds, project labels for chats, and project-path copy
  support.
- Keeps and continues the upstream slash menu, usage, message metrics, settings
  search, and sidebar chat workflow improvements.

## Features

- Hide Codex upgrade prompts.
- Show 5-hour and weekly usage in the sidebar.
- Show assistant message token metrics on hover.
- Add search to Codex Settings and keep Settings sidebar width aligned.
- Render the primary sidebar actions as a compact 2x2 grid.
- Add subtle project backgrounds, project colors, and project labels in the
  sidebar.
- Cmd/Ctrl-click sidebar chats for multi-select batch actions.
- Polish the composer slash menu with denser rows, favorites, clearer section
  states, and keyboard-friendly behavior.
- Show a compact session loading spinner above the composer.
- Hide Codex++ tweak pages from the main app sidebar and add responsive spacing
  to the main content area.

## Install

Install this repository as a tweak directory:

```sh
mkdir -p "$HOME/Library/Application Support/codex-plusplus/tweaks"
cp -R . "$HOME/Library/Application Support/codex-plusplus/tweaks/ui-improvements"
```

Then reload Codex++ tweaks from Codex, or restart Codex.

## Validate

```sh
node --check index.js
codexplusplus validate-tweak .
codexplusplus doctor
```

## Manifest

- Tweak id: see `manifest.json`
- Scope: `both`
- Entry: `index.js`
