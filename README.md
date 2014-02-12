laravel-sass
============

**THIS REPO IS IN DEVELOPMENT. DON'T USE IT YET.**

Automatic SASS-to-CSS compiling for Laravel 4 while being in development. Every time you run your app
(hitting index.php) laravel-sass will automatically compile all .scss files in your scss folder to .css files in
your css folder. Boom!

## Installation & Usage

Add this to your composer.json, please note that this is a **require-dev**, not a normal **require**. This devides
real dependencies from ones you only need for local development.

```json
"require-dev": {
    "panique/laravel-sass": "dev-master"
}
```

Add this line into your `public/index.php` in Laravel, right **before** `$app->run();`.

```php
SassCompiler::run("scss/", "css/");
```

The first parameter is the relative path to your scss folder (create one) and the second parameter is the relative
path to your css folder. Make sure PHP can write into the css folder by giving the folder
`sudo chmod -R 777 public/css` (when being in /var/www).
**Note:** 777 is just for development, in a production server there's no need to give that folder any write-rights.

Install or update your Composer dependencies to add laravel-sass by doing `composer install` or `composer update`.
Composer automatically installs everything in require-dev by default.

**IMPORTANT:** When you later deploy your application and don't want to install the require-dev stuff, then do
`composer install --no-dev` (or `composer update --no-dev`).
