BitDbBcryptAuthAdapter
======================

Zend Framework 2 database authentication adapter for Bcrypt hashed passwords.
 
Installation
------------

### By cloning

Clone into `./vendor/`.

### Post intallation

1. Enable the module in your `application.config.php` file.

```php
<?php
return array(
	'modules' => array(
		// ...
		'BitDbBcryptAuthAdapter',
	),
	// ...
);
```

Usage
-----

Usage is very similar to Zend Framework 2 provided [Database Table Authentication](http://framework.zend.com/manual/2.3/en/modules/zend.authentication.adapter.dbtable.html)

When storing password in the database, use something like:

```php
use Zend\Crypt\Password\Bcrypt;

$bcrypt = new Bcrypt();
$securePass = $bcrypt->create('user password');
```

Then, to authenticate against it, use this module like:

```php
use BitDbBcryptAuthAdapter\AuthAdapter;
use Zend\Authentication\AuthenticationService;

...

$auth = new AuthenticationService();

$authAdapter = new AuthAdapter($this->serviceLocator->get('Zend\Db\Adapter\Adapter'));

$authAdapter->setTableName('user');
$authAdapter->setIdentityColumn('email');
$authAdapter->setCredentialColumn('password');
$authAdapter->setIdentity('user@bitspan.rs');
$authAdapter->setCredential('plaintext password');

$result = $authAdapter->authenticate();
```
