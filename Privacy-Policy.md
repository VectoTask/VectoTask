# VectoTask Privacy Policy

**Effective date:** [DATE] 

**Last updated:** 7 November 2026 

**App version covered:** 1.0.6  

**Publisher / responsible entity:** [PUBLISHER NAME AS SHOWN IN MICROSOFT PARTNER CENTER]  

**Privacy contact:** VectoTask@gmail.com  

**Markets:** Worldwide

## 1. About this policy

This Privacy Policy explains how **VectoTask**, a Windows desktop application for creating and running workflow automations, handles information.

This policy applies to the VectoTask version distributed as an MSIX package through the Microsoft Store. If other editions, such as a standalone or development build, are distributed, their information-handling behavior may differ.

VectoTask is designed to store its workflow information and application records locally on your device. However, some features communicate with Microsoft Store services or other network destinations, as described below.

Microsoft independently handles information when you use Microsoft Store and related Windows services. Microsoft's handling of that information is governed by Microsoft's own privacy terms and policies. This policy does not replace Microsoft's privacy statement.

## 2. Information VectoTask stores on your device

Depending on how you use the application, VectoTask may store the following information locally:

- **Workflows:** Workflow definitions and visual workflow graphs, including triggers, conditions, actions, node configuration, names, and descriptions.
- **Drafts and autosaves:** Workflow drafts, saved graph information, and related view or editing state.
- **Application settings:** Theme and layout preferences, automation preferences, and Store update dismissal settings.
- **Keyboard shortcuts:** Configured shortcuts and their associated actions.
- **Activity records:** Workflow names, trigger information, execution status, actions performed, error messages, start and end times, and execution duration.
- **Application logs:** Operational messages, process names, workflow-related details, file paths, errors, and diagnostic or environment information.
- **Automations:** Any automations created  and its activity will be stored locally on the device 

For the MSIX version, the reviewed source uses the following application data location:

`%LOCALAPPDATA%\VectoTask\msix`

The standalone and development builds use separate locations:

- Standalone: `%LOCALAPPDATA%\VectoTask\standalone`
- Development: `%LOCALAPPDATA%\VectoTask\dev`

If `%LOCALAPPDATA%` is unavailable, the application may use a folder under the current Windows user's home directory.

The application may create subfolders for its database, drafts, logs, backups, and exports. Existing legacy VectoTask or FlowPilot data may also be migrated from `~/.vectotask` or `~/.flowpilot` into the active data directory, with a migration backup.

**Local storage security:** The reviewed source does not show encryption of the SQLite database, logs, or backup archives. These files should therefore be treated as ordinary files accessible to the Windows user and anyone else who can access that Windows account or device. Avoid storing sensitive secrets in workflows unless you accept the associated risks.

VectoTask provides user-requested data export, import, and backup features. Activity history can be cleared in the application, and individual workflows or drafts can be deleted. The reviewed source does not establish a general automatic expiry period for these records. Logs, backups, and exported files may remain until deleted by the user or removed through other confirmed cleanup behavior.

Uninstalling the application may not automatically delete information stored outside its installation directory. If you want to remove local application data, review the relevant data folders and back up anything you want to keep before deleting files.

## 3. Information used by local automation features

When enabled and configured, VectoTask's automation features may inspect or interact with information on your device, including:

- Running process names and process state.
- Configured keyboard shortcuts.
- Files and folders selected by you.
- Active application or window information.
- Relevant system state used by automation triggers.

The reviewed project source includes process monitoring, global hotkeys, window and application discovery, file and folder actions, desktop startup integration, and workflow activity logging.

These operations are performed on your device by the application. Resulting workflow information and activity details may be written to the local database or application logs described in Section 2.

Depending on your configuration, workflows may launch or close programs, open URLs in your default browser, simulate keyboard or mouse input, or act on files and folders you have selected.

You are responsible for reviewing your workflows and understanding their effects before enabling automatic execution.

---
## Artificial Intelligence and Generative AI

VectoTask's use of artificial intelligence and generative AI technologies, if any, depends on the features included in the application.

If a future version introduces features that use live generative AI models to create content in response to user inputs, this Privacy Policy will be updated to explain the relevant data processing practices, including any information shared with AI service providers.

Where applicable, users will also be provided with a means to report inappropriate AI-generated content to the developer.

## 4. Network communication

VectoTask includes certain features that may communicate over a network.

### 4.1 Internet connectivity checks

When a workflow evaluates an internet-connectivity condition, the reviewed source attempts a TCP connection to `8.8.8.8` on port `53` with a short timeout.

This address belongs to Google's public DNS service and is used by the connectivity check to determine whether a connection succeeds. The reviewed code does not include workflow content in this connectivity-check request.

Network providers may process connection metadata under their own terms and policies.

### 4.2 Microsoft Store update discovery

In the MSIX installation, VectoTask uses Windows `StoreContext` APIs after application launch and periodically thereafter to check whether application or package updates are available. The reviewed code sets a 24-hour timer for periodic checks.

These requests are handled through Windows and Microsoft Store services. The precise account, device, package, or other information processed by Microsoft is determined by Microsoft's services and is not fully specified by the reviewed VectoTask source.

