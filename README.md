[Idealo Product Scraper](https://apify.com/ecomscrape/idealo-product-scraper?fpr=data)

# Contact

If you encounter any issues or need to exchange information, please feel free to contact us through the following link:

[My profile](https://apify.com/ecomscrape)

# Guide (English version)

## What does Idealo.de Product Scraper do?

## Introduction

Idealo stands out as a premier price comparison platform and e-commerce engine, originating from Germany in 2000, serving millions of users across Europe. As one of the largest price comparison portals, Idealo.de aggregates product information from thousands of retailers, making it a goldmine of valuable market data. For businesses, researchers, and e-commerce professionals, manually collecting this data is time-consuming and inefficient.

The Idealo.de Product Scraper addresses this challenge by automating the extraction of comprehensive product information, enabling users to gather competitive intelligence, monitor pricing trends, and conduct market research at scale. Whether you're tracking competitor prices, analyzing market positioning, or building price comparison tools, this scraper provides the structured data you need.

## Scraper Overview

The Idealo.de Product Scraper is a powerful data extraction tool designed specifically to harvest product information from Idealo's extensive database. With more than 96 million page visits per month, idealo serves as the price expert in the online retail sector, making it an invaluable source of market intelligence.

This scraper excels at extracting detailed product data including pricing information, seller offers, customer ratings, and product specifications. Built with robust error handling and proxy support, it can handle large-scale data collection operations while maintaining reliability and avoiding detection.

The tool is ideal for e-commerce managers, market researchers, pricing analysts, and businesses looking to gain competitive advantages through data-driven insights. It transforms hours of manual research into automated, scalable data collection processes.

## Input and Output Details

### Input Format

#### 1. Collect product data from product information pages

Example url 1: [https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html](https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html)

Example url 2: [https://www.idealo.de/preisvergleich/ProductCategory/9212.html](https://www.idealo.de/preisvergleich/ProductCategory/9212.html)

Example url 3: [https://www.idealo.de/preisvergleich/OffersOfProduct/202249542_-crystal-3-0-sodastream.html](https://www.idealo.de/preisvergleich/OffersOfProduct/202249542_-crystal-3-0-sodastream.html)

Example Screenshot of product information page:

![](https://images.apifyusercontent.com/fQePFsK-QBPUr3MfAR_XAbxJ9WfNaDn5SeqtaidD-NI/w:1800/cb:1/aHR0cHM6Ly9pLmliYi5jby9mUXBzampoL1NjcmVlbnNob3QtZnJvbS0yMDI1LTAxLTAyLTE4LTA4LTAxLnBuZw.webp)

The scraper accepts JSON configuration with the following structure:

```
{
  "max_retries_per_url": 2, // Maximum waiting time when accessing the links you provided.
  "proxy": { // Add a proxy to ensure that during the data collection process, you are not detected as a bot.
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL" 
    ],
    "apifyProxyCountry": "SG" // You should choose an Country that coincides with the Country you want to collect data from
  },
  "scrape_type": "specific_product_urls", // Get products by Specific product urls
  "urls": [ // Links to product information pages.
    "https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html",
    "https://www.idealo.de/preisvergleich/OffersOfProduct/202249542_-crystal-3-0-sodastream.html",
    "https://www.idealo.de/preisvergleich/ProductCategory/9212.html",
  ]
}
```

**Input Requirements:**

- **URLs**: Direct links to Idealo.de product pages (format: idealo.de/preisvergleich/OffersOfProduct/[ID])
- **Proxy Configuration**: Recommended to use residential proxies from target country
- **Retry Settings**: Configure maximum attempts per URL for reliability
- **Scrape Type**: Currently supports "specific_product_urls" mode

**Output:**

You get the output from the Idealo.de Product Scraper stored in a tab. The following is an example of the Information Fields collected after running the Actor.

```
[ // List of product information
  {
    "id": "203473202",
    "url": "https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html",
    "name": "Ninja AF400",
    "full_title": "Ninja AF400 AF400EUDBCP",
    "variant_title": "AF400EUDBCP",
    "brand": "Ninja",
    "product_overview": "Produktübersicht: 9,5 Liter  Fassungsvermögen Frittiergut 2,8 kg  2.470 Watt  Temperaturbereich bis 180 °C  mit Timer",
    "description": "Bereits ab 269,90 € ✓ Große Shopvielfalt ✓ Testberichte & Meinungen ✓ | Jetzt Ninja  AF400EUDBCP  günstig kaufen bei idealo.de",
    "image_url": [
      "https://cdn.idealo.com/folder/Product/203473/2/203473202/s1_produktbild_gross/ninja-af400eudbcp.jpg"
    ],
    "sku": "0622356264518",
    "gtin": "0622356264518",
    "low_price": 269.9,
    "high_price": 299.0,
    "currency": "EUR",
    "total_offers": 4,
    "top_offers": [
      {
        "shop_name": "warenstube-bender.de",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 269.9
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "ninjakitchen.de",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 269.99
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "eBay",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 279.0
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "otto.de (Marktplatzhändler)",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 299.0
          }
        ],
        "event": "leadout"
      }
    ],
    "total_ratings": null,
    "rating_score": null,
    "detail": [
      {
        "key": "Produkttypen",
        "value": "Heißluftfritteuse, Doppelfritteuse"
      },
      {
        "key": "Serien",
        "value": "Ninja Foodi, Ninja Foodi MAX"
      },
      {
        "key": "Fassungsvermögen",
        "value": "9,5 Liter"
      },
      {
        "key": "Fassungsvermögen Frittiergut",
        "value": "2,8 kg"
      },
      {
        "key": "Zubereitungsarten",
        "value": "Backen, Braten, Kochen, ohne Fett, Dörren, Erwärmen"
      },
      {
        "key": "Bedienelemente",
        "value": "Tasten"
      },
      {
        "key": "Sicherheitseinrichtungen",
        "value": "Kontrollleuchte, Anti-Rutsch-Füße, wärmeisolierter Griff"
      },
      {
        "key": "Ausstattungen",
        "value": "Ein-/Ausschalter, abnehmbarer Frittierkorb, abnehmbares Zubehör"
      },
      {
        "key": "Funktionen",
        "value": "Timer"
      },
      {
        "key": "Anzeigen",
        "value": "LED, mit Display"
      },
      {
        "key": "Form",
        "value": "rechteckig"
      },
      {
        "key": "Farbe",
        "value": "schwarz"
      },
      {
        "key": "Material",
        "value": "Metall"
      },
      {
        "key": "Breite",
        "value": "41,5 cm"
      },
      {
        "key": "Höhe",
        "value": "32,5 cm"
      },
      {
        "key": "Tiefe",
        "value": "27 cm"
      },
      {
        "key": "Gewicht",
        "value": "8,8 kg"
      },
      {
        "key": "Leistung (W)",
        "value": "2.470 Watt"
      },
      {
        "key": "Anzahl der Automatikprogramme",
        "value": "6"
      },
      {
        "key": "Temperaturbereich",
        "value": "bis 180 °C"
      },
      {
        "key": "Betriebsspannung",
        "value": "220 - 240 V"
      },
      {
        "key": "Netzabsicherung",
        "value": "16 A"
      },
      {
        "key": "Frequenz",
        "value": "50 Hz"
      }
    ],
    "pros": [
      "großes Fassungsvermögen",
      "2 synchronisierbare Garschubladen",
      "breiter Temperaturbereich"
    ],
    "cons": [
      "keine App-Konnektivität",
      "keine komplett vorkonfigurierten Garprogramme"
    ],
    "from_url": null,
    "page": null
  }, // ... Many other product details
]
```

**Output Fields Explained:**

- **ID**: Unique product identifier from Idealo's database - essential for tracking and database operations
- **URL**: Source URL of the scraped product page - enables easy reference and verification
- **Name**: Concise product name as displayed on Idealo - useful for quick identification and cataloging
- **Full Title**: Complete product title including brand and specifications - provides comprehensive product description for detailed analysis
- **Product Overview**: Detailed product description and key features - valuable for understanding product positioning and specifications
- **Image URL**: Direct link to product image - enables visual product identification and catalog building
- **Low Price**: Minimum price found across all sellers - critical for price monitoring and competitive analysis
- **High Price**: Maximum price found across all sellers - helps understand price range and market positioning
- **Currency**: Price currency (typically EUR for German market) - ensures accurate financial calculations
- **Total Offers**: Number of sellers offering the product - indicates market competition and availability
- **Top Offers**: Details of best available deals - provides actionable pricing intelligence
- **Total Ratings**: Number of customer reviews - indicates product popularity and data reliability
- **Rating Score**: Average customer rating - reflects product quality and customer satisfaction

#### 2. Collect product data from products by Queries

Example url 1: "[https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html](https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html)",

Example url 2: [https://www.idealo.de/preisvergleich/SubProductCategory/9592.html](https://www.idealo.de/preisvergleich/SubProductCategory/9592.html)

Example url 3: [https://www.idealo.de/preisvergleich/SubProductCategory/1002.html](https://www.idealo.de/preisvergleich/SubProductCategory/1002.html)

Example Screenshot of Author product list page:

![](https://images.apifyusercontent.com/D0UgFMJljOzG8btrQ07ncqtvXT53VRlTRPuToGujkR0/w:1800/cb:1/aHR0cHM6Ly9pLmliYi5jby9obU5TMUtYL1NjcmVlbnNob3QtZnJvbS0yMDI1LTAxLTAyLTE4LTA5LTUyLnBuZw.webp)

**Input:**

```
{
  "max_retries_per_url": 2, // Maximum waiting time when accessing the links you provided.
  "max_items_per_url": 20, // Total items you want scrape
  "proxy": { // Add a proxy to ensure that during the data collection process, you are not detected as a bot.
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL" 
    ],
    "apifyProxyCountry": "SG" // You should choose an Country that coincides with the Country you want to collect data from
  },
  "scrape_type": "product_list_by_query", // Get products by Specific product urls
  "urls": [ // List of product list page from query urls
    "https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html",
    "https://www.idealo.de/preisvergleich/ProductCategory/9212.html",
    "https://www.idealo.de/preisvergleich/SubProductCategory/1002.html"
  ],
}
```

**Output:**

```
[
  {
    "id": "204292302",
    "url": "https://www.idealo.de/preisvergleich/OffersOfProduct//204292302",
    "name": null,
    "full_title": "Ninja AF400",
    "variant_title": null,
    "brand": null,
    "product_overview": "Heißluftfritteuse, 9,5 Liter, Fassungsvermögen Frittiergut 2,8 kg, 2.470 Watt, Temperaturbereich bis 180 °C, mit Timer",
    "description": null,
    "image_url": "https://cdn.idealo.com/folder/Product/204292/3/204292302/s1_produktbild_mittelgross/ninja-af400.jpg",
    "sku": null,
    "gtin": null,
    "low_price": 159.99,
    "high_price": 159.99,
    "currency": "€",
    "total_offers": 80,
    "top_offers": null,
    "total_ratings": 20,
    "rating_score": 2.4,
    "detail": null,
    "pros": null,
    "cons": null,
    "from_url": "https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html", // Which url are the products crawled from
    "page": 1 // Which page are the products crawled from
  }, // ... Many other product details
]
```

## Usage Guide

**Step-by-step Implementation:**

1. **Prepare URLs**: Collect Idealo.de product page URLs you want to scrape
2. **Configure Proxy**: Set up residential proxy matching your target market (Germany for .de)
3. **Set Parameters**: Configure retry attempts and scraping preferences
4. **Execute Scraper**: Run the tool with your JSON configuration
5. **Process Output**: Import structured data into your analysis tools or databases

**Best Practices:**

- Use residential proxies from Germany to avoid geographical restrictions
- Implement delays between requests to prevent rate limiting
- Monitor for CAPTCHA challenges and adjust proxy rotation accordingly
- Validate output data quality and completeness before processing

**Error Handling:**

- Network timeouts: Increase retry count and add delays
- Blocked requests: Rotate proxy servers and user agents
- Missing data: Implement fallback extraction methods
- Rate limiting: Implement exponential backoff strategies

## Benefits and Applications

**Time Efficiency**: Automate data collection that would take hours manually, enabling real-time price monitoring and competitive analysis across thousands of products.

**Business Applications**:

- **Competitive Intelligence**: Track competitor pricing strategies and market positioning
- **Price Optimization**: Analyze market price ranges to optimize your own pricing
- **Market Research**: Understand consumer preferences through ratings and reviews data
- **Inventory Planning**: Use offer counts and availability data for demand forecasting

**Data Quality**: Structured output ensures consistent data format for analysis, reporting, and integration with business intelligence tools.

## Conclusion

The Idealo.de Product Scraper transforms the complex task of price comparison research into an automated, scalable process. By providing comprehensive product data in structured format, it enables businesses to make data-driven decisions and maintain competitive advantages in dynamic markets.

Ready to streamline your price monitoring and market research? Start extracting valuable Idealo.de product data today.

# Anleitung (Deutsche Version)

## Was macht der Idealo.de Product Scraper?

## Einführung

Idealo ist eine führende Preisvergleichsplattform und E-Commerce-Engine, die im Jahr 2000 in Deutschland gegründet wurde und inzwischen Millionen von Nutzern in ganz Europa bedient. Als eines der größten Preisvergleichsportale aggregiert Idealo.de Produktinformationen von Tausenden Händlern und ist somit eine Fundgrube wertvoller Marktdaten. Für Unternehmen, Forscher und E-Commerce-Fachleute ist die manuelle Datensammlung zeitaufwendig und ineffizient.

Der Idealo.de Product Scraper löst dieses Problem, indem er die umfassende Extraktion von Produktinformationen automatisiert. So ermöglicht er es Nutzern, Wettbewerbsanalysen durchzuführen, Preistrends zu überwachen und Marktforschung im großen Stil zu betreiben. Egal ob Sie Konkurrentenpreise verfolgen, Marktpositionierungen analysieren oder eigene Preisvergleichstools entwickeln möchten – dieser Scraper liefert Ihnen die strukturierte Datenbasis, die Sie benötigen.

## Überblick über den Scraper

Der Idealo.de Product Scraper ist ein leistungsstarkes Werkzeug zur Datenerfassung, das speziell dafür entwickelt wurde, Produktinformationen aus der umfangreichen Datenbank von Idealo zu extrahieren. Mit über 96 Millionen Seitenaufrufen pro Monat ist Idealo der Preis-Experte im Onlinehandel und damit eine unschätzbare Quelle für Markteinblicke.

Der Scraper überzeugt durch die Extraktion detaillierter Produktdaten einschließlich Preisinformationen, Händlerangebote, Kundenbewertungen und technischer Produktspezifikationen. Dank fortschrittlicher Fehlerbehandlung und Proxy-Unterstützung eignet sich das Tool für groß angelegte Datensammlungen, bleibt dabei zuverlässig und vermeidet Erkennung durch Gegenseiten.

Das Tool ist ideal für E-Commerce-Manager, Marktforscher, Pricing-Analysten und Unternehmen, die sich durch datenbasierte Erkenntnisse einen Wettbewerbsvorteil verschaffen möchten. Es verwandelt stundenlange manuelle Recherchen in automatisierte und skalierbare Datenprozesse.

## Details zu Input und Output

### Eingabeformat

#### 1. Produktdaten von Produktinformationsseiten sammeln

Beispiel-URL: [https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html](https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html)

Beispiel-Screenshot der Produktinformationsseite:

![](https://images.apifyusercontent.com/fQePFsK-QBPUr3MfAR_XAbxJ9WfNaDn5SeqtaidD-NI/w:1800/cb:1/aHR0cHM6Ly9pLmliYi5jby9mUXBzampoL1NjcmVlbnNob3QtZnJvbS0yMDI1LTAxLTAyLTE4LTA4LTAxLnBuZw.webp)

Der Scraper akzeptiert eine JSON-Konfiguration mit folgender Struktur:

```
{
  "max_retries_per_url": 2, // Maximale Wartezeit beim Zugriff auf die angegebenen Links.
  "proxy": { // Fügen Sie einen Proxy hinzu, um sicherzustellen, dass Sie während der Datensammlung nicht als Bot erkannt werden.
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL" 
    ],
    "apifyProxyCountry": "SG" // Wählen Sie idealerweise ein Land, das dem Zielmarkt der Datensammlung entspricht.
  },
  "scrape_type": "specific_product_urls", // Produkte über spezifische Produkt-URLs abrufen
  "urls": [ // Links zu Produktinformationsseiten
    "https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html"
  ]
}
```

**Eingabeanforderungen:**

- URLs: Direkte Links zu Produktseiten auf Idealo.de (Format: idealo.de/preisvergleich/OffersOfProduct/[ID])
- Proxy-Konfiguration: Es wird empfohlen, Residential-Proxies aus dem Zielland zu verwenden
- Retry-Einstellungen: Konfigurieren Sie die maximale Anzahl von Versuchen pro URL für Zuverlässigkeit
- Scrape-Typ: Aktuell wird der Modus "specific_product_urls" unterstützt

**Ausgabe:**

Das Ergebnis des Idealo.de Product Scraper erhalten Sie als Tabelle. Nachfolgend finden Sie ein Beispiel der Informationsfelder, die nach dem Durchlauf des Actors gesammelt werden.

```
[ // Liste von Produktinformationen
  {
    "id": "203473202",
    "url": "https://www.idealo.de/preisvergleich/OffersOfProduct/203473202_-af400eudbcp-ninja.html",
    "name": "Ninja AF400",
    "full_title": "Ninja AF400 AF400EUDBCP",
    "variant_title": "AF400EUDBCP",
    "brand": "Ninja",
    "product_overview": "Produktübersicht: 9,5 Liter  Fassungsvermögen Frittiergut 2,8 kg  2.470 Watt  Temperaturbereich bis 180 °C  mit Timer",
    "description": "Bereits ab 269,90 € ✓ Große Shopvielfalt ✓ Testberichte & Meinungen ✓ | Jetzt Ninja  AF400EUDBCP  günstig kaufen bei idealo.de",
    "image_url": [
      "https://cdn.idealo.com/folder/Product/203473/2/203473202/s1_produktbild_gross/ninja-af400eudbcp.jpg"
    ],
    "sku": "0622356264518",
    "gtin": "0622356264518",
    "low_price": 269.9,
    "high_price": 299.0,
    "currency": "EUR",
    "total_offers": 4,
    "top_offers": [
      {
        "shop_name": "warenstube-bender.de",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 269.9
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "ninjakitchen.de",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 269.99
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "eBay",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 279.0
          }
        ],
        "event": "leadout"
      },
      {
        "shop_name": "otto.de (Marktplatzhändler)",
        "products": [
          {
            "id": 203473202,
            "category": 3513,
            "name": "Ninja AF400EUDBCP",
            "price": 299.0
          }
        ],
        "event": "leadout"
      }
    ],
    "total_ratings": null,
    "rating_score": null,
    "detail": [
      {
        "key": "Produkttypen",
        "value": "Heißluftfritteuse, Doppelfritteuse"
      },
      {
        "key": "Serien",
        "value": "Ninja Foodi, Ninja Foodi MAX"
      },
      {
        "key": "Fassungsvermögen",
        "value": "9,5 Liter"
      },
      {
        "key": "Fassungsvermögen Frittiergut",
        "value": "2,8 kg"
      },
      {
        "key": "Zubereitungsarten",
        "value": "Backen, Braten, Kochen, ohne Fett, Dörren, Erwärmen"
      },
      {
        "key": "Bedienelemente",
        "value": "Tasten"
      },
      {
        "key": "Sicherheitseinrichtungen",
        "value": "Kontrollleuchte, Anti-Rutsch-Füße, wärmeisolierter Griff"
      },
      {
        "key": "Ausstattungen",
        "value": "Ein-/Ausschalter, abnehmbarer Frittierkorb, abnehmbares Zubehör"
      },
      {
        "key": "Funktionen",
        "value": "Timer"
      },
      {
        "key": "Anzeigen",
        "value": "LED, mit Display"
      },
      {
        "key": "Form",
        "value": "rechteckig"
      },
      {
        "key": "Farbe",
        "value": "schwarz"
      },
      {
        "key": "Material",
        "value": "Metall"
      },
      {
        "key": "Breite",
        "value": "41,5 cm"
      },
      {
        "key": "Höhe",
        "value": "32,5 cm"
      },
      {
        "key": "Tiefe",
        "value": "27 cm"
      },
      {
        "key": "Gewicht",
        "value": "8,8 kg"
      },
      {
        "key": "Leistung (W)",
        "value": "2.470 Watt"
      },
      {
        "key": "Anzahl der Automatikprogramme",
        "value": "6"
      },
      {
        "key": "Temperaturbereich",
        "value": "bis 180 °C"
      },
      {
        "key": "Betriebsspannung",
        "value": "220 - 240 V"
      },
      {
        "key": "Netzabsicherung",
        "value": "16 A"
      },
      {
        "key": "Frequenz",
        "value": "50 Hz"
      }
    ],
    "pros": [
      "großes Fassungsvermögen",
      "2 synchronisierbare Garschubladen",
      "breiter Temperaturbereich"
    ],
    "cons": [
      "keine App-Konnektivität",
      "keine komplett vorkonfigurierten Garprogramme"
    ],
    "from_url": null,
    "page": null
  }, // ... Viele weitere Produktdetails
]
```

**Erläuterung der Ausgabefelder:**

- **ID**: Eindeutige Produktkennung aus der Idealo-Datenbank – unerlässlich für Tracking und Datenbank-Operationen
- **URL**: Quell-URL der gescrapten Produktseite – ermöglicht einfache Referenzierung und Überprüfung
- **Name**: Kurzbezeichnung des Produkts, wie sie auf Idealo angezeigt wird – nützlich zur schnellen Identifikation und Katalogisierung
- **Vollständiger Titel**: Vollständiger Produkttitel mit Marke und Spezifikationen – bietet eine umfassende Produktbeschreibung für detaillierte Analysen
- **Produktübersicht**: Ausführliche Produktbeschreibung und Hauptmerkmale – wertvoll für das Verständnis der Produktpositionierung und -eigenschaften
- **Bild-URL**: Direktlink zum Produktbild – ermöglicht die visuelle Identifikation und den Aufbau von Produktkatalogen
- **Niedrigster Preis**: Niedrigster gefundener Preis bei allen Anbietern – entscheidend für Preisbeobachtung und Wettbewerbsanalyse
- **Höchster Preis**: Höchster gefundener Preis bei allen Anbietern – hilft, die Preisspanne und Marktpositionierung zu verstehen
- **Währung**: Preiswährung (in der Regel EUR für den deutschen Markt) – sorgt für genaue finanzielle Berechnungen
- **Anzahl der Angebote**: Anzahl der Händler, die das Produkt anbieten – zeigt Marktwettbewerb und Verfügbarkeit an
- **Top-Angebote**: Details zu den besten verfügbaren Deals – liefert umsetzbare Preis-Intelligenz
- **Anzahl Bewertungen**: Anzahl der Kundenrezensionen – zeigt die Beliebtheit des Produkts und die Zuverlässigkeit der Daten an
- **Bewertungs-Score**: Durchschnittliche Kundenbewertung – spiegelt Produktqualität und Kundenzufriedenheit wider

#### 2. Sammeln von Produktdaten durch Suchanfragen

Beispiel-URL: "[https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html](https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html)"

Beispiel-Screenshot einer Autor-Produktlistenseite:

![](https://images.apifyusercontent.com/D0UgFMJljOzG8btrQ07ncqtvXT53VRlTRPuToGujkR0/w:1800/cb:1/aHR0cHM6Ly9pLmliYi5jby9obU5TMUtYL1NjcmVlbnNob3QtZnJvbS0yMDI1LTAxLTAyLTE4LTA5LTUyLnBuZw.webp)

**Input:**

```
{
  "max_retries_per_url": 2, // Maximale Wartezeit beim Zugriff auf die von Ihnen bereitgestellten Links.
  "max_items_per_url": 20, // Gesamtanzahl der Elemente, die Sie scrapen möchten
  "proxy": { // Fügen Sie einen Proxy hinzu, um sicherzustellen, dass Sie während des Datensammlungsprozesses nicht als Bot erkannt werden.
    "useApifyProxy": true,
    "apifyProxyGroups": [
      "RESIDENTIAL" 
    ],
    "apifyProxyCountry": "SG" // Sie sollten ein Land wählen, das mit dem Land übereinstimmt, aus dem Sie Daten sammeln möchten.
  },
  "scrape_type": "product_list_by_query", // Produkte anhand von spezifischen Produkt-URLs abrufen
  "urls": [ // Liste der Produktlistenseiten aus Query-URLs
    "https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html"
  ]
}
```

**Output:**

Sie erhalten die Ausgabe des Idealo.de Product Scraper in einem Tab gespeichert. Im Folgenden sehen Sie ein Beispiel der Informationsfelder, die nach dem Ausführen des Actors gesammelt wurden.

```
[
  {
    "id": "204292302",
    "url": "https://www.idealo.de/preisvergleich/OffersOfProduct//204292302",
    "name": null,
    "full_title": "Ninja AF400",
    "variant_title": null,
    "brand": null,
    "product_overview": "Heißluftfritteuse, 9,5 Liter, Fassungsvermögen Frittiergut 2,8 kg, 2.470 Watt, Temperaturbereich bis 180 °C, mit Timer",
    "description": null,
    "image_url": "https://cdn.idealo.com/folder/Product/204292/3/204292302/s1_produktbild_mittelgross/ninja-af400.jpg",
    "sku": null,
    "gtin": null,
    "low_price": 159.99,
    "high_price": 159.99,
    "currency": "€",
    "total_offers": 80,
    "top_offers": null,
    "total_ratings": 20,
    "rating_score": 2.4,
    "detail": null,
    "pros": null,
    "cons": null,
    "from_url": "https://www.idealo.de/preisvergleich/ProductCategory/3513I16-705.html", // Von welcher URL die Produkte gecrawlt werden
    "page": 1 // Von welcher Seite die Produkte gecrawlt werden
  }, // ... Viele weitere Produktdetails
]
```

## Anleitung zur Nutzung

**Schritt-für-Schritt-Anleitung:**

1. **URLs vorbereiten**: Sammeln Sie die Idealo.de-Produktseiten-URLs, die Sie scrapen möchten
2. **Proxy konfigurieren**: Richten Sie einen Residential Proxy ein, der Ihrem Zielmarkt entspricht (Deutschland für .de)
3. **Parameter festlegen**: Konfigurieren Sie die Wiederholungsversuche und Scraping-Präferenzen
4. **Scraper ausführen**: Führen Sie das Tool mit Ihrer JSON-Konfiguration aus
5. **Output verarbeiten**: Importieren Sie die strukturierten Daten in Ihre Analysetools oder Datenbanken

**Best Practices:**

- Nutzen Sie deutsche Residential-Proxies, um geografische Beschränkungen zu vermeiden
- Fügen Sie Verzögerungen zwischen Anfragen ein, um Rate Limiting vorzubeugen
- Überwachen Sie auf CAPTCHA-Herausforderungen und passen Sie ggf. die Proxy-Rotation an
- Validieren Sie die Datenqualität und Vollständigkeit vor der Weiterverarbeitung

**Fehlerbehandlung:**

- Netzwerk-Timeouts: Erhöhen Sie den Wiederholungszähler und integrieren Sie Verzögerungen
- Blockierte Anfragen: Rotieren Sie Proxy-Server und User Agents
- Fehlende Daten: Implementieren Sie alternative Extraktionsmethoden
- Rate Limiting: Nutzen Sie exponentielle Backoff-Strategien

## Vorteile und Anwendungsbereiche

**Zeiteffizienz**: Automatisieren Sie die Datensammlung, die manuell Stunden dauern würde, und ermöglichen Sie so eine Echtzeit-Preisüberwachung und Wettbewerbsanalyse über Tausende von Produkten.

**Geschäftliche Anwendungen:**

- **Wettbewerbs-Intelligenz**: Verfolgen Sie Preisstrategien und Marktpositionierung der Konkurrenz
- **Preisoptimierung**: Analysieren Sie Preisspannen am Markt, um Ihre Preise zu optimieren
- **Marktforschung**: Verstehen Sie Kundenpräferenzen durch Bewertungs- und Rezensionsdaten
- **Bestandsplanung**: Nutzen Sie Angebotszahlen und Verfügbarkeitsdaten zur Nachfrageprognose

**Datenqualität**: Strukturierter Output gewährleistet ein konsistentes Datenformat für Analyse, Reporting und Integration in Business-Intelligence-Tools.

## Fazit

Der Idealo.de Product Scraper verwandelt die komplexe Aufgabe der Preisvergleichsrecherche in einen automatisierten, skalierbaren Prozess. Durch die Bereitstellung umfassender Produktdaten im strukturierten Format können Unternehmen datenbasierte Entscheidungen treffen und Wettbewerbsvorteile in dynamischen Märkten sichern.

Bereit, Ihr Preis-Monitoring und Ihre Marktforschung zu optimieren? Starten Sie noch heute mit dem Extrahieren wertvoller Idealo.de-Produktdaten.

# Your feedback

We are always working to improve Actors' performance. So, if you have any technical feedback about Idealo.de Product Scraper or simply found a bug, please create an issue on the Actor's Issues tab in Apify Console.