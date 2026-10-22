# Application notes

## Database and route map

### SIS

- Local route documented as `/sis`.
- SQL dump: `sis/database/sis_db.sql`.
- Configuration is initialised through `sis/config.php` and `sis/classes/DBConnection.php`.
- Supplied notes include a default administrator credential.
- Timezone is configured as `Asia/Manila`.

### Inventory management system

- Local route documented as `/inventory-management-system`.
- Database: `shop_inventory`.
- SQL dump: `inventory-management-system/inc/config/shop_inventory.sql`.
- Root URL and database values are defined in `inventory-management-system/inc/config/constants.php`.
- `README.md` and `readme.txt` document different default credentials.

### Register

- Connection file: `Register/connection.php`.
- Database name in source: `login_form`.
- Database host includes port `8080`, which must be checked against the actual database service.
- No matching SQL dump was found in the supplied snapshot.

### showdata

- Connection file: `showdata/database.php`.
- Database name in source: `db_adt44`.
- Database endpoint uses `127.0.0.1:3307`.
- No matching SQL dump was found in the supplied snapshot.

## Repository boundary

`dashboard/`, `xampp/`, `applications.html`, `bitnami.css` and the root `index.php` appear to be XAMPP dashboard/environment files. Application source should ideally be kept separately from the local server distribution. No files are removed by this documentation refresh.

The repository contains extensive vendored frontend assets under SIS and inventory. Their version strings help identify historical dependencies but do not establish active support or safety.
