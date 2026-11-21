# dsh-session-atlas

[简体中文](README.zh.md)

**Session Modular Improvement Plan.**

A modular program for differentiable, continuous improvement of the session experience.
One card, one row per enhancement, with an independent switch for each row.

- [Next actions](../dsh-next-actions/README.md) fills the composer when you select a suggestion below the reply.
- [Closing note](../dsh-session-caesura/README.md) saves the draft as a private note in this browser
  when you click the rest symbol `𝄽` beside Send after a turn.
- [Agent mode switch](../dsh-preset-switch/README.md) lets you select a preset from the chevron by the header label
  while the session is idle.

## Install

Requires DeepSeek Harness 0.2.2-rc.5 with the Web client.

1. Run `pnpm install` in this directory to resolve the linked source packages.
2. If any source bundle is installed independently in the target profile, record its switch state and remove the bundle.
   Both forms use the same row IDs, so merely turning off a row leaves the duplicate ID in place.
3. In **Plugins → Add plugin**, select this directory.
   Check that its card has three rows and restore their switch states.

[Project documentation](docs/README.md)
