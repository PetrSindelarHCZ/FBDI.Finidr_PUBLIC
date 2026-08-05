# HD FBDI Service - Release Notes v1.26.135.1

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

- Added the Service Configuration Editor for hotfolders, export folders, watched extensions, screening settings, attribution rules, and punch settings.
- Improved configuration validation and editor usability.
- Updated Tray App text and controls for clearer English-language operation.

## Configuration

Service settings are stored in `%ProgramData%\Heidelberg Praha\HD FBDI Service\`.

For current installation documentation see the [repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).
