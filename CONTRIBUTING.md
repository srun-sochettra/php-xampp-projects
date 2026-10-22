# Contributing

Treat each PHP directory as a separate historical application. Keep changes scoped to one application unless a repository-level cleanup explicitly documents moved files and changed local URLs.

## Local verification

Use an isolated XAMPP environment and synthetic data. Record the PHP, Apache and MariaDB/MySQL versions, database imported, connection settings and exact browser routes tested.

For authentication changes, replace legacy password handling deliberately and plan migration of existing hashes. Test invalid sessions, duplicate accounts, authorisation checks and safe error responses. For database work, use parameterised queries and verify destructive SQL against a disposable database first.

For upload/report changes, test file type/size/path boundaries, unauthorised access, missing records and output encoding. Do not infer security from Bootstrap/AdminLTE UI controls.

## Pull requests

Explain the affected application, problem, smallest change, schema/configuration impact, checks run and rollback. Keep private database dumps, credentials, uploaded files and generated runtime data out of commits. Follow [SECURITY.md](SECURITY.md) for sensitive reports.
