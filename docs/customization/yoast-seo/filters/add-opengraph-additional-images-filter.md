---
id: add-opengraph-additional-images-filter
title: Yoast SEO - Allows to add additional images to the Open Graph tags
sidebar_label: Add additional images to the OpenGraph tags
custom_edit_url: https://github.com/Yoast/developer-docs/edit/master/docs/customization/yoast-seo/filters/add-opengraph-additional-images-filter.md
---
By default, Yoast SEO plugin allows to have one OpenGraph image in the page `head` element.

The `wpseo_add_opengraph_additional_images` filter allows to add additional images to the OpenGraph tags. Each image added through the filter will have `og:image`, `og:image:width` and `og:image:height` tags.

By default, the filter adds the additional OpenGraph images to posts, but it is possible to add them to others WordPress content types with some conditionals.

## Usage

### Add an additional OpenGraph image to WordPress posts
```php
<?php
/**
 * Add an additional OpenGraph image to WordPress posts
 */
function add_additional_image_to_opengraph_tags( $image_container ) {
    $image_id = $some_id;
    if ( $image_id ) {
        $image_container->add_image_by_id( $image_id );
    }
}
add_filter( 'wpseo_add_opengraph_additional_images', 'add_additional_image_to_opengraph_tags' );
```

### Add an additional OpenGraph image to WordPress archives pages
```php
<?php
/**
 * Add an additional OpenGraph image to WordPress archives pages
 */
function add_additional_image_to_archive_opengraph_tags( $image_container ) {
    if ( is_archive() ) {
        $image_id = $some_id;
        if ( $image_id ) {
            $image_container->add_image_by_id( $image_id );
        }
    }
}
add_filter( 'wpseo_add_opengraph_additional_images', 'add_additional_image_to_archive_opengraph_tags' );
```
