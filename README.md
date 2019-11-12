# Contao ^4.x Tipps
 Some notes of daily work with contao. 


## Installation
Database Collation `utf8mb4_unicode_ci`

## Utils
find image/file by uuid `\StringUtil::binToUuid()`. its more powerful than findByPk... ` ¯\_(ツ)_/¯ `

## Performance Check
```
curl -s -w '\nLookup time:\t\t%{time_namelookup}\nConnect time:\t\t%{time_connect}\nSSL handshake time:\t%{time_appconnect}\nPre-Transfer time:\t%{time_pretransfer}\nRedirect time:\t\t%{time_redirect}\nStart transfer time:\t%{time_starttransfer}\n\nTotal time:\t\t%{time_total}\n' -o /dev/null https://website.de
```

## Settings for config.yml
### Security headers

See Contao4 Boilerplate
[See my Boilerplate](https://github.com/akroii/Contao4-Boilerplate/blob/master/app/config/config.yml#L1-L19)




