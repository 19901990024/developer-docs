---
id: woocommerce-seo
title: Schema output for WooCommerce SEO
custom_edit_url: https://github.com/Yoast/developer-docs/edit/master/docs/features/schema/plugins/woocommerce-seo.md
---
The schema output for our [WooCommerce SEO plugin](https://yoast.com/wordpress/plugins/yoast-woocommerce-seo/) builds upon the [Yoast SEO schema output](yoast-seo.md), to add additional detail about products and ecommerce functionality.

## Core functionality
### On all pages
* Remove WooCommerce's breadcrumb schema.

### On product pages
* Change the `@type` of the `WebPage` piece into `ItemPage`.
* Alter the `Product` piece.
	* Apply our validation logic to each existing WooCommerce *piece* /value.
    * Add a `mainEntityOfPage` property to the `Product`, referencing the `WebPage` by ID.
	* Set the `brand` and `manufacturer` properties, based on taxonomy settings.
	* Set the `seller` to the `Organization` (or `Person` ) which is set as the `Publisher` of the `WebSite`.
    * Stitch `offers`, `review` and/or `aggregateRating` values into the graph (when available / as appropriate).

### On checkout pages
* Change the `@type` of the `WebPage` piece to `CheckoutPage`.
