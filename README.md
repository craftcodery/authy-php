# PHP Client for Twilio Authy Two-Factor Authentication (2FA) API

Documentation for PHP usage of the Authy API lives in the [official Twilio documentation](https://www.twilio.com/docs/authy/api/).

The Authy API supports multiple channels of 2FA:
* One-time passwords via SMS and voice.
* Soft token ([TOTP](https://www.twilio.com/docs/glossary/totp) via the Authy App)
* Push authentication via the Authy App

If you only need SMS and Voice support for one-time passwords, we recommend using the [Twilio Verify API](https://www.twilio.com/docs/verify/api) instead. [More on how to choose between Authy and Verify here.](https://www.twilio.com/docs/verify/authy-vs-verify)

### Authy Quickstart

For a full tutorial, check out the PHP/Laravel Authy Quickstarts in our docs:
* [PHP/Laravel Authy Quickstart](https://www.twilio.com/docs/authy/quickstart/two-factor-authentication-php-laravel)

## Authy PHP Installation

This library requires PHP 7.2/.5+

Install with [composer](https://www.twilio.com/docs/usage/tutorials/how-to-set-up-your-php-development-environment). The [`craftcodery/authy-php`](http://packagist.org/packages/craftcodery/authy-php) package is available on [Packagist](https://packagist.org/packages/craftcodery/authy-php).

```bash
composer require craftcodery/authy-php
```

## Usage

To use the Authy client, import AuthyApiClient and initialize it with your production API Key found in the [Twilio Console](https://www.twilio.com/console/authy/applications/):

```php
$authy_api = new Authy\AuthyApi('#your_api_key');
```

![authy api key in console](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/account-security-api-key.width-800.png)

## 2FA Workflow

1. [Create a user](https://www.twilio.com/docs/authy/api/users#enabling-new-user)
2. [Send a one-time password](https://www.twilio.com/docs/authy/api/one-time-passwords)
3. [Verify a one-time password](https://www.twilio.com/docs/authy/api/one-time-passwords#verify-a-one-time-password)

**OR**

1. [Create a user](https://www.twilio.com/docs/authy/api/users#enabling-new-user)
2. [Send a push authentication](https://www.twilio.com/docs/authy/api/push-authentications)
3. [Check a push authentication status](https://www.twilio.com/docs/authy/api/push-authentications#check-approval-request-status)


## <a name="phone-verification"></a>Phone Verification

[Phone verification now lives in the Twilio API](https://www.twilio.com/docs/verify/api) and has [PHP support through the official Twilio helper libraries](https://www.twilio.com/docs/libraries/php). 

[Legacy (V1) documentation here.](verify-legacy-v1.md) **Verify V1 is not recommended for new development. Please consider using [Verify V2](https://www.twilio.com/docs/verify/api)**.

## Copyright

Copyright (c) 2011-2020 Authy Inc. See [LICENSE](https://github.com/twilio/authy-php/blob/master/LICENSE.md) for further details.
