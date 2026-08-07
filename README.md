# HD FBDI Service

**Automated JDF/JMF Export Service for Heidelberg Suprasetter**

Public distribution repository for HD FBDI Service — a Windows background service that monitors hotfolders and processes incoming print files (TIF, IMP) into JDF/JMF job packages for Heidelberg Suprasetter CTP devices.

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-brightgreen)
![.NET](https://img.shields.io/badge/.NET-10.0-purple)
![Service](https://img.shields.io/badge/type-Windows%20Service-blue)

---

## Downloads

Download the latest installer from the [Releases](../../releases) page.

- `HD-FBDI-Service-install.exe` — recommended installer; warns when the required x64 .NET 10 Windows Desktop or ASP.NET Core runtime is missing

---

## System Requirements

| Requirement | Minimum |
|---|---|
| **Operating System** | Windows 10 (64-bit) or Windows Server 2016 or later |
| **.NET Runtime** | 10.0 (must be installed separately) |
| **Permissions** | Local Administrator (service installation) |

---

## Installation

1. Download `HD-FBDI-Service-install.exe` from the Releases page.
2. Run as **Administrator**.
3. Follow the installation wizard.
4. Service starts automatically after installation.
5. Tray app launches and registers autostart.

Running the installer over an existing installation performs an **in-place upgrade** — no uninstall needed.

---

## Components

| Component | Description |
|---|---|
| **HD FBDI Service** | Windows background service — file watching, JDF/JMF export |
| **HD FBDI TrayApp** | Systray companion — service control, status monitoring, hotfolder backlog alerts |

---

## Configuration

Service settings are stored in:

```
%ProgramData%\Heidelberg Praha\HD FBDI Service\Settings.json
```

The color book is stored in `ColorBook.json`. Runtime job state is stored in `RuntimeState\JobList.json`.

On first start, missing JSON files are created with inert defaults. No hotfolder, export, or spool directories are created until configured.

Version `v1.26.162.4` was the last version that migrated `Settings.xml` and `ColorBook.xml` to JSON. Upgrades with XML-only configuration are blocked; run that version first or create the missing JSON files with the current configuration tool.

---

## Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```
