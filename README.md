# Moselle, a sdk package for BT open APIs

This package is still under construction (july 6th 2022).

Open Api are described in the Bouygues Telecom Developer Portal: https://developer.bouyguestelecom.fr

## Install

```
composer require bboxlab/moselle
```

## List of API and tools in Open API SDK

- authenticator for app credentials Oauth flow
- check email address
- check iban
- check portability

## How to use?

First, install the package on your php application with composer.

Then, create a Sdk Moselle Object with a credentials and a moselle configuration.

```php
$configuration = new Configuration();
...
$sdk = new Sdk('clientId', 'secretId', $configuration);

```

You can use a preexisting configuration, here for the default bt env configuration.

```php
$sdk = new Sdk('clientId', 'secretId', new ConfigurationCreator()->createApConfig());
```

When sdk is set correctly, you can use it to fetch secured open api

```php
$response = $sdk->checkEmail('example@email.com')
```

A Moselle Response object is returned with the app credentials token created as an object and the response given by Bt Api as an array. 

## How to test Moselle package

You can use phpunit to launch the tests:

```bash
 ./vendor/bin/phpunit tests/
```
