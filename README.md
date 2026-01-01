# wordpress (Monorepo)
Smart, small, secure WordPress stack. Dieses Monorepo enthält zwei Submodule:

- `wordpress-nginx`: NGINX-Frontend für WordPress
- `wordpress-php-fpm`: PHP-FPM-Backend mit WordPress

## Verwendung

1. Submodule initialisieren/aktualisieren: `git submodule update --init --recursive`
2. Stack bauen und starten (Docker Compose):
   - Build: `docker-compose --profile build build` (baut nur nginx und php-fpm; MariaDB wird nur gepullt)
   - Start: `docker-compose --profile up up` (inkl. DB)
   - Stop: `docker-compose --profile up down`
3. Frontend erreichbar auf Port 8123 (siehe Submodul-Portmapping).

Das Top-Level `docker-compose.yml` verbindet die beiden Module und eine MariaDB. Die Service-Images werden beim Build mit Tags `mwaeckerlin/wordpress` und `mwaeckerlin/wordpress-proxy` versehen.
