# Session Modular Improvement Plan

[简体中文](README.zh.md)

Four independently switchable features for continuing a conversation or wrapping up a turn.

- [Next actions](../dsh-next-actions/README.md).
  Click a suggestion below a reply to put it in the composer for editing.
- [Closing note](../dsh-session-caesura/README.md).
  After a turn, click `𝄽` beside Send to save the draft as a private note in this browser.
- [Agent mode switch](../dsh-preset-switch/README.md).
  When the session is idle, open the menu beside the preset name in the header.
- [Session sounds](../dsh-session-sounds/README.md).
  On macOS Desktop, hear a cue when a reply finishes or the session needs your response.

## Install

Requires the Web client on DeepSeek Harness `0.2.2-rc.5`.

1. Run `pnpm install` in this directory.
2. If any included plugin is installed separately in this profile, note its switch state
   and remove its bundle to avoid duplicate plugin IDs.
3. In **Plugins → Add plugin**, select this directory.
   Restore any saved switch states on the new card.

[Maintenance and verification](docs/README.md)
