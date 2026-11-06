# VectoTask Third-Party Notices

**Version:** Draft — pending final package verification

VectoTask uses or references third-party software and resources. Their respective authors and licensors retain their rights to those components. This document identifies components declared in the project materials; it does not confirm that every listed component is included in every VectoTask distribution.

The exact versions, transitive dependencies, and contents of the submitted Microsoft Store package must be verified before distribution. The project includes a `THIRD_PARTY_LICENSES.md` file that is intended to provide license texts and notices.

## Components identified in project materials

| Component | Purpose / project evidence | License declared by project | Verification status |
|---|---|---|---|
| PySide6, Shiboken6, Qt 6 | User interface runtime. `pyproject.toml` declares `PySide6>=6.6.0`; project notices describe dynamic linking. | LGPLv3 (project-declared) | Exact versions, linkage, modifications, and applicable license obligations require verification. |
| psutil | Process and system monitoring. `pyproject.toml` declares `psutil>=5.9.0`. | BSD 3-Clause (project-declared) | Exact version and complete required copyright, conditions, and disclaimer require verification. |
| winsdk | StoreContext and StartupTask functionality are referenced in project source/build materials. It is not listed as a direct dependency in `pyproject.toml`. | MIT (project-declared) | Inclusion in the final package, exact version, and applicable notice require verification. |
| Pillow | Referenced by the MSIX asset-generation script. | HPND (project-declared) | Determine whether Pillow is distributed with the application or used only as a build-time tool. |
| Python 3.11+ / standard library | Runtime requirement declared in project metadata; the project README refers to Python 3.12+. | PSF license (project-declared) | Confirm the bundled interpreter version and applicable license materials. |
| SQLite / `sqlite3` | Used for the local database. | Public domain (project-declared) | Confirm the SQLite version/build and any applicable notices. |
| Lucide icons | Project materials describe embedded SVG path data. | ISC (project-declared) | Verify the assets included in the distribution and provide the required license notice. |

## License texts and attribution

The project-root file `THIRD_PARTY_LICENSES.md` is the starting point for the full license texts and notices.

The final distributed version of this document and the accompanying license materials must be checked against the exact application package. License names and component references in project materials should not be treated as independent confirmation of package contents or legal compliance.

Where required by the applicable license terms, VectoTask distributions must provide the relevant copyright notices, license texts, disclaimers, and other required materials in a customer-accessible location.

## Distribution-specific information

Third-party components may differ between development builds and distributed packages. Some tools may be used only during development or asset generation and may not be included in the application.

The final notices should therefore reflect the components actually redistributed with the specific VectoTask release, rather than assuming that every development dependency is shipped to customers.

## Contact

For questions about third-party notices, contact:

**VectoTask@gmail.com**

