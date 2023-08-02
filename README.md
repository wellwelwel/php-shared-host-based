# PHP Shared Host Based 🐳

This is an image based on shared hosts of most popular private companies and pre-configured to operate in production environment and works for both **amd64** and **arm64**.

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

- Testing it on browser in `http://localhost:3000`

---

## Customizing

- **Workdir:** `/srv/www/public_html`
  - Modify the **index.php** at `/srv/www/public_html/index.php`
  - You can create a volume in `/srv/www/public_html` or `/srv/www`, also just copy your app content to it 🤹🏻‍♀️
- [**php.ini**](./resources/php.ini): `/usr/local/etc/php/php.ini`
- [**000-default.conf**](./resources/000-default.conf): `/etc/apache2/sites-available/000-default.conf`

---

> It's a image create for [**SVPS Project**](https://github.com/wellwelwel/svps) 🧙🏻
