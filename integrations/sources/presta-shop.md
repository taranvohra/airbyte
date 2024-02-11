# PrestaShop

## Overview

The PrestaShop source supports both Full Refresh and Incremental syncs. You can choose if this connector will copy only the new or updated data, or all rows in the tables and columns you set up for replication, every time a sync is run.

### Output schema

This Source is capable of syncing the following core Streams:

* [Addresses](https://devdocs.prestashop.com/1.7/webservice/resources/addresses/)
* [Carriers](https://devdocs.prestashop.com/1.7/webservice/resources/carriers/)
* [Cart Rules](https://devdocs.prestashop.com/1.7/webservice/resources/cart\_rules/)
* [Carts](https://devdocs.prestashop.com/1.7/webservice/resources/carts/)
* [Categories](https://devdocs.prestashop.com/1.7/webservice/resources/categories/)
* [Combinations](https://devdocs.prestashop.com/1.7/webservice/resources/combinations/)
* [Configurations](https://devdocs.prestashop.com/1.7/webservice/resources/configurations/)
* [Contacts](https://devdocs.prestashop.com/1.7/webservice/resources/contacts/)
* [Content Management System](https://devdocs.prestashop.com/1.7/webservice/resources/content\_management\_system/)
* [Countries](https://devdocs.prestashop.com/1.7/webservice/resources/countries/)
* [Currencies](https://devdocs.prestashop.com/1.7/webservice/resources/currencies/)
* [Customer Messages](https://devdocs.prestashop.com/1.7/webservice/resources/customer\_messages/)
* [Customer Threads](https://devdocs.prestashop.com/1.7/webservice/resources/customer\_threads/)
* [Customers](https://devdocs.prestashop.com/1.7/webservice/resources/customers/)
* [Deliveries](https://devdocs.prestashop.com/1.7/webservice/resources/deliveries/)
* [Employees](https://devdocs.prestashop.com/1.7/webservice/resources/employees/)
* [Groups](https://devdocs.prestashop.com/1.7/webservice/resources/groups/)
* [Guests](https://devdocs.prestashop.com/1.7/webservice/resources/guests/)
* [Image Types](https://devdocs.prestashop.com/1.7/webservice/resources/image\_types/)
* [Languages](https://devdocs.prestashop.com/1.7/webservice/resources/languages/)
* [Manufacturers](https://devdocs.prestashop.com/1.7/webservice/resources/manufacturers/)
* [Messages](https://devdocs.prestashop.com/1.7/webservice/resources/messages/)
* [Order Carriers](https://devdocs.prestashop.com/1.7/webservice/resources/order\_carriers/)
* [Order Details](https://devdocs.prestashop.com/1.7/webservice/resources/order\_details/)
* [Order Histories](https://devdocs.prestashop.com/1.7/webservice/resources/order\_histories/)
* [Order Invoices](https://devdocs.prestashop.com/1.7/webservice/resources/order\_invoices/)
* [Order Payments](https://devdocs.prestashop.com/1.7/webservice/resources/order\_payments/)
* [Order Slip](https://devdocs.prestashop.com/1.7/webservice/resources/order\_slip/)
* [Order States](https://devdocs.prestashop.com/1.7/webservice/resources/order\_states/)
* [Orders](https://devdocs.prestashop.com/1.7/webservice/resources/orders/)
* [Price Ranges](https://devdocs.prestashop.com/1.7/webservice/resources/price\_ranges/)
* [Product Customization Fields](https://devdocs.prestashop.com/1.7/webservice/resources/product\_customization\_fields/)
* [Product Feature Values](https://devdocs.prestashop.com/1.7/webservice/resources/product\_feature\_values/)
* [Product Features](https://devdocs.prestashop.com/1.7/webservice/resources/product\_features/)
* [Product Option Values](https://devdocs.prestashop.com/1.7/webservice/resources/product\_option\_values/)
* [Product Suppliers](https://devdocs.prestashop.com/1.7/webservice/resources/product\_suppliers/)
* [Products](https://devdocs.prestashop.com/1.7/webservice/resources/products/)
* [ShopGroups](https://devdocs.prestashop.com/1.7/webservice/resources/shop\_groups/)
* [ShopUrls](https://devdocs.prestashop.com/1.7/webservice/resources/shop\_urls/)
* [Shops](https://devdocs.prestashop.com/1.7/webservice/resources/shops/)
* [Specific Price Rules](https://devdocs.prestashop.com/1.7/webservice/resources/specific\_price\_rules/)
* [Specific Prices](https://devdocs.prestashop.com/1.7/webservice/resources/specific\_prices/)
* [States](https://devdocs.prestashop.com/1.7/webservice/resources/states/)
* [Stock Availables](https://devdocs.prestashop.com/1.7/webservice/resources/stock\_availables/)
* [Stock Movement Reasons](https://devdocs.prestashop.com/1.7/webservice/resources/stock\_movement\_reasons/)
* [Stock Movements](https://devdocs.prestashop.com/1.7/webservice/resources/stock\_movements/)
* [Stores](https://devdocs.prestashop.com/1.7/webservice/resources/stores/)
* [Suppliers](https://devdocs.prestashop.com/1.7/webservice/resources/suppliers/)
* [Tags](https://devdocs.prestashop.com/1.7/webservice/resources/tags/)
* [Tax Rule Groups](https://devdocs.prestashop.com/1.7/webservice/resources/tax\_rule\_groups/)
* [Tax Rules](https://devdocs.prestashop.com/1.7/webservice/resources/tax\_rules/)
* [Taxes](https://devdocs.prestashop.com/1.7/webservice/resources/taxes/)
* [Translated Configurations](https://devdocs.prestashop.com/1.7/webservice/resources/translated\_configurations/)
* [Weight Ranges](https://devdocs.prestashop.com/1.7/webservice/resources/weight\_ranges/)
* [Zones](https://devdocs.prestashop.com/1.7/webservice/resources/zones/)

If there are more endpoints you'd like Airbyte to support, please [create an issue.](https://github.com/airbytehq/airbyte/issues/new/choose)

### Features

| Feature                       | Supported?  |                                                                                                                                                                                                                                                                                               |
| ----------------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Full Refresh Sync             | Yes         |                                                                                                                                                                                                                                                                                               |
| Incremental Sync              | Yes         | Addresses, Cart Rules, Carts, Categories, Customer Messages, Customer Threads, Customers, Manufacturers, Messages, Order Carriers, Order Histories, Order Invoices, Order Payments, Order Slip, Orders, Products, Stock Movement Reasons, Stock Movements, Stores, Suppliers, Tax Rule Groups |
| Replicate Incremental Deletes | Coming soon |                                                                                                                                                                                                                                                                                               |
| SSL connection                | Yes         |                                                                                                                                                                                                                                                                                               |
| Namespaces                    | No          |                                                                                                                                                                                                                                                                                               |

## Getting started

PrestaShop enables merchants to give third-party tools access to their shop’s database through a CRUD API, otherwise called a [web service](https://devdocs.prestashop.com/1.7/webservice/).

By default, the webservice feature is disabled on PrestaShop and needs to be [switched on](https://devdocs.prestashop.com/1.7/webservice/tutorials/creating-access/#enable-the-webservice) before the first use.

### Requirements

* PrestaShop [access key](https://devdocs.prestashop.com/1.7/webservice/tutorials/creating-access/#create-an-access-key)
* PrestaShop url

## CHANGELOG

| Version | Date       | Pull Request                                            | Subject                |
| ------- | ---------- | ------------------------------------------------------- | ---------------------- |
| 0.1.0   | 2021-07-02 | [#4465](https://github.com/airbytehq/airbyte/pull/4465) | Initial implementation |
