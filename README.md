# PHP XAMPP Projects

**A local-development collection of PHP/MySQL applications for student information, inventory workflows, authentication practice and tabular data display.**

This repository appears to be a snapshot of an XAMPP `htdocs` workspace rather than one cohesive application. It contains four custom project areas alongside copied XAMPP/dashboard files and large third-party frontend bundles.

Recommended repository name: **`php-xampp-projects`**, replacing the overly broad `xampp`.

## Included applications

| Directory | Source-backed scope | Database dump |
| --- | --- | --- |
| `sis/` | Student information system built around an AdminLTE-style dashboard, academic records and user administration | `sis/database/sis_db.sql` |
| `inventory-management-system/` | Inventory, customer/vendor, purchase, sale, image and report workflows with Bootstrap/DataTables assets | `inventory-management-system/inc/config/shop_inventory.sql` |
| `Register/` | Small registration/login/session exercise using MySQLi | No SQL dump supplied in the snapshot |
| `showdata/` | Small database login/data-table display exercise | No SQL dump supplied in the snapshot |

The repository also includes `dashboard/`, `xampp/`, `applications.html`, `bitnami.css` and `index.php` from an XAMPP installation/dashboard. Those files are environment material, not authored application features.

## Local-use boundary

These projects are suitable only for a controlled local lab. The supplied source contains development database settings, documented default accounts and legacy password hashing. Do not expose this checkout to the public internet or use real student, customer, vendor or sales data.

The bundled dashboard identifies the environment as **XAMPP for Windows 8.2.12**, but the applications and SQL dumps include older code/dependency assumptions. Presence in one workspace does not establish compatibility with every bundled version.

## Proposed setup

Use an isolated XAMPP installation and a disposable database environment. Preserve an original copy before changing configuration or importing SQL.

1. Place the project directories under your XAMPP `htdocs` directory.
2. Start Apache and MySQL/MariaDB through the XAMPP Control Panel.
3. Open the local phpMyAdmin interface.
4. Create/import only the database required by the application you are testing.
5. Review that application's connection file and local URL before opening it.

Typical local paths from the supplied documentation are:

```text
http://localhost/sis
http://localhost/inventory-management-system
```

The inventory project expects database `shop_inventory`. The student system's supplied notes expect `sis_db`. `Register/connection.php` references `login_form`, while `showdata/database.php` references `db_adt44`; no matching SQL dumps for those two were found in the snapshot.

Do not assume the supplied ports are correct for your machine. `Register/connection.php` places `8080` in the database hostname, while `showdata/database.php` uses MySQL port `3307`. Review these against the actual MySQL/MariaDB listener before use.

## Project-specific notes

### Student information system

The `sis` project includes a large dashboard/plugin tree and a SQL dump. Its supplied readme documents a default administrator account. Authentication code uses MD5-based password handling. Roles, sessions and administrative screens are historical source, not evidence of secure access control.

The application sets its timezone to `Asia/Manila`. Review this before using date/time records in Cambodia or another locale.

### Inventory management system

The inventory project uses a fixed localhost root URL and root database user with an empty password in `inc/config/constants.php`. Its two documentation files list different default-login credentials. Treat both as insecure development defaults and inspect the imported user table rather than assuming either set is current.

The bundled SQL dump and frontend libraries reflect an older application stack. DataTables, Bootstrap, Popper, JSZip, pdfmake and other vendored assets are included directly in the repository; their presence is not a current dependency/security audit.

### Register and showdata

These are small practice modules rather than integrated parts of the SIS/inventory systems. They use separate connection assumptions and databases. No repository-level migration or unified account model connects the four applications.

## Security and data warnings

- Several authentication paths use MD5, which is unsuitable for password storage.
- Connection details and default accounts are committed in source/documentation.
- `Register/functions.php` builds a query with a session value interpolated into SQL.
- The projects include file-upload and administrative functionality that require a dedicated security review before any non-local use.
- Error output and legacy code may reveal database or filesystem details.
- Third-party libraries are vendored and old enough that version presence should not be treated as safe or supported.

See [SECURITY.md](SECURITY.md) for the bounded review.

## Repository organisation

The snapshot contains 2,572 text entries, most under `sis/`, followed by the inventory system and copied XAMPP dashboard files. Consider removing XAMPP's own dashboard/runtime files from version control in a separate reviewed cleanup, keeping only your application folders and necessary documentation. This documentation overlay does not delete anything.

See [application notes](docs/application-notes.md) for paths and configuration boundaries.

## Verification

This refresh inspected the attached Repomix snapshot, root/nested documentation, representative connection/authentication files and both SQL-dump paths. No PHP syntax check, XAMPP service, database import, login, upload, browser workflow or third-party asset build was executed.

The ZIP changes documentation only. Read [CONTRIBUTING.md](CONTRIBUTING.md) and [refresh notes](docs/repository-refresh.md).

## Licence and provenance

No root project licence is included in the supplied snapshot. The nested inventory/SIS notes attribute downloaded source to an external source-code site. This refresh does not claim authorship or redistribution rights for copied applications, XAMPP dashboard files or vendored libraries.
