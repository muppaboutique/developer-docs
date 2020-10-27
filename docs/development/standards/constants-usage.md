---
id: constants-usage
title: Standards - Constants usage
sidebar_label: Constants usage
custom_edit_url: https://github.com/Yoast/developer-docs/edit/master/docs/development/standards/constants-usage.md
---

## Constants usage

In order to keep the usage of constants throughout our code base organised and easily accessible while at the same time ensuring classes don't have unnecessary dependencies on one another all constants should be cleanly separated into their own classes that can then be used wherever required.

Wrapping them in a class has the additional benefit of enabling autoloading for constants which ensures no additional setup is required and they are only loaded when necessary.

All such wrapping classes should be added to the `src/constants` directory.

For example, such a wrapping class could look as follows:
```php
namespace Yoast\WP\SEO\Constants;

class Link_Types {
    /**
     * Internal links are links that direct to the same site and are not images.
     */
    const INTERNAL = 'internal';

    /**
     * External links are links that direct to a different site, even if it is a subdomain, and are not images.
     */
    const EXTERNAL = 'external';

    /**
     * Internal images are images from the same site.
     */
    const INTERNAL_IMAGE = 'image-in';

    /**
     * External images are images from a different site.
     */
    const EXTERNAL_IMAGE = 'image-ex';
}
```

This class would then be used like this:
```php
use Yoast\WP\SEO\Constants\Link_Types;

if ( $link->type === Link_Types::INTERNAL ) {
    // Do something.
}
```

There is one exception to this rule. If a constant is only used within one class, and possibly tests of that class, then it should be included within that class but the docblock should mark it as internal.

For example:
```php
class Example {

    /**
     * A clear and concise explanation of this constant.
     *
     * @internal
     */
    const INTERNAL_CONSTANT = 'This is not used anywhere else';

    /**
     * A clear and concise explantion of this function.
     *
     * @return string The return value.
     */
    public function get_thing() {
        return \get_option( self::INTERNAL_CONSTANT );
    }
}
```
