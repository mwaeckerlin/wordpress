# Changelog

- 2026-09-26 **1.0.0**
    - wordpress-php-fpm 1.0.1 ships no secret: keys and salts are generated at random on the first start, and the database password has no default; the development stack sets it for its own database
    - Both images are published for amd64 and arm64, built, tested and published on every change and every week
    - The documentation of the environment variables corrects the default PHP-FPM host and describes the generated keys and salts
