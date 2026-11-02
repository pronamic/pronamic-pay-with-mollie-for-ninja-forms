=== Pronamic Pay with Mollie for Ninja Forms ===
Contributors: pronamic
Tags: pronamic, mollie, ninja-forms, form, payment
Requires at least: 5.9
Tested up to: 7.1
Requires PHP: 8.3
Stable tag: 1.11.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Connect Mollie to Ninja Forms with Pronamic Pay. This free plugin is all that you need to start selling with Ninja Forms.

== Description ==

[Pronamic Pay](https://www.pronamicpay.com/) · [Pronamic](https://www.pronamic.eu/) · [GitHub](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms)

Accept payments with Mollie and Ninja Forms. This free plugin is all that you need to connect your Ninja Forms forms to Mollie. The installation is as easy as creating a form. Just add your form fields, choose a payment amount and add a list of the available payment methods from Mollie. You can choose which payment methods you want to embed in your form.

https://youtu.be/Rsycvh7Sgvk

### Features

This plugin is developed from the idea that online payments should be easy. Some of the features:

- Easy install
- Support for most major payment methods
- Payment status pages
- Automatic payment status updates via Mollie webhooks and the WordPress REST API
- High quality support
- Built by Pronamic

### External services

This plugin uses a number of external services to initiate payments. These are documented below with a link to the service's Terms of Use.

#### Mollie API

This plugin provides the link between the forms plugin Ninja Forms and payment provider Mollie. To communicate with Mollie, this plugin connects to the Mollie API via [https://api.mollie.com/](https://api.mollie.com/). The documentation for the Mollie API can be found at [https://docs.mollie.com/](https://docs.mollie.com/), Mollie's user agreement can be found at [https://www.mollie.com/legal/user-agreement](https://www.mollie.com/legal/user-agreement). From your WordPress website, customer and payment data can be passed on to Mollie for setting up and processing payments.

### Pronamic Pay Premium

With a Pronamic Pay Premium license, you get access to exceptional support and a range of exclusive benefits that take your payment experience to the next level.

#### Premium support

- **Fast and expert help** from our team of specialists.
- **Priority treatment** for your support tickets.

#### Premium add-ons

- **Pronamic Pay Fundraising Add-On**
  Easily create online fundraising and crowdfunding campaigns.
- **Pronamic Pay Notification Add-On**
  Set up extensive notifications for payers and administrators.
- **Pronamic Pay WP All Export Add-On**
  Export all your payment data with a few clicks.

And much more!

Discover all the benefits of Pronamic Pay Premium at [https://www.pronamicpay.com/](https://www.pronamicpay.com/).

**Upgrade to Pronamic Pay Premium now and take advantage of all the benefits!**

== Installation ==

1. To install this plugin you can follow the WordPress documentation section "[Installing Plugins](https://wordpress.org/documentation/article/manage-plugins/#installing-plugins-1)".
2. After installation you can follow the manual "[How to connect Pronamic Pay to Ninja Forms](https://www.pronamicpay.com/en/manuals/how-to-connect-pronamic-pay-to-ninja-forms/)".

== Screenshots ==

1. Payment Gateway Configurations
2. Edit Payment Gateway Configuration

== Changelog ==

<!-- Start changelog -->

### [1.11.1] - 2026-11-02

#### Changed

- Updated the build and development configuration to the SolveBeam plugin boilerplate. No functional changes.

#### Composer

- Changed `giggsey/libphonenumber-for-php-lite` from `9.0.40` to `9.0.42`.
	Updated phone number metadata for many regions (including CN, US, AU, IN and others) and fixed carrier code handling for Brazilian numbers.
	Release notes: https://github.com/giggsey/libphonenumber-for-php-lite/releases/tag/9.0.41, https://github.com/giggsey/libphonenumber-for-php-lite/releases/tag/9.0.42
- Changed `symfony/polyfill-mbstring` from `v1.38.2` to `v1.43.3`.
	Fixes for ill-formed UTF-8 handling, stricter argument validation in `mb_ord()`/`mb_chr()`/`mb_str_split()`, and better alignment with native `ext/mbstring` behavior.
	Release notes: https://github.com/symfony/polyfill-mbstring/releases/tag/v1.43.0, https://github.com/symfony/polyfill-mbstring/releases/tag/v1.43.3

Full set of changes: [`1.11.0...1.11.1`][1.11.1]

[1.11.1]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.11.0...v1.11.1

### [1.11.0] - 2026-09-28

#### Changed

- Raised the minimum required PHP version from 8.2 to 8.3.
- Tested up to WordPress 7.1.
- Mollie payment due dates are now set through a bank transfer payment request, as Mollie only supports due dates for bank transfer payments.
- Subscription renewal pre-notifications are now sent 14 days in advance instead of 1 week.

#### Fixed

- Fixed a currency mismatch exception when calculating payment totals in a currency other than EUR.
- Fixed errors when loading payments or subscriptions whose post no longer exists.

#### Composer

- Changed `php` from `>=8.2` to `>=8.3`.
- Changed `automattic/jetpack-autoloader` from `v5.0.21` to `v5.0.23`.
	Version 5.0.22 started honoring the root package's `exclude-from-classmap` setting for the Jetpack class map; 5.0.23 reverted this, so there is no net change in behavior.
	Release notes: https://github.com/Automattic/jetpack-autoloader/blob/v5.0.23/CHANGELOG.md
- Changed `pronamic/wp-mollie` from `v1.10.1` to `v2.0.0`.
	Breaking: the `due_date` property moved from `PaymentRequest` to `BankTransferPaymentRequest`, matching Mollie's supported payment type.
	Release notes: https://github.com/pronamic/wp-mollie/releases/tag/v2.0.0
- Changed `pronamic/wp-money` from `2.4.5` to `2.5.0`.
	Added an optional currency argument to `Parser::parse()`, allowing amounts to be parsed in currencies other than EUR.
	Release notes: https://github.com/pronamic/wp-money/releases/tag/v2.5.0
- Changed `woocommerce/action-scheduler` from `4.0.0` to `4.2.0`.
	Fixes a lock that could get permanently stuck, enforces unique action inserts atomically, reduces SQL queries on the admin page and guards against object-injection when reading stored schedule data.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/4.1.0, https://github.com/woocommerce/action-scheduler/releases/tag/4.2.0
- Changed `wp-pay-gateways/mollie` from `v4.20.0` to `v4.21.0`.
	Uses a bank transfer payment request when setting the Mollie payment due date, for compatibility with `pronamic/wp-mollie` 2.0.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.21.0
- Changed `wp-pay/core` from `v4.34.0` to `v4.35.0`.
	Changed the default subscription renewal pre-notification period to 14 days, hides the next payment date for cancelled subscriptions and fixes currency mismatch and missing post errors.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.35.0

Full set of changes: [`1.10.0...1.11.0`][1.11.0]

[1.11.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.10.0...v1.11.0

### [1.10.0] - 2026-08-03

#### Added

- Added integration with the Pronamic Pay default payment methods package, so default payment methods are registered independently from the core library.

#### Composer

- Added `pronamic/pronamic-pay-default-payment-methods` version `v1.0.1`.
	Renamed the iDEAL QR payment method to "iDEAL | Wero QR".
	Release notes: https://github.com/pronamic/pronamic-pay-default-payment-methods/releases/tag/v1.0.1
- Changed `wp-pay/core` from `v4.32.0` to `v4.33.0`.
	Payment method registration now runs through the new `pronamic_pay_register_payment_methods` action and the default methods moved to a separate package.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.33.0

Full set of changes: [`1.9.0...1.10.0`][1.10.0]

[1.10.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.9.0...v1.10.0

### [1.9.0] - 2026-04-02

#### Composer

- Changed `automattic/jetpack-autoloader` from `v5.0.15` to `v5.0.16`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.16
- Changed `pronamic/wp-datetime` from `v2.1.8` to `v2.2.0`.
	Release notes: https://github.com/pronamic/wp-datetime/releases/tag/v2.2.0
- Changed `wp-pay/core` from `v4.30.0` to `v4.32.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.32.0

Full set of changes: [`1.8.0...1.9.0`][1.9.0]

[1.9.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.8.0...v1.9.0

### [1.8.0] - 2026-01-27

#### Composer

- Changed `wp-pay-gateways/mollie` from `v4.18.0` to `v4.19.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.19.0
- Changed `wp-pay/core` from `v4.29.0` to `v4.30.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.30.0

Full set of changes: [`1.7.0...1.8.0`][1.8.0]

[1.8.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.7.0...v1.8.0

### [1.7.0] - 2026-01-05

#### Composer

- Changed `automattic/jetpack-autoloader` from `v5.0.13` to `v5.0.15`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.15
- Changed `wp-pay-gateways/mollie` from `v4.17.0` to `v4.18.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.18.0
- Changed `wp-pay/core` from `v4.28.0` to `v4.29.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.29.0

Full set of changes: [`1.6.4...1.7.0`][1.7.0]

[1.7.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.6.4...v1.7.0

### [1.6.4] - 2025-11-17

#### Composer

- Changed `automattic/jetpack-autoloader` from `v5.0.12` to `v5.0.13`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.13
- Changed `wp-pay-gateways/mollie` from `v4.16.3` to `v4.17.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.17.0
- Changed `wp-pay/core` from `v4.27.1` to `v4.28.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.28.0

Full set of changes: [`1.6.3...1.6.4`][1.6.4]

[1.6.4]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.6.3...v1.6.4

### [1.6.3] - 2025-11-11

#### Composer

- Changed `automattic/jetpack-autoloader` from `v5.0.10` to `v5.0.12`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.12
- Changed `wp-pay-extensions/ninjaforms` from `v3.3.3` to `v3.3.4`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-ninjaforms/releases/tag/v3.3.4
- Changed `wp-pay-gateways/mollie` from `v4.16.2` to `v4.16.3`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.16.3

Full set of changes: [`1.6.2...1.6.3`][1.6.3]

[1.6.3]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.6.2...v1.6.3

### [1.6.2] - 2025-09-17

#### Changed

- Changed `automattic/jetpack-autoloader` from `v5.0.9` to `v5.0.10`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.10
- Changed `wp-pay-gateways/mollie` from `v4.16.1` to `v4.16.2`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.16.2
- Changed `wp-pay/core` from `v4.27.0` to `v4.27.1`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.27.1

Full set of changes: [`1.6.1...1.6.2`][1.6.2]

[1.6.2]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.6.1...v1.6.2

### [1.6.1] - 2025-08-26

#### Commits

- Fixed Mollie user agreement link ([7cfc908](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/7cfc908d1e7489ebb17c41dc6193eb6cccebec80))
- Removed "VIES VAT number validation", no longer used ([eee08bb](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/eee08bb3cf410c533ad8250911ff1994ba42f88a))

#### Composer

- Changed `wp-pay-gateways/mollie` from `v4.16.0` to `v4.16.1`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.16.1

Full set of changes: [`1.6.0...1.6.1`][1.6.1]

[1.6.1]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.6.0...v1.6.1

### [1.6.0] - 2025-08-22

#### Composer

- Changed `php` from `>=8.1` to `>=8.2`.
- Changed `automattic/jetpack-autoloader` from `v5.0.7` to `v5.0.9`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.9
- Changed `woocommerce/action-scheduler` from `3.9.2` to `3.9.3`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.9.3
- Changed `wp-pay-gateways/mollie` from `v4.15.0` to `v4.16.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.16.0
- Changed `wp-pay/core` from `v4.26.0` to `v4.27.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.27.0

Full set of changes: [`1.5.0...1.6.0`][1.6.0]

[1.6.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.5.0...v1.6.0

### [1.5.0] - 2025-06-19

#### Composer

- Changed `automattic/jetpack-autoloader` from `v3.1.3` to `v5.0.7`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v5.0.7
- Changed `composer/installers` from `v2.3.0` to `v2.3.0`.
	Release notes: https://github.com/composer/installers/releases/tag/v2.3.0
- Changed `woocommerce/action-scheduler` from `3.9.2` to `3.9.2`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.9.2
- Changed `wp-pay-gateways/mollie` from `v4.14.1` to `v4.15.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.15.0
- Changed `wp-pay/core` from `v4.25.0` to `v4.26.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.26.0

Full set of changes: [`1.4.1...1.5.0`][1.5.0]

[1.5.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.4.1...v1.5.0

### [1.4.1] - 2025-02-25

#### Changed

- Improved Mollie error handling when updating subscription mandate. ([8f03de5](https://github.com/pronamic/wp-pronamic-pay-mollie/commit/8f03de511ccf3ebb0223919dd7fcf6185e4e9c3c))

#### Composer

- Changed `wp-pay-gateways/mollie` from `v4.14.0` to `v4.14.1`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.14.1

Full set of changes: [`1.4.0...1.4.1`][1.4.1]

[1.4.1]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.4.0...v1.4.1

### [1.4.0] - 2025-02-17

#### Changed

- Fixed early registration of payment methods for loading translations. ([75aed83](https://github.com/pronamic/wp-pay-core/commit/75aed831f46f32d1c5e01eced8b521fe8e331faf))
- Removed Mollie iDEAL issuers support for iDEAL 2.0 migration. ([eebbad1](https://github.com/pronamic/wp-pronamic-pay-mollie/commit/eebbad1ba21ec7d55862d40925efc1e1ea7035ef))

#### Composer

- Changed `automattic/jetpack-autoloader` from `v3.0.8` to `v3.1.3`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v3.1.3
- Changed `composer/installers` from `v2.2.0` to `v2.3.0`.
	Release notes: https://github.com/composer/installers/releases/tag/v2.3.0
- Changed `woocommerce/action-scheduler` from `3.8.0` to `3.9.2`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.9.2
- Changed `wp-pay-extensions/ninjaforms` from `v3.3.2` to `v3.3.3`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-ninjaforms/releases/tag/v3.3.3
- Changed `wp-pay-gateways/mollie` from `v4.12.0` to `v4.14.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.14.0
- Changed `wp-pay/core` from `v4.20.0` to `v4.25.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.25.0

Full set of changes: [`1.3.1...1.4.0`][1.4.0]

[1.4.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.3.1...v1.4.0

### [1.3.1] - 2024-06-19

#### Commits

- Requires PHP: 8.1. ([f4c64d2](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/f4c64d2d7e09aae9a2ca9b79826de04446902276))

#### Composer

- Changed `wp-pay/core` from `v4.19.0` to `v4.20.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.20.0

Full set of changes: [`1.3.0...1.3.1`][1.3.1]

[1.3.1]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.3.0...v1.3.1

### [1.3.0] - 2024-06-12

#### Composer

- Changed `automattic/jetpack-autoloader` from `v3.0.7` to `v3.0.8`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v3.0.8
- Changed `wp-pay-gateways/mollie` from `v4.11.0` to `v4.12.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.12.0
- Changed `wp-pay/core` from `v4.18.0` to `v4.19.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.19.0

Full set of changes: [`1.2.0...1.3.0`][1.3.0]

[1.3.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.2.0...v1.3.0

### [1.2.0] - 2024-05-27

#### Composer

- Changed `php` from `>=8.0` to `>=8.1`.
- Changed `woocommerce/action-scheduler` from `3.7.4` to `3.8.0`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.8.0
- Changed `wp-pay-gateways/mollie` from `v4.10.3` to `v4.11.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.11.0
- Changed `wp-pay/core` from `v4.17.0` to `v4.18.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.18.0

Full set of changes: [`1.1.1...1.2.0`][1.2.0]

[1.2.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.1.1...v1.2.0

### [1.1.1] - 2024-05-15

#### Composer

- Changed `automattic/jetpack-autoloader` from `v3.0.4` to `v3.0.7`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v3.0.7
- Changed `woocommerce/action-scheduler` from `3.7.3` to `3.7.4`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.7.4
- Changed `wp-pay-gateways/mollie` from `v4.10.0` to `v4.10.3`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.10.3
- Changed `wp-pay/core` from `v4.16.0` to `v4.17.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.17.0

Full set of changes: [`1.1.0...1.1.1`][1.1.1]

[1.1.1]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.1.0...v1.1.1

### [1.1.0] - 2024-03-26

#### Commits

- Tested up to: 6.5. ([ac818c3](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/ac818c31d1891e02fa954abfca133e7d9d8fc079))
- Removed Mollie signup link. ([5333171](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/5333171ace565fd99243d4fde8f9c15cdf23e96b))
- Reduce tags to 5. ([527ddb1](https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/commit/527ddb1643e2cb2859ae7262ec6f2b6c9e3d9778))

#### Composer

- Changed `automattic/jetpack-autoloader` from `v2.12.0` to `v3.0.4`.
	Release notes: https://github.com/Automattic/jetpack-autoloader/releases/tag/v3.0.4
- Changed `woocommerce/action-scheduler` from `3.7.2` to `3.7.3`.
	Release notes: https://github.com/woocommerce/action-scheduler/releases/tag/3.7.3
- Changed `wp-pay-extensions/ninjaforms` from `v3.3.1` to `v3.3.2`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-ninjaforms/releases/tag/v3.3.2
- Changed `wp-pay-gateways/mollie` from `v4.9.2` to `v4.10.0`.
	Release notes: https://github.com/pronamic/wp-pronamic-pay-mollie/releases/tag/v4.10.0
- Changed `wp-pay/core` from `v4.15.1` to `v4.16.0`.
	Release notes: https://github.com/pronamic/wp-pay-core/releases/tag/v4.16.0

Full set of changes: [`1.0.0...1.1.0`][1.1.0]

[1.1.0]: https://github.com/pronamic/pronamic-pay-with-mollie-for-ninja-forms/compare/v1.0.0...v1.1.0

### [1.0.0] - 2023-01-30

- First release.

[1.0.0]: https://github.com/pronamic/wp-pronamic-pay-with-mollie-for-ninja-forms/releases/tag/v1.0.0

<!-- End changelog -->

== Links ==

-	[Pronamic Pay](https://www.pronamicpay.com/)
-	[Pronamic](https://www.pronamic.eu/)
