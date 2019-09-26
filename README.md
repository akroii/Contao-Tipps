# Contao ^4.x Tipps
 Some notes of daily work with contao


## Installation
Database Collation `utf8mb4_unicode_ci`

## Utils
find image by uuid `\StringUtil::binToUuid()`

## Settings for config.yml
```
# Contao configuration
contao:
    url_suffix: ''
    image:
        imagine_options:
            jpeg_quality: 100
# Security configuration
nelmio_security:
    xss_protection:
        enabled: true
        mode_block: true
    forced_ssl:
        enabled: true
        hsts_max_age: 2592000
        hsts_subdomains: true
        redirect_status_code: 301
```



