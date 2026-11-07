
# VectoTask — Microsoft Store Legal Package

Last updated: 6 November 2026  
Application version reviewed: 1.0.6  
Project identity: VectoTask (formerly FlowPilot)

This repository contains the legal documentation and compliance preparation materials for VectoTask, a Windows desktop workflow automation application.

This is a working publication package. Some source behavior is established below, but this was a bounded source review, not an independent network capture, package certification, security review, or legal audit.

Complete the remaining fields and verify all disclosures against the exact release build and actual Microsoft Partner Center package before publication.

---

## Documents

The following documents are included in this repository:

1. [Privacy Policy](https://github.com/VectoTask/VectoTask/blob/main/Privacy-Policy.md)
2. [End User License Agreement (EULA)](https://github.com/VectoTask/VectoTask/blob/main/EULA.md)
3. [Third-Party Notices and Licence Register](https://github.com/VectoTask/VectoTask/blob/main/Third-Party-Notices.md)

---

## Summary of Source Evidence

### 1. Local Data Storage

SQLite stores the following information locally:

- Workflows and workflow graphs.
- Workflow drafts.
- Application settings.
- Configured shortcuts.
- Workflow activity records.

The application also writes a persistent `vectotask.log` file.

Application data is stored under the following environment-specific locations:

- Development: `%LOCALAPPDATA%\VectoTask\dev`
- MSIX: `%LOCALAPPDATA%\VectoTask\msix`
- Standalone: `%LOCALAPPDATA%\VectoTask\standalone`

If `%LOCALAPPDATA%` is unavailable, the application uses a fallback directory under the user's home directory.

Exact per-environment subfolders and migration from legacy `~/.vectotask` and `~/.flowpilot` directories are documented in the Evidence Register.

### 2. Network Communication

The reviewed source identifies these network-related behaviours:

- **Connectivity testing:** A connectivity condition opens a TCP connection to `8.8.8.8` on port `53` when that condition executes.
- **Microsoft Store update discovery:** MSIX installations query `StoreContext` shortly after launch and subsequently every 24 hours.
- **Store APIs:** Windows Store APIs are used for update discovery.

No app-server telemetry, analytics, or crash-upload code was identified in the reviewed source search. This is not a guarantee for every bundled binary or future application build.

### 3. HTTP and Webhook Nodes

HTTP request and webhook node definitions exist in the visual workflow node registry.

However, the reviewed executor and source search did not identify an implementation that executes these request types.

These nodes may therefore be nonfunctional or Coming Soon, despite their displayed definitions.

The application can also open user-configured URLs in the system browser.

The exact release behaviour must be verified before making customer-facing statements about these features.

### 4. MSIX Package Identity and Capabilities

The generated MSIX manifest:

- Requests `runFullTrust`.
- Declares a Windows startup task.
- Uses the candidate identity `VectoTask.Desktop`.
- Uses the test publisher `CN=VectoTask-Test-Dev`.

These are development/test values, not confirmed Microsoft Store identity values.

The installer script contains a candidate GitHub URL, but repository ownership and public support availability have not been verified.

### 5. Third-Party Dependencies

The project's existing third-party notice file lists:

- PySide6 / Qt
- psutil
- winsdk
- Pillow
- Python
- SQLite
- Lucide

This declared inventory must be reconciled with the actual transitive dependencies and contents of the exact Store package.

The project dependency metadata lists PySide6 and psutil but does not list every build/runtime component claimed by the existing notice.

---

## Important Privacy and Licensing Warning

The existing project `LICENSE` contains statements describing VectoTask as strictly offline and stating that it does not transmit information.

These statements conflict with the reviewed source, which includes connectivity testing and Microsoft Store update queries.

**Do not publish the conflicting privacy paragraph as written.**

The project owner should correct the statements before distribution and ensure that all public legal documents accurately describe the application's actual behaviour.

---

## Microsoft Store References

The following official Microsoft documentation is relevant to the release process:

- [Privacy Policy and Support Information for MSIX Apps](https://learn.microsoft.com/en-us/windows/apps/publish/publish-your-app/msix/support-info)
- [Enter App Properties for MSIX Apps](https://learn.microsoft.com/en-us/windows/apps/publish/publish-your-app/enter-app-properties)
- [Create an App Submission for MSIX Apps](https://learn.microsoft.com/en-au/windows/apps/publish/publish-your-app/msix/create-app-submission)

Microsoft makes publishers responsible for providing a valid privacy policy where required. Declared package capabilities can affect whether Partner Center requires one.

Confirm the current requirements directly in Partner Center when preparing the submission.

---

**VectoTask**

*Automate. Simplify. Achieve.*

---
© 2026 Harshvardhan Yadav. All rights reserved.
