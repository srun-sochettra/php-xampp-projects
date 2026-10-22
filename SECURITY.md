# Security and local-use guidance

This repository contains legacy local PHP applications and copied XAMPP/vendor assets. It is not an audited or production-ready system. No supported-version programme or response deadline is established here.

## Immediate risks

- Authentication code in the SIS and inventory applications uses MD5-based password handling.
- Development database credentials and default login details are committed.
- `Register/functions.php` interpolates a session-derived user ID into SQL.
- The projects include administrative records, uploads and business/academic data without a verified modern authorisation model.
- Connection and runtime errors may expose implementation details.
- Large third-party libraries are vendored at historical versions; no dependency audit was performed.

Do not expose the applications publicly, reuse default credentials or load real personal/business records. If any committed credentials are reused elsewhere, rotate them. Removing current text alone does not remove Git history.

## XAMPP boundary

The bundled XAMPP dashboard explicitly targets development use. XAMPP configuration/runtime files should not be treated as application source or deployed with these PHP projects. Bind services to local interfaces and review Apache, PHP and MariaDB configuration separately.

## Reporting

Use synthetic data in reports. Redact credentials, student/customer records, SQL dumps and uploaded files. Use a verified private maintainer channel if available, or request one without publishing sensitive details. No dedicated security address or private-reporting feature was confirmed by the snapshot.

These are static source observations, not executed exploits or implemented fixes.
