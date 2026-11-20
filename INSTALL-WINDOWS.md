# MASHINA VST — Windows test build

This is currently the upstream **FM-1** plugin built for compatibility testing;
the name shown in FL Studio will be **FM-1**, not MASHINA VST.

Unzip the archive. You must install **both** components:

1. Copy the entire `FM-1.vst3` directory to
   `C:\Program Files\Common Files\VST3\`.
2. Copy `FM-1.clap` to
   `C:\Program Files\Common Files\CLAP\`.
3. Restart FL Studio Producer Edition 20.9.2 (64-bit), then run a plugin scan
   in its Plugin Manager. Find the FM-1 instrument.
4. Open its UI and use **Load firmware / save…** to select your MASHINA
   `.fwsc` firmware package. It is **not included** in the archive.
5. Add notes in the Piano Roll, select the desired firmware MIDI channel
   mapping, and check the FL Studio mixer output.

If the FM-1 VST3 fails to load, check that both files are installed in the
correct folders. The Windows VST3 wrapper loads the companion CLAP at runtime.

This is an **unsigned development build** from third-party upstream source.
Review provenance in UPSTREAM.md before installation.

Please report the exact FL Studio plugin-scan result, whether MASHINA boots,
whether notes produce audio, and whether saved projects reopen correctly.
