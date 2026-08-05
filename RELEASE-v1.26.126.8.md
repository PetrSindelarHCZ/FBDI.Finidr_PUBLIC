# HD FBDI Service - Release Notes v1.26.126.8

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

- Added JSON-based settings and color-book handling as part of the configuration transition.
- Improved configuration loading and preparation for the later JSON-only migration baseline.

## Configuration

Service settings are stored in `%ProgramData%\Heidelberg Praha\HD FBDI Service\`.

For current installation documentation see the [repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).
