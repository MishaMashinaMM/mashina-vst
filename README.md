# MASHINA VST

**Goal:** play M-VAVE FM1 firmware, especially **MASHINA**, as an instrument inside **FL Studio Producer Edition 20.9.2 (64-bit) on Windows 10**.

## Status: first Windows build prototype

The initial build uses the existing open-source [fm1-emu](https://github.com/joakimeriksson/fm1-emu) project. It runs actual firmware through an emulated FM1 rather than recreating sounds. It already supports host MIDI, stereo audio, a device panel, firmware package loading and song-state persistence.

The first build deliberately retains the upstream **FM-1** plugin name. It is **not yet a custom MASHINA-branded plugin**, and compatibility with FL Studio 20.9.2 has not yet been tested.

## Download a test build

Go to [GitHub Actions](../../actions/workflows/windows-vst3.yml), open a successful run on the development branch, and download the artifact named `mashina-vst-windows-x64-prototype`. If there is no completed successful run, no testable plugin has been produced yet.

Unzip the archive and follow [INSTALL-WINDOWS.md](INSTALL-WINDOWS.md). Both the VST3 and CLAP components must be installed; the Windows VST3 loads the CLAP component at runtime.

A compatible firmware `.fwsc` file is required and is **not** distributed by this project.

## What we will verify

- FM-1 appears as a VST3 instrument in FL Studio 20.9.2.
- MASHINA firmware boots and produces sound from Piano Roll MIDI.
- Stereo output and MIDI channels function as expected.
- Firmware settings and saved patches survive an FL Studio project reopen.
- UI controls and performance are practical for live and studio use.

## Development

- Target: Windows 10, x86-64, FL Studio Producer Edition 20.9.2.
- Build: [Windows VST3 workflow](.github/workflows/windows-vst3.yml), using a pinned upstream revision.
- Provenance and technical decisions: [UPSTREAM.md](UPSTREAM.md).
- Work takes place on a development branch; `main` remains untouched until verification.

### Credits

The emulator and original plugin are by [Joakim Eriksson and contributors](https://github.com/joakimeriksson/fm1-emu), under the upstream MIT license. MASHINA firmware is a separate project. The test build contains no firmware binaries.
