# HD FBDI Service - Release Notes v1.26.162.4

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

- Added the Test Sender to the installer package and improved its sample-file workflow.
- Added JSON manifest-based sample loading and cleaner packaging exclusions.
- Improved installer version handling, console interaction, and packaging reliability.
- Improved persistence behavior when job-list access is temporarily denied.

## Configuration

This release is the last version that migrates legacy `Settings.xml` and `ColorBook.xml` configuration to JSON.

Service settings are stored in `%ProgramData%\Heidelberg Praha\HD FBDI Service\`.

For current installation documentation see the [repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).
