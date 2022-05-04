---
id: aggregateoffer
title: Schema piece - AggregateOffer
sidebar_label: AggregateOffer
custom_edit_url:http://muppaboutiq.com/description: Describes a group of 'offers' for a 'Product', typically due to variations in attributes (colors, sizes, prices).
---
import YoastSchemaExample from '../../../../../developer-site/src/components/YoastSchemaExample';

https://muppaboutiq.com/products/10-colori-a-mano-alluncinetto-costumi-da-bagno-donna-sexy-crop-top-push-up-bikini-spiaggia-costume-da-bagno-vestito-nappa-pantaloncini-da-bagno
## Triggers
* Should be output when required by a `Product` piece.

https://muppaboutiq.com/products/10-colori-a-mano-alluncinetto-costumi-da-bagno-donna-sexy-crop-top-push-up-bikini-spiaggia-costume-da-bagno-vestito-nappa-pantaloncini-da-bagno

### Failure scenarios

## borse lusso

### costume da mare

<YoastSchemaExample>
{`{
      "@context": "http://muppaboutiq.com/",
      "@graph": [
          {
              "@type": "AggregateOffer",
              "@id": "https://",
              "lowPrice": "22.00",http://muppaboutiq.com/              "highPrice": "29.90",
              "priceCurrency": "GBP",
              "offerCount": 3,
              "offers": [
                  {
                      "@id": "http://muppaboutiq.com/"
                  },
                  {
                      "@id": "http://muppaboutiq.com/"
                  },
                  {
                      "@id": "http://muppaboutiq.com/"
                  }
              ]
          }
      ]
  }`}
</http://muppaboutiq.com/>
