# ShelfBot (SHELF: Shop Host, E-commerce & Ledger Finder)

This bot identifies which e-commerce platform a website runs on (for example Shopify, WooCommerce or Magento).

## What it does
- Reads only public pages: robots.txt, the homepage, sitemap.xml, and at most one platform information page.
- Sends at most 6 requests per website, no more than 1 per second.
- Follows robots.txt.
- Does not log in, fill in forms, add items to a cart or open the checkout.
- Does not collect personal data.
- Does not try to get around blocks or bot protection.

## User-Agent
`ShelfBot/0.2 (+https://github.com/NexarHex/shelf)`

## How to block it
Add this to your robots.txt:

```
User-agent: ShelfBot
Disallow: /
```

## Contact
Open an issue in this repository: https://github.com/NexarHex/shelf/issues# shelf