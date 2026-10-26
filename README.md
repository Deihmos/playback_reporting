# Playback Reporting - playback exclusions

An unofficial fork of [faush01/playback_reporting](https://github.com/faush01/playback_reporting), an Emby Server plugin for collecting and displaying playback statistics.

## Added in 2.1.0.8

- **Exclude audio playback** checkbox.
- **Excluded libraries** list populated from your Emby server; select any libraries to stop logging their playback.
- Save confirmation and error feedback.
- Library exclusions use server IDs, so library renames preserve selections.
- Existing history is retained. Both options are disabled by default.

## Download and install

Download the ZIP from [Releases](https://github.com/Deihmos/playback_reporting/releases).

1. Stop Emby Server.
2. Back up your existing `plugins/playback_reporting.dll` outside the plugins directory.
3. Replace it with `playback_reporting.dll` from the ZIP.
4. Start Emby and refresh the web interface.
5. Open **Playback Reporting  Settings  Playback exclusions**, select your options, and click **Save exclusions**.

Stop ongoing playback before saving exclusions for a clean boundary. Exclusions apply to new playback logging; they do not remove existing history or filter imported history.

To revert, stop Emby, restore your original DLL, and restart. A future plugin update may replace this custom build.

## Build

Install a .NET SDK supporting netstandard2.0, then run:

```sh
dotnet build playback_reporting/playback_reporting.csproj -c Release
```

The DLL is written to `playback_reporting/bin/Release/netstandard2.0/`.
NuGet access is required. Building does not automatically install the plugin.

## Validation

- Release build passed with no warnings or errors.
- Eight C# checks exercised audio exclusions, library exclusions, legacy settings, and missing items.
- JavaScript checks covered library loading, saved selections, safe library names, preserving unrelated settings, and loading failures.
- JavaScript syntax and Git whitespace checks passed.

**Not yet tested in a running Emby server.** Verify included and excluded playback after installing.

## Attribution and license

Based on upstream version 2.1.0.7, commit `30d39f9934051ccd7a0536eb7db3acf3434f125b`.
Playback exclusions and optional build installation were added on October 26, 2026.

Distributed under [GPL-3.0](LICENSE). Original copyright and license notices are retained.

