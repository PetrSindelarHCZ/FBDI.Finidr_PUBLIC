# HD FBDI Service - Release Notes v1.26.217.1

## Installation

Download **HD-FBDI-Service-install.exe** from the release assets and run it as **Administrator**.

The installer will:

- Install HD FBDI Service as a Windows Service with automatic startup.
- Install HD FBDI Tray App into the `TrayApp` subfolder.
- Start the service and launch the Tray App.

Running the installer over an existing JSON-based installation performs an in-place upgrade. No uninstall is required.

This release includes all changes delivered since `v1.26.162.4`, the last version that migrated XML configuration to JSON.

### Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```

## Upgrade from older versions

Version `v1.26.162.4` was the last version that migrated `Settings.xml` and `ColorBook.xml` to JSON.

If an installation contains XML configuration without the corresponding JSON files, the installer blocks the upgrade to protect the existing installation. In that case, first run `v1.26.162.4`, or create the missing JSON files with the current configuration tool.

An upgrade is not blocked when old XML files remain next to valid JSON files.

## Configuration

Service configuration is stored in:

```text
%ProgramData%\Heidelberg Praha\HD FBDI Service\Settings.json
%ProgramData%\Heidelberg Praha\HD FBDI Service\ColorBook.json
```

Persistent runtime job state is stored in:

```text
%ProgramData%\Heidelberg Praha\HD FBDI Service\RuntimeState\JobList.json
```

A clean installation creates inert JSON configuration files. It does not create hotfolder, export, or spool directories until those paths are configured.

## Changes since v1.26.162.4

- More reliable processing of TIFF and IMP files that are still locked or being written. The service waits for readiness and retries without losing the job state.
- Operator controls for releasing, retrying, discarding, and deleting problematic job inputs.
- Continuation runs for files that arrive late, including links between the original and continuation job.
- Recovery of interrupted processing after service restart, including pending inputs, exports, and discarded data.
- Runtime job history and service status remain available across restarts.
- Configurable automatic and manual retention of old terminal jobs and discarded data.
- TrayApp controls for service start, stop, restart, job actions, runtime status, retention status, and locked-input diagnostics.
- Released inputs from a partially exported job are rediscovered automatically after they become available in the hotfolder, even when no new file watcher event is raised.
- The released input is processed as one continuation run through the normal stability and validation checks. Repeated polling does not create duplicate runs.
- Safer first start with JSON configuration defaults.
- Protected upgrades from XML-only configuration.
- Improved retention status refresh after service start and restart.
- Additional reliability checks for retention operations.
- Installer packaging validates that the TrayApp files required for IPC are present before creating the installer.

For general configuration details, see the [public repository README](https://github.com/PetrSindelarHCZ/FBDI.Finidr_PUBLIC#readme).

