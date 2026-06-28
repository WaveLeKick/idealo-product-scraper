[Idealo Product Scraper](https://apify.com/data_alchemist/idealo-product-scraper?fpr=data)

Scrapes structured product data from idealo.de/.fr/.co.uk/.es/.it/.at product pages, including name, images, pricing offers, reviews, test scores, technical specifications, and more.

## What it does

Given one or more idealo.de product page URLs, the Actor extracts:

| Field | Description |
| --- | --- |
| `url` | Source product page URL |
| `sku` / `gtin` | Product identifiers from JSON-LD |
| `name` | Product name |
| `images` | List of product image URLs |
| `description` | Short feature summary (e.g. "380 Watt, Betriebszeit 70 Min., beutellos") |
| `reviewCount` | Number of user reviews |
| `reviewScore` | Average review score (0–5) |
| `testScore` | Average expert test grade (e.g. 1.8) |
| `properties` | Full technical datasheet as a flat key/value object |
| `offer_count` | Number of offers found |
| `offers` | List of offers — each with `price`, `link`, and `logo` |
| `similar_products` | Related category links with names and URLs |

## Offer redirect resolution

Idealo wraps all outbound store links in an internal redirect (`/relocator/relocate?...`). When **Resolve Offer Redirects** is enabled (default: `true`), the Actor follows each redirect and replaces the idealo relay URL with the final destination URL at the actual store (e.g. `https://www.amazon.de/...`).

This is useful when you need real store URLs for price monitoring, affiliate tracking, or deduplication. Disable it to speed up crawling when the raw redirect links are sufficient.

## Input

```
{
  "startUrls": [
    { "url": "https://www.idealo.de/preisvergleich/OffersOfProduct/205019562_-ip3251eut-shark-clean.html" }
  ],
  "resolveOfferRedirects": true,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| `startUrls` | array | — | Product page URLs to scrape (required) |
| `resolveOfferRedirects` | boolean | `true` | Follow redirect links to extract final store URLs |
| `proxyConfiguration` | object | Apify Proxy | Proxy settings — residential proxies with country `DE` recommended |

## Output example

```
{
  "url": "https://www.idealo.de/preisvergleich/OffersOfProduct/205019562_-ip3251eut-shark-clean.html",
  "sku": "0622356283717",
  "gtin": "0622356283717",
  "name": "Shark IP3251EUT",
  "images": [
    "https://cdn.idealo.com/folder/Product/205019/5/205019562/s1_produktbild_gross/shark-ip3251eut.jpg"
  ],
  "description": "lila, 380 Watt, Betriebszeit 70 Min., Ladezeit 360 min, Behältervolumen 0,7 Liter, beutellos, Lithium-Ionen",
  "reviewCount": 1,
  "reviewScore": 5.0,
  "testScore": 1.8,
  "properties": {
    "Produkttypen": "Akku-Staubsauger, Stielstaubsauger",
    "Leistung (W)": "380 Watt",
    "Betriebszeit": "70 Min."
  },
  "offer_count": 25,
  "offers": [
    {
      "price": 384.95,
      "link": "https://www.amazon.de/dp/...",
      "logo": "https://cdn.idealo.com/folder/Shop/4/6/4640/s1_shop_160x60.png"
    }
  ],
  "similar_products": [
    { "name": "Akku-Staubsauger", "url": "https://www.idealo.de/preisvergleich/ProductCategory/2925F346250.html" },
    { "name": "Shark Staubsauger", "url": "https://www.idealo.de/preisvergleich/ProductCategory/2925F9911618.html" }
  ]
}
```

## Notes

- Residential proxies with the same country code as the target idealo site (DE,UK,IT etc) are strongly recommended for reliable results

## Possible websites

idealo.de | idealo.fr | idealo.co.uk | idealo.es | idealo.it | idealo.at | idealo.es and more