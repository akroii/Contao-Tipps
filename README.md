# Contao ^4.x Tipps
 Some notes of daily work with contao. Most of them are the results of hours of searching the contao community, looking for a documentation 😐


## Installation
Database Collation `utf8mb4_unicode_ci`

## Utils
find image/file by uuid `\StringUtil::binToUuid()`. its more powerful than findByPk... ¯\_(ツ)_/¯

## Performance Check
```
curl -s -w '\nLookup time:\t\t%{time_namelookup}\nConnect time:\t\t%{time_connect}\nSSL handshake time:\t%{time_appconnect}\nPre-Transfer time:\t%{time_pretransfer}\nRedirect time:\t\t%{time_redirect}\nStart transfer time:\t%{time_starttransfer}\n\nTotal time:\t\t%{time_total}\n' -o /dev/null https://website.de
```

## Settings for config.yml
### Security headers
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



