# Amazon Offers API

Get every seller offer for an Amazon ASIN: price, shipping, condition, Buy Box winner and seller ratings as JSON.

Powered by [Serpent API](https://apiserpent.com). Full reference: **[Amazon Offers API docs](https://apiserpent.com/amazon-offers-api)**.

## Quick start

1. Get an API key at [apiserpent.com](https://apiserpent.com). Every account starts with 10 free API calls.
2. Call the endpoint with your key in the `X-API-Key` header:

```bash
curl -G "https://apiserpent.com/api/amazon/offers" \
  --data-urlencode "asin=B0BZXMJMXZ" \
  -H "X-API-Key: $SERPENT_API_KEY"
```

## Endpoint

`GET https://apiserpent.com/api/amazon/offers`

| Parameter | Required | Description |
| --- | --- | --- |
| `asin` | Yes | 10-character ASIN, or an ISBN-10 for books |
| `domain` | No | `amazon.com` (default), `co.uk`, `de`, `fr`, `co.jp`, `ca`, `it`, `es`, `com.mx`, `com.br` |
| `country` | No | Two-letter code such as `de`. Used only when `domain` is not sent. |
| `page` | No | 1 to 20, default 1 |

## Response

`asin`, `domain`, `title`, `image`, `rating`, `ratings_count`, `total_offers`, `offers[]`, `next_page`. Each offer has `position`, `buy_box`, `condition`, `price`, `shipping`, `currency`, `delivery`, `seller_name`, `seller_id`, `sold_by_amazon`, `fulfilled_by_amazon`, `seller_rating`.

See the [docs](https://apiserpent.com/amazon-offers-api) for the complete field list and sample responses.

## Examples

| File | Language | Run |
| --- | --- | --- |
| [`example.py`](example.py) | Python 3 (`pip install requests`) | `SERPENT_API_KEY=sk_live_... python example.py` |
| [`example.mjs`](example.mjs) | Node.js 18+ (no dependencies) | `SERPENT_API_KEY=sk_live_... node example.mjs` |

## Use cases

- Buy Box and repricing tools
- Seller and competitor monitoring
- Price comparison apps

## More from Serpent API

- [Serpent API docs](https://apiserpent.com/docs) - Google, Bing, Yahoo, DuckDuckGo and Brave search, plus AI rank tracking
- [All SDKs and tools on GitHub](https://github.com/apiserpent)

## License

MIT
