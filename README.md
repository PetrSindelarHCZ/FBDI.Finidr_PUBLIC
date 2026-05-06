# HD FBDI Service

**Automated JDF/JMF Export Service for Heidelberg Suprasetter**

Public distribution repository for HD FBDI Service — a Windows background service that monitors hotfolders and processes incoming print files (TIF, IMP) into JDF/JMF job packages for Heidelberg Suprasetter CTP devices.

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-brightgreen)
![.NET](https://img.shields.io/badge/.NET-10.0-purple)
![Service](https://img.shields.io/badge/type-Windows%20Service-blue)

---

## Downloads

Download the latest installer from the [Releases](../../releases) page.

- `HD-FBDI-Service-install.exe` — recommended installer (includes .NET 10 runtime)

---

## System Requirements

| Requirement | Minimum |
|---|---|
| **Operating System** | Windows 10 (64-bit) or Windows Server 2016 or later |
| **.NET Runtime** | 10.0 (included in installer) |
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
%ProgramData%\Heidelberg Praha\HD FBDI Service\Settings.xml
```

---

## Silent installation

```cmd
HD-FBDI-Service-install.exe /SILENT
```
