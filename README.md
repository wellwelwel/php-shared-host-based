# PHP Shared Host Based 🐳

A Docker image based on shared hosts of most popular private companies, pre-configured to operate in production environment and works for both **amd64** and **arm64**.

It already has **Composer** installed.

---

## Pull

```sh
docker pull wellwelwel/php:8-shared-based
```

---

## Run

```sh
docker run -p 8080:80 wellwelwel/php:8-shared-based
```

- Testing it on browser: `http://localhost:8080`

---

## Compose

```yml
version: '3.9'
services:
  app:
    image: wellwelwel/php:8-shared-based
    ports:
      - '8080:80'
    volumes:
      - ./src:/srv/www/public_html
```

---

## Customizing

### Files and Resources

- **Workdir:** `/srv/www/public_html`
  - Modify the **index.php** at `/srv/www/public_html/index.php`
  - You can create a volume in `/srv/www/public_html` or `/srv/www`, also just copy your app contents into it 🤹🏻‍♀️
- [**php.ini**](./resources/php.ini): `/usr/local/etc/php/php.ini`
- [**000-default.conf**](./resources/000-default.conf): `/etc/apache2/sites-available/000-default.conf`

### OPcache

> OP Cache increases PHP code execution performance by storing a shared in-memory cache of pre-compiled code from application scripts.

Turn off `opcache` in _.htaccess_ file to see your changes in real time:

```apache
php_flag opcache.enable Off
```

### Debug

Turn on `display_errors` in _.htaccess_ file to debug errors:

```apache
php_flag display_errors On
```

---

> It's an image created for [**SVPS Project**](https://github.com/wellwelwel/svps) 🧙🏻
