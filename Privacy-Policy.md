# VectoTask Privacy Policy

**Effective date:** [DATE]  
**App version covered:** [SUBMITTED VERSION]  
**Publisher / responsible entity:** [LEGAL PUBLISHER NAME AS SHOWN IN PARTNER CENTER]  
**Privacy contact:** [REAL EMAIL OR HTTPS CONTACT PAGE]  
**Markets:** [COUNTRIES/REGIONS]

## 1. About this policy

This policy explains information handling by **VectoTask**, a Windows desktop application for creating and running local workflow automations. The reviewed project describes VectoTask as formerly named FlowPilot. This policy covers the app and its publisher, [PUBLISHER NAME], for the [Microsoft Store/MSIX version — confirm] version. Microsoft independently handles information under Microsoft's own terms when you use Microsoft Store services; this policy does not replace Microsoft's privacy statement.

## 2. Information VectoTask stores on your device

The reviewed source uses SQLite and local files. Depending on your app use, the database can include:

- Workflows and visual workflow graphs, including trigger settings, conditions, actions, node configuration, names and descriptions.
- Workflow drafts and autosaves, including graph and view state.
- App settings, theme/layout preferences, automation preferences, and Store update dismissal settings.
- Keyboard shortcuts and their configured actions.
- Activity records such as workflow name, trigger type/details, status, actions performed, error messages, start/end times, and duration.
- Application logs. Logs can include operational messages, process names or workflow details, file paths, errors, and diagnostic/environment information.

The database and log files are stored locally under the environment-specific application data directory, normally `%LOCALAPPDATA%\VectoTask\msix` for the MSIX build, `%LOCALAPPDATA%\VectoTask\standalone` for the standalone build, and `%LOCALAPPDATA%\VectoTask\dev` for development. If `%LOCALAPPDATA%` is unavailable, the source uses a folder under the current user's home directory. The app creates database, drafts, logs, backups, and exports subfolders. Existing legacy VectoTask/FlowPilot data may be migrated from `~/.vectotask` or `~/.flowpilot` into the active data directory, with a migration backup.

The source does not show encryption of the SQLite database, logs, or backup archives. Treat local app data and exported backup ZIP files as ordinary files accessible to the Windows user and anyone else who can access that Windows account/device. Do not store secrets in workflows unless you accept that risk.

The app has user-requested export/import and backup behavior. The source does not establish an automatic expiry period for these records. Activity history can be cleared in the app; deleting an individual workflow/draft is supported. Logs, backups, and old exports may remain until the user deletes them or other cleanup behavior is confirmed. Uninstall behavior for data stored outside the installation directory has not been verified; back up or manually remove app data if desired, after confirming what will be lost.

## 3. Information used by local automation features

When enabled/configured, local automation features may inspect running process names and state, keyboard shortcuts, selected files/folders, active application/window information, and system state to trigger workflows or perform actions. The project source includes process monitoring, global hotkeys, window/app discovery, file/folder actions, desktop startup integration, and workflow activity logging. These operations are performed on the device by the app, but resulting workflow details may be written to the local database or log as described above.

Automations can launch or close programs, open URLs in the default browser, manipulate keyboard/mouse input, and act on user-selected files or folders. You choose workflow settings and are responsible for their effects. Review workflows before enabling automatic execution.

## 4. Network communication

The reviewed source includes these network-related behaviors:

- **Connectivity condition:** When a workflow evaluates the internet-connectivity condition, the app attempts a TCP connection to `8.8.8.8` on port 53 with a short timeout. This contacts Google's public DNS service to determine whether a connection succeeds. The source does not send workflow content as part of this check. Network provider logs/metadata may be governed by that provider's terms.
- **Microsoft Store update discovery:** In an MSIX installation, the app calls Windows `StoreContext` APIs after launch and periodically (the code sets a 24-hour timer) to ask whether app/package updates are available. The request is handled through Windows/Microsoft Store services. The project source does not specify the precise account/device/package data Microsoft processes; consult Microsoft's privacy materials. The code also opens a Microsoft Store URI when a user chooses to view the app in the Store. Standalone builds skip these Store update checks.
- **User-configured HTTP/webhook nodes:** Definitions for HTTP request and webhook nodes exist in the workflow registry, but the reviewed source did not reveal a working request executor for them. Therefore this policy does not represent that these nodes currently transmit payloads. Their status and behavior must be confirmed against the exact release package; if executable, this section must be revised to explain recipients and data sent.
- **Other destinations:** The app can open URLs supplied by the user in the default web browser. Any resulting browser/service communication is controlled by the browser and destination service. No app-server analytics or telemetry endpoint was identified in the reviewed source, but bundled components and the final release package must still be audited before making a broader “no telemetry” claim.

## 5. Purposes and sharing

Local information is used to provide the app's workflow, settings, activity history, logging, backup/restore, and update-notification features. The source review found no VectoTask-operated cloud account or service. Microsoft Store update queries and the connectivity check described above are network communications. If user-configured request integrations become executable, their external services will be selected by the user and require separate disclosure here.

The publisher does not receive the locally stored workflow/database contents through a publisher-operated server in the reviewed source. This statement is limited to the reviewed code and does not describe information a user deliberately sends to an external service through a workflow or browser, or information handled by Microsoft Store/Windows.

## 6. Retention and deletion

Local records remain on the device until deleted by the user or otherwise removed. The reviewed code does not define a general retention schedule or automatic log rotation. Users can clear the app's activity history and delete workflows/drafts in the app; users can also export/import data. To request deletion of app data, [PROVIDE VERIFIED IN-APP OR FILESYSTEM INSTRUCTIONS AND CONTACT]. Confirm installer uninstall behavior and any retained app-data behavior before publication.

## 7. Security

VectoTask stores the described data in local SQLite files and logs. The source reviewed does not show encryption at rest, a cloud backup, or a publisher server storing these records. Protect your Windows account and device, and handle exported backup files carefully. No method of storage or transmission can be guaranteed completely secure.

## 8. Your choices and rights

You choose whether to create workflows, configure automatic triggers, export backups, and use external URLs. You can disable automation and clear activity history using app controls. For privacy requests concerning information handled by the publisher, contact [PRIVACY CONTACT]. Because the reviewed source shows local storage and no publisher-operated account/service, the publisher may not possess a copy of your local workflow data. Rights and remedies depend on your location; [PUBLISHER: add required local rights and regulator contact information for target markets].

## 10. International processing

VectoTask's reviewed workflow database and logs are stored on the user's device. Microsoft Store update discovery and user-chosen external services may involve processing outside the user's country. [ADD verified destinations and safeguards as required for target markets.]

## 11. Changes and contact

We may update this policy to reflect changes in the app or applicable requirements. The current policy will be available at [PUBLIC HTTPS PRIVACY POLICY URL]. [DESCRIBE notice for material changes, if applicable.]

Privacy questions: **[PUBLISHER LEGAL NAME]**, [POSTAL ADDRESS IF REQUIRED], [PRIVACY EMAIL], [HTTPS SUPPORT PAGE].

---

**Internal notes — remove before publication:** The source readme describes the app as “offline-first,” but source includes Store update queries and a TCP connectivity check; avoid “strictly offline” and “no transmission” claims. Source review did not execute/capture a release build or inspect all transitive binaries. App version and publisher identity are inconsistent/incomplete across files; see Evidence Register.
