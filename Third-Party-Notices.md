# VectoTask Third-Party Notices

**Draft inventory based on project declarations; reconcile against the exact Store package before distribution.** The project has a `THIRD_PARTY_LICENSES.md` that says license materials are bundled with builds. The source project metadata and license file do not fully establish exact versions, transitive dependencies, or which listed components are included in the submitted MSIX.

## Components identified by project materials

| Component | Role / evidence | Declared license / notice | Release verification required |
|---|---|---|---|
| PySide6, Shiboken6, Qt 6 | Runtime UI; `pyproject.toml` declares `PySide6>=6.6.0`; project notice says dynamically linked. | LGPLv3 (project-declared) | Capture exact Qt/PySide versions, binary linkage and modifications; include full license and relinking/replacement information required by the applicable LGPL version. |
| psutil | Runtime process/system monitoring; `pyproject.toml` declares `psutil>=5.9.0`. | BSD 3-Clause (project-declared) | Verify version and include complete copyright, conditions, and disclaimer. |
| winsdk | StoreContext and StartupTask projections are referenced by source/build documents; project notice declares MIT. Not listed as a direct dependency in `pyproject.toml`. | MIT (project-declared) | Verify included module/package and exact license/copyright notice in the packaged build. |
| Pillow | Used in the MSIX asset-generation script; project notice declares HPND. | HPND (project-declared) | Determine whether any Pillow code ships in the final app or was only a build-time tool; include notice if redistributed. |
| Python 3.11+ / standard library | Runtime declared in project metadata; README says Python 3.12+. | PSF license (project-declared) | Confirm actual bundled interpreter/runtime version and include applicable license notices. |
| SQLite / `sqlite3` | Local database; project notice says SQLite public domain. | Public domain dedication (project-declared) | Verify actual SQLite version/build and include any applicable notice. |
| Lucide icons | Project notice declares embedded SVG path coordinates. | ISC (project-declared) | Verify icons/assets and required copyright/license text. |

## Notice text and source

The project-root file `THIRD_PARTY_LICENSES.md` should be reviewed as the starting point for full component license texts and notices. Its current statements, dates, and exact distribution claims have not been independently verified. The submitted package should contain complete required texts and attribution in a customer-accessible location.

## Final-package steps

1. Generate a full direct and transitive software bill of materials from the exact packaged build, including PyInstaller-bundled modules, Python, Qt DLLs/plugins, and redistributables.
2. Identify build-time tools separately from components shipped to customers.
3. Compare the package contents to every item above and remove false/unshipped entries; add all missing libraries, fonts, icons, images, codecs, and runtimes.
4. Verify versions, copyright notices, license texts, modifications, dynamic-linking/relinking obligations, and redistribution requirements. Confirm that the package satisfies each component's terms, especially LGPL requirements and asset rights.
5. Publish the final notices at [PUBLIC HTTPS URL] and include them in the MSIX/install folder if required by license terms.
