# wordpress (Monorepo)
Smart, small, secure WordPress stack. Dieses Monorepo enthält zwei Submodule:

- `wordpress-nginx`: NGINX-Frontend für WordPress
- `wordpress-php-fpm`: PHP-FPM-Backend mit WordPress

## Verwendung

1. Submodule initialisieren/aktualisieren: `git submodule update --init --recursive`
2. Stack bauen und starten (Podman Compose):
   - Build: `podman-compose build` (baut nur nginx und php-fpm; MariaDB wird nur gepullt)
   - Start: `podman-compose up` (ohne DB) oder mit DB-Profil: `podman-compose --profile db up`
   - Stop: `podman-compose down`
3. Frontend erreichbar auf Port 8080.

Das Top-Level `docker-compose.yml` verbindet die beiden Module und eine MariaDB. Die Service-Images werden beim Build mit Tags `mwaeckerlin/wordpress` und `mwaeckerlin/wordpress-proxy` versehen.
