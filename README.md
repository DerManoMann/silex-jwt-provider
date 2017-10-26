# Silex JWT Provider
Silex provider for JWT

[![Build Status](https://travis-ci.org/DerManoMann/silex-jwt-provider.png?branch=master)](https://travis-ci.org/DerManoMann/silex-jwt-provider)

## Usage

```php
<?php
  
use Evaneos\JWT\Silex\Provider\SecurityJWTServiceProvider;
use Silex\Provider\SecurityServiceProvider;
  
$app->register(new SecurityServiceProvider(), [
    'security.firewalls' => [
        'all' => [
            'stateless' => true,
            'pattern' => '^.*$',
            'jwt' => [
                'secret_key' => 'secret',
                'allowed_algorithms' => ['HS256'],
                'retrieval_strategy' => 'chain',
            ],
        ],
    ],
]);
  
$app->register(new SecurityJWTServiceProvider());
```
