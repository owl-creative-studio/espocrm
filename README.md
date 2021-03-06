## EspoCRM

<a href='https://www.espocrm.com'>EspoCRM is an Open Source CRM</a> (Customer Relationship Management) software that allows you to see, enter and evaluate all your company relationships regardless of the type. People, companies or opportunities - all in an easy and intuitive interface.

It's a web application with a frontend designed as a single page application based on backbone.js and a REST API backend written in PHP.

Download the latest release from our [website](https://www.espocrm.com).

### Requirements

* PHP 7.2 and later (with pdo, json, gd, openssl, zip, imap, mbstring, curl extensions);
* MySQL 5.7 (and later), or MariaDB 10.1 (and later).

For more information about server configuration see [this article](https://www.espocrm.com/documentation/administration/server-configuration/).

### Documentation

Documentation for administrators, users and developers is available [here](https://www.espocrm.com/documentation/).

### How to report a bug

Create an issue [here](https://github.com/espocrm/espocrm/issues) or post on our [forum](http://forum.espocrm.com/forum/bug-reports).

### How to install a stable version

[Download](https://www.espocrm.com/download/) the latest version. See the [instructions](https://www.espocrm.com/documentation/administration/installation/) about installation.

### Getting started (for developers)

1. Clone repository to your local computer.
2. Change to the project's root directory.
3. Install [composer](https://getcomposer.org/doc/00-intro.md).
4. Run `composer install` if composer is installed globally or `php composer.phar install` if locally.

Note: Some dependencies require php extensions that you might don't have installed (e.g. zmq, ldap) and don't need to use. You can skip these requirements by installing with a flag *--ignore-platform-reqs*: `composer install --ignore-platform-reqs`.

Note: Never update composer dependencies if you are going to contribute code back.

Now you can build. Build will create compiled css files.

To compose a proper *config.php* and populate database you can run install by opening `http(s)://{YOUR_CRM_URL}/install` location in a browser.

Then open `data/config.php` file and add:

```php
'isDeveloperMode' => true,
```

### How to build (for developers)

You need to have nodejs and Grunt CLI installed.

1. Change to the project's root directory.
2. Install project dependencies with `npm install`.
3. Run Grunt with `grunt`.

The build will be created in the `build` directory.

Note: By default grunt installs composer dependencies. You can skip it by running `grunt offline`.

Upgrade packages can be built with `grunt upgrade`.

### How to contribute (for developers)

Before we can merge your pull request you need to accept our CLA [here](https://github.com/espocrm/cla). It's very simple to do.

Branches:

* *hotfix/** – upcoming maintenance release; fixes should be pushed to this branch;
* *master* – develop branch; new features should be pushed to this branch;
* *stable* – last stable release.

### Running tests (for developers)

Before running tests, you need to build for testing:

```
grunt test
```

Unit tests:

```
vendor/bin/phpunit --bootstrap=vendor/autoload.php tests/unit
```

Integration tests:

```
vendor/bin/phpunit --bootstrap=vendor/autoload.php tests/integration
```

### How to make a translation

Build po file with command:
`node po.js en_EN`
(specify needed language instead of en_EN)

After that translate the generated po file.

Build json files from the translated po file:

1. Put your po file espocrm-en_EN.po into `build` directory
2. Run `node lang.js en_EN`

Json files will be created in build directory grouped by folders.

### License

EspoCRM is published under the GNU GPLv3 [license](https://raw.githubusercontent.com/espocrm/espocrm/master/LICENSE.txt).
