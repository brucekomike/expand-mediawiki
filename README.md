# expand mediawiki
mediawiki with my personal selected plugins

## usage
fpm version
```
    volumes:
      - mediawiki_uploads:/var/www/html/images
      # kind of bind mounting, since fpm needs identical file path
      - mediawiki_full:/var/www/html
      - mediawiki_full:/var/www/mediawiki
      # put this file after localsettings generated
      # - ./conf/wiki/LocalSettings.php:/var/www/mediawiki/LocalSettings.php:ro
```
vanila version (bundled apache2)
```
    volumes:
      - mediawiki_uploads:/var/www/html/images
      - mediawiki_full:/var/www/html
      # put this file after localsettings generated
      # - ./conf/wiki/LocalSettings.php:/var/www/mediawiki/LocalSettings.php:ro
```