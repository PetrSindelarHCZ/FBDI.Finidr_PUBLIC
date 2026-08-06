# HD FBDI Service - Release Notes v1.26.218.2

## Installation

Download **HD-FBDI-Service-install.exe** from the release assets and run it as **Administrator**.

The installer will:

- Install HD FBDI Service as a Windows Service with automatic startup.
- Install HD FBDI Tray App into the `TrayApp` subfolder.
- Start the service and launch the Tray App.

Running the installer over an existing JSON-based installation performs an in-place upgrade. No uninstall is required.

### Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```

## Upgrade notes

No configuration migration is required when upgrading from `v1.26.217.1`. Existing service configuration and runtime job history are preserved.

For older XML-based installations, first upgrade through `v1.26.162.4`, the last version that migrated `Settings.xml` and `ColorBook.xml` to JSON. The current installer blocks an XML-only upgrade to protect the existing configuration.

## Changes since v1.26.217.1

- A redesigned TrayApp separates everyday job control from service configuration.
- Job views now group work that requires attention, is processing, is completed, or was discarded, with live counts for each view.
- Job details and available actions are clearer, with improved status explanations, confirmation dialogs, and a compact, collapsible detail panel.
- Multiple jobs can be selected for compatible actions, with improved keyboard navigation.
- New or changed job incidents raise tray notifications. Selecting a notification opens the affected job directly.
- The tray menu shows how many jobs currently require attention.
- Service status is shown with clearer animated icons, and Start, Stop, and Restart controls are enabled according to the current state.
- The job and settings windows remember their position, size, and maximized state while remaining visible after monitor-layout changes.
- The complete TrayApp interface is available in Czech, English, and German. The default `system` setting follows the Windows display language when supported.
- New light- and dark-theme tray icons improve visibility across Windows themes.
- Fixed job-list status display and handling of locked jobs when no spool folder is configured.

## Configuration

Service configuration remains stored in:

```text
%ProgramData%\Heidelberg Praha\HD FBDI Service\Settings.json
%ProgramData%\Heidelberg Praha\HD FBDI Service\ColorBook.json
```

Persistent runtime job state remains stored in:

```text
%ProgramData%\Heidelberg Praha\HD FBDI Service\RuntimeState\JobList.json
```

TrayApp window placement and notification state are stored in:

```text
%ProgramData%\Heidelberg Praha\HD FBDI Service\UiSettings.json
```

For general configuration details, see the [public repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).

