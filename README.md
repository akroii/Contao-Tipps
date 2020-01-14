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
### check your host
taken from toflar https://github.com/contao/contao/issues/809#issuecomment-571509691
```
<?php

require_once __DIR__.'/../vendor/autoload.php';
$start = microtime(true);

$finder = \Symfony\Component\Finder\Finder::create()
    ->in(__DIR__.'/../vendor/contao')
    ->files()
    ->name('*.php')
    ->contains('<?php')
;

$endFinder = microtime(true);
$timeNeededToInstantiateFinder = $endFinder - $start;

// Trigger iterator before measuring the time
$count = count($finder);
$timeNeededToFindFiles = microtime(true) - $endFinder;

$output =  sprintf('I found %d PHP files in your "vendor/contao" directory.', $count) . "\n";
$output .= sprintf('To do so, I used the Symfony Finder component which was instantiated within %02.2f seconds.', $timeNeededToInstantiateFinder) . "\n";
$output .= sprintf('Searching the files itself took me %02.2f seconds.', $timeNeededToFindFiles) . "\n";
echo $output;
```
## Contao Manager: Upgrade Contao to new Version LTS ##
https://getcomposer.org/doc/articles/versions.md#writing-version-constraints


## Settings for config.yml
### Security headers

See Contao4 Boilerplate
[See my Boilerplate](https://github.com/akroii/Contao4-Boilerplate/blob/master/app/config/config.yml#L1-L19)




