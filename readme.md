# Laravel Administrator (New Version)

Administrator is an administrative interface builder for [Laravel](http://laravel.com). With Administrator you can visually manage your Eloquent models and their relations, and also create stand-alone settings pages for storing site data and performing site tasks.

- **Author:** Jan Hartigan
- **Website:** [http://frozennode.com](http://administrator.frozennode.com/)
- **Version:** 5.0.11

New Version

- **Author:** Antonio Dal Sie
- **Website:** [http://antoniodalsie.com](http://antoniodalsie.com/)
- **Version:** 5.4

[![Build Status](https://travis-ci.org/exodusanto/Laravel-Admin.svg?branch=master)](https://travis-ci.org/exodusanto/Laravel-Admin)

<img src="https://raw.github.com/FrozenNode/Laravel-Administrator/master/examples/images/overview.jpg" />

## Composer

To install Administrator as a Composer package to be used with Laravel 5.6, simply run:

```sh
composer require "exodusanto/administrator: 5.6.*"
```

To install Administrator as a Composer package to be used with Laravel 5.5, simply run:

```sh
composer require "exodusanto/administrator: 5.5.*"
```

To install Administrator as a Composer package to be used with Laravel 5.4, simply run:

```sh
composer require "exodusanto/administrator: 5.4.*"
```

To install Administrator as a Composer package to be used with Laravel 5, simply run:

```sh
composer require "exodusanto/administrator: 5.*"
```

Once it's installed, you can register the service provider in `config/app.php` in the `providers` array:

```php
'providers' => [
    'Frozennode\Administrator\AdministratorServiceProvider',
]
```

Then publish Administrator's assets with `php artisan vendor:publish`. This will add the file `config/administrator.php`. This [config file](http://administrator.frozennode.com/docs/configuration) is the primary way you interact with Administrator. This command will also publish all of the assets, views, and translation files.

### Laravel 4

If you want to use Administrator with Laravel 4, you need to resolve to Administrator 4:

```json
"exodusanto/administrator": "4.*"
```

Then publish the config file with `php artisan config:publish frozennode/administrator`. This will add the file `app/config/packages/frozennode/administrator/administrator.php`.

Then finally you need to publish the package's assets with the `php artisan asset:publish frozennode/administrator` command.

### Laravel 3

Since Administrator has switched over to Composer, you can no longer use `php artisan bundle:install administrator` or `php artisan bundle:upgrade administrator`. If you want to use Administrator with Laravel 3, you must switch to the [3.3.2 branch](https://github.com/FrozenNode/Laravel-Administrator/tree/3.3.2), download it, and add it in the `/bundles/administrator` directory and add this to your bundles.php file:

```php
'administrator' => array(
    'handles' => 'admin', //this determines what URI this bundle will use
    'auto' => true,
),
```

## Documentation

The complete docs for Administrator can be found at http://administrator.frozennode.com. You can also find the docs in the `/src/docs` directory.


## Copyright and License
Administrator was written by Jan Hartigan of Frozen Node for the Laravel framework.
Administrator is released under the MIT License. See the LICENSE file for details.


## Recent Changelog

### 5.6.3
- Added: Cloud upload options

### 5.6.0
- Support: Laravel 5.6

### 5.5.3
- Added: Image field upload to Storage (ex. S3)

### 5.5.1
- Bugfix: Fix relation BelongsToMany methods 

### 5.5.0
- Added: L5.5 support
- Added: Laravel Package Auto-Discovery

### 5.4.0
- Added: New layout
- Added: Laravel 5.4 compatibility
- Added: Title config String or Closure
- Added: Favicon (png only) config String or Closure
- Added: ENUM config Array or Closure
- Added: New ckeditor layout
- Added: Images config:
    - **Test** resize: prevent stretch of image
    - **Incremental** naming: name*_n* if already exist
- Bugfix: wysiwyg loading on settings

### 5.0.11
- Bugfix: Had to make the middleware additon backwards compatable
- Docs: Added doc updates

### 5.0.10
- Bugfix: L5.2 changed the way url() works so added url('/') instead
- Added: Support for middleware additions to the Admin routes via the administrator config
- Testfix: Fixed failing tests

### 5.0.9
- Bugfix: Fix for datetimepicker partially being covered by top menu  

### 5.0.8
- Bugfix: Rename Bool class to Boolean to fix PHP 7 
- Bugfix: added missing custom attribute field

### 5.0.7
- Bugfix: Fixed boolean true bug 
- Bugfix: Fixes a bug where soft deletes are not being properly detected in L5

### 5.0.6
- Added: Support for custom domains in the admin routes
- Added: Ability to access the model from withinthe column output renderer
- Added: Dynamic Form Request Validation

### 5.0.5
- Added: Added password field to the settings view
- Added: Romanian Language
- Added: Basic HasMany Implementation along with re-ordering support
- Bugfix: Autocomplete working with default value
- Bugfix: Adding missing session to Admin Controller
- Bugfix: Fixed improper handling of filter value 0 for Enum/Text field
- Docfix: Simplified the composer command in the install docs to match the packagist.org instuctions
- Docfix: Changed the type definition for global_rows_per_page to int instead of Null|nt since Null causes divide by 0 error
