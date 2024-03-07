=== Pronamic Pay with Mollie for Ninja Forms ===
Contributors: pronamic
Tags: mollie, ninja-forms, ninja forms, form, payment, donation
Requires at least: 5.9
Tested up to: 6.4
Requires PHP: 8.0
Stable tag: 1.0.0
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Connect Mollie to Ninja Forms with Pronamic Pay. This free plugin is all that you need to start selling with Ninja Forms.

== Description ==

Accept payments with Mollie and Ninja Forms. This free plugin is all that you need to connect your Ninja Forms forms to Mollie.
The installation is as easy as creating a form. Just add your form fields, choose a payment amount and add a list of the available payment methods from Mollie. You can choose which payment methods you want to embed in your form.

https://youtu.be/Rsycvh7Sgvk

= External services =

This plugin uses a number of external services to initiate payments. These are documented below with a link to the service's Terms of Use.

**Mollie API**

This plugin provides the link between the forms plugin Ninja Forms and payment provider Mollie. To communicate with Mollie, this plugin connects to the Mollie API via https://api.mollie.com/.
The documentation for the Mollie API can be found at https://docs.mollie.com/, Mollie's user agreement can be found at https://www.mollie.com/gb/user-agreement-v9.
From your WordPress website, customer and payment data can be passed on to Mollie for setting up and processing payments.

**VIES VAT number validation**

If a payment via this plugin is initiated with a VAT number, this plugin will attempt to validate this VAT number via the VIES VAT number validation.
The VIES VAT number validation is an online service provided by the European Union that allows businesses to verify the validity of VAT numbers issued by EU Member States.
This is important for businesses that are trading with companies in other EU countries, as it helps to ensure that they are only dealing with legitimate businesses.
Communication with this service is done via the http://ec.europa.eu/taxation_customs/vies/checkVatService.wsdl URL.
The disclaimer for this service can be consulted via  https://ec.europa.eu/taxation_customs/vies/#/disclaimer and the privacy statement via https://ec.europa.eu/taxation_customs/vies/rest-api/privacy-statement.

== Installation ==

1. To install this plugin you can follow the WordPress documentation section "[Installing Plugins](https://wordpress.org/documentation/article/manage-plugins/#installing-plugins-1)".
2. After installation you can follow the manual "[How to connect Pronamic Pay to Ninja Forms](https://www.pronamicpay.com/en/manuals/how-to-connect-pronamic-pay-to-ninja-forms/)".

== Screenshots ==

1. Payment Gateway Configurations
2. Edit Payment Gateway Configuration

== Changelog ==

= 1.0.0 =

- First release.

== Links ==

-	[Pronamic Pay](https://www.pronamicpay.com/)
-	[Pronamic](https://www.pronamic.eu/)
