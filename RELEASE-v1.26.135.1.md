# HD FBDI Service – Release Notes

## Installation

Download **HD-FBDI-Service-install.exe** (attached below) and run it as **Administrator**.

The installer will:
- Install HD FBDI Service as a Windows Service (auto-start).
- Install HD FBDI Tray App into the `TrayApp` subfolder.
- Start the service and launch the tray app.

Running the installer over an existing installation performs an **in-place upgrade** automatically.

### Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```

## What's included

| Component | Description |
|-----------|-------------|
| HD FBDI Service | Windows background service for automated print-job processing |
| HD FBDI Tray App | Tray application for service monitoring and hotfolder alerts |

## Configuration

Service settings are stored in `C:\ProgramData\Heidelberg Praha\HD FBDI Service\`.  
Tray app settings are in `appsettings.json` next to `HD FBDI.TrayApp.exe`.

For full documentation see the [repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr#readme).
