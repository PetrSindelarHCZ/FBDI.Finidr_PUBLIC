# HD FBDI Service - Release Notes v1.26.126.5

## Installation

Download **HD-FBDI-Service-install.exe** from the release assets and run it as **Administrator**.

- Install HD FBDI Service as a Windows Service with automatic startup.
- Install HD FBDI Tray App into the `TrayApp` subfolder.
- Start the service and launch the Tray App.

Running the installer over an existing installation performs an in-place upgrade. No uninstall is required.

### Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```

## Changes in this release

- Improved startup behavior when configured drives or hotfolders are unavailable.
- Added per-hotfolder attribution rules with a global fallback.
- Improved exception handling and reduced unnecessary job-state logging.
- Replaced timer handling with a periodic processing loop.
- Improved Tray App automatic startup registration.

## Configuration

Service settings are stored in `%ProgramData%\Heidelberg Praha\HD FBDI Service\`.
This release still uses the configuration format documented for the `v1.26.126.x` line.

## Notes

For current installation documentation see the [repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).
