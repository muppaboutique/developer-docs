---
id: functional-specification
title: Alt Attributes - Functional specification
sidebar_label: Alt attributes
custom_edit_url: https://github.com/Yoast/developer-docs/edit/master/docs/features/alt-attributes/functional-specification.md
description: This documentation provides technical information about Yoast SEO manages alt attributes.
---
This documentation provides technical information about [Yoast SEO](https://yoast.com/wordpress/plugins/seo/) manages alt attributes.

HTML `<img>` tags support an `alt` attribute, which is intended to provide context/content to assistive devices and non-visual consumers (e.g., search engines).

## We (generally) don't automatically populate alt attributes
It's our policy to not automatically set alt attributes in most cases, as we can't be confident that the value will be accurate/useful, or whether it'll help or harm SEO/accessibility. It's also best practice to not set an alt attribute value when an image is purely 'decorative' - and we lack the context to make this distinction reliably.

However, there are some exceptions to this rule.

### For product images
In the case of images on _product pages_ which lack an alt attribute value, we automatically use _the name of the product_ as a default.

When there are _multiple_ _grouped_ product images (e.g., a gallery of featured images), we automatically append ` (alternate view)` to the name of the product, to differentiate between the 'main' and 'secondary' images.
