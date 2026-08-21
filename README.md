# expand mediawiki
mediawiki with my personal selected plugins

## local image builds
```
docker build -t expand-mediawiki:local -f Dockerfile .
docker build --build-arg SOURCE_IMAGE=expand-mediawiki:local -t expand-mediawiki-slim:local -f Dockerfile.slim .
docker build --build-arg SOURCE_IMAGE=expand-mediawiki:local -t expand-mediawiki-fpm:local -f Dockerfile.fpm .
docker build --build-arg SOURCE_IMAGE=expand-mediawiki-fpm:local -t expand-mediawiki-fpm-slim:local -f Dockerfile.fpm-slim .
```

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