# Upstream emulator and build provenance

The first MASHINA VST milestone **repackages an unmodified build** of
[Joakim Eriksson's fm1-emu](https://github.com/joakimeriksson/fm1-emu).
It is a technical compatibility prototype, not yet a custom-branded MASHINA plugin.

- Upstream source: https://github.com/joakimeriksson/fm1-emu
- Revision: `09aeae3e9d78db52c3b9f5ceed93bd1120ccf444` (2026-11-19)
- Upstream license: MIT. The build also uses upstream's declared plugin dependencies.
- Upstream Windows build: `tools/build_plugin.ps1`
- Format delivered: 64-bit VST3 wrapper **and** its companion CLAP library.
- Firmware: **not bundled**. Load a legally obtained `.fwsc` or compatible `.fm1save` through the plugin UI.

This pinned commit is intentionally fixed so a successful Windows build can be
reproduced. Update it deliberately after checking upstream release notes, changes,
license notices, and plugin functionality.

## Validation gates

1. GitHub Actions builds both plugin components and uploads the ZIP.
2. On Windows 10, FL Studio Producer Edition 20.9.2 (64-bit) detects the VST3.
3. MASHINA `.fwsc` firmware boots and accepts MIDI from FL Studio Piano Roll.
4. Audio reaches the FL Studio mixer without sustained dropouts.
5. Save/reopen a FL Studio project and verify presets and settings survive.
6. Verify multiple MIDI-channel tracks, UI controls and live latency.

Only step 1 is automated by this repository at present. None of steps 2–6
should be called validated until tested in the target DAW.

## Next milestone

After baseline FL Studio validation, introduce distinct plugin branding and
MASHINA-specific UX using the upstream source and documented licenses.
Avoid changing emulator timing or state handling until compatibility is proven.
