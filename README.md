Angel CMS
=====
Angel is a CMS built on top of Laravel.  It is available via [Packagist](https://packagist.org/packages/angel/core).

Installation
------------
We are currently using Laravel 4.1 for this CMS until 4.2 is more stable.

Install Laravel 4.1 using the following command:
```bash
composer create-project laravel/laravel --prefer-dist {project-name} 4.1.*
```

Add the `angel/core` package requirement to your `composer.json` file, like this:
```javascript
"require": {
    "laravel/framework": "4.1.*",
    "angel/core": "dev-master"
},
```

Issue a `composer update` to install the package.

After the package has been installed, open `app/config/app.php` and add the following to your `providers` array:
```php
'Angel\Core\CoreServiceProvider'
```

Delete all the default routes in `app/routes.php` and all the filters except for the `csrf` filter in `app/filters.php`.

Set up your database so that we can run the migrations.

Finally, issue the following artisan commands:
```bash
php artisan asset:publish angel/core         # Publish the assets
php artisan config:publish angel/core        # Publish the config
php artisan migrate --package="angel/core"   # Run the migrations
```

Usage
-----
