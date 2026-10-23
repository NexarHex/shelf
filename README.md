## About ShelfBot

ShelfBot is the crawler behind SHELF, a tool that tells which e-commerce platform a website runs
(for example Shopify, WooCommerce or Wix) and shows a few public details from its homepage.

**What it reads, per website, once:** DNS records and `robots.txt` (and, if the homepage redirects to
another host of the same site, that host's `robots.txt`), then — only where `robots.txt` allows it — the
homepage, at most one sitemap file, at most one shop page linked from the homepage (only to look for
platform markers),
and at most one small platform check (WooCommerce's public Store API index `/wp-json/wc/store/v1`,
or Magento's `/magento_version`). That is **at most 6 requests in total**, at most 1 request per
second, usually fewer. It never logs in, never opens cart, checkout or account pages, stores no
product data or prices, and stores no personal data.

**It follows your rules:** ShelfBot obeys `robots.txt` (including `Crawl-delay` up to 30 seconds) and
stops immediately when a site answers "too many requests" (HTTP 429) or shows a bot challenge.
It never tries to get around a block.

**It identifies itself:** every request carries the User-Agent `ShelfBot/0.2 (+https://github.com/NexarHex/shelf)`.
Requests can also be signed with Web Bot Auth; the public key directory is at
`https://shelfbot.nexarhex.workers.dev/.well-known/http-message-signatures-directory`.

**Opting out:** add this to your `robots.txt`:

```
User-agent: ShelfBot
Disallow: /
```

**Contact:** <CONTACT-EMAIL-OR-ISSUES-LINK>