VectoTask may also open a Microsoft Store URI when you choose to view the application in the Store.

Standalone builds do not perform the Store update checks described above.

For information about Microsoft's handling of information, consult Microsoft's applicable privacy statement and terms.

### 4.3 User-configured HTTP or webhook features

The reviewed project contains definitions for HTTP request and webhook workflow nodes. However, the source review did not establish that these nodes currently have a functioning request executor.

Accordingly, this policy does not claim that these nodes currently transmit workflow payloads. Their functionality and behavior must be verified against the exact released application package. If they become executable, this policy should be updated to explain what information may be sent, to which recipients, and for what purpose.

### 4.4 Browser and other external services

VectoTask can open URLs supplied by you in your default web browser. Any resulting communication is handled by the browser and the destination website or service, under their respective terms and privacy policies.

The reviewed source did not identify a VectoTask-operated analytics or telemetry endpoint. This observation is limited to the source reviewed and should not be interpreted as a guarantee about every bundled component or future release.

## 5. Purposes and sharing of information

VectoTask uses locally stored information to provide its application features, including:

- Creating, editing, and running workflows.
- Saving application settings and preferences.
- Maintaining workflow activity history and application logs.
- Supporting backup, restore, import, and export.
- Checking for Microsoft Store updates in the MSIX version.

The reviewed source did not identify a VectoTask-operated cloud account or service that receives locally stored workflow databases or application logs.

The publisher does not receive the local workflow and database contents through a publisher-operated server in the reviewed source. This statement is limited to the reviewed code and does not cover information you deliberately send to an external service through a workflow, browser, or other integration, or information processed by Microsoft Store and Windows services.

VectoTask does not control the privacy practices of Microsoft, your network provider, websites, or other external services.

## 6. Retention and deletion

VectoTask's local records generally remain on your device until you delete them or they are otherwise removed.

The reviewed source does not define a general retention schedule or automatic log-rotation period.

Depending on the feature, you can:

- Clear activity history using the application's controls.
- Delete individual workflows or drafts.
- Export information for your own backup.
- Import previously exported information.

Logs, backups, and exported files may remain on your device after you delete a workflow or clear activity history.

To remove local VectoTask data, review the application's data folders described in Section 2. Back up any information you want to retain before deleting these files.

For privacy questions or requests concerning information handled by the publisher, contact **VectoTask@gmail.com**. Because the reviewed application primarily stores workflow information locally, the publisher may not have access to a copy of your local workflow database.

## 7. Security

VectoTask stores the information described in this policy in local SQLite database files, logs, and related files on your device.

The reviewed source does not show encryption at rest, a publisher-operated cloud backup, or a publisher server storing these local records.

You are responsible for protecting your Windows account and device and for handling exported backup files carefully.

No method of electronic storage or transmission can be guaranteed to be completely secure.

## 8. Your choices and privacy rights

You decide whether to create workflows, configure automatic triggers, enable automation features, export backups, and open external URLs.

You can use the application's available controls to disable automation and clear activity history.

For privacy requests concerning information handled by the publisher, contact:

**Privacy contact:** VectoTask@gmail.com

Because VectoTask's reviewed source shows local storage and no publisher-operated account or cloud service, the publisher may not possess a copy of your local workflow data.

Depending on your country or region, you may have privacy rights such as requesting access to, correction of, or deletion of personal information, or raising an objection or complaint with a relevant privacy regulator. The availability and scope of these rights depend on applicable law.

**Making a privacy request**

To submit a privacy-related request, contact us at **vectotask@gmail.com**. Please describe your request and provide enough information for us to understand and respond to it. We may ask for reasonable information to verify your identity before processing a request.

We will review and respond to requests in accordance with applicable privacy laws. If you believe your privacy rights have not been respected, you may also have the right to contact the relevant privacy regulator in your country or region.

## 9. International processing

VectoTask's workflow database and application logs are stored locally on the user's device.

However, Microsoft Store update checks and network communications initiated by connectivity checks or user-selected external services may involve processing by providers operating in countries other than the user's own.

Microsoft's handling of information through Microsoft Store and Windows services is governed by Microsoft's applicable privacy terms and policies. The handling of information by other external services is governed by those services' respective privacy policies.

The publisher does not independently determine or control the locations where Microsoft or other external service providers process information. Where applicable, international processing and transfers are subject to the privacy laws and safeguards that apply to the relevant provider and service.

## 10. Changes to this policy and contact

We may update this Privacy Policy when VectoTask's features, information-handling practices, or applicable requirements change.

The latest version of this policy will be made available at:

[Public HTTPS Privacy Policy](https://github.com/VectoTask/VectoTask/blob/main/Privacy-Policy.md)

The **Last updated** date at the beginning of this policy indicates when it was most recently revised. Where required, we will provide additional notice of material changes.

For privacy questions or requests, contact:

**Publisher:** Harshvardhan Yadav  
**Privacy contact:** VectoTask@gmail.com  

---
© 2026 Harshvardhan Yadav. All rights reserved.
