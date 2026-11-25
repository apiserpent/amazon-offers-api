[English](README.md) | **简体中文**

# Amazon 卖家报价 API

获取某个 Amazon ASIN 下的全部卖家报价：价格、运费、成色、Buy Box 归属和卖家评分，以 JSON 返回。

由 [Serpent API](https://apiserpent.com) 提供。完整文档：**[Amazon Offers API 文档](https://apiserpent.com/amazon-offers-api)**。

## 快速开始

1. 在 [apiserpent.com](https://apiserpent.com) 注册并获取 API Key，每个账号赠送 10 次免费调用。
2. 在请求头 `X-API-Key` 中带上你的 Key 调用接口：

```bash
curl -G "https://apiserpent.com/api/amazon/offers" \
  --data-urlencode "asin=B0BZXMJMXZ" \
  -H "X-API-Key: $SERPENT_API_KEY"
```

## 接口

`GET https://apiserpent.com/api/amazon/offers`

| 参数 | 必填 | 说明 |
| --- | --- | --- |
| `asin` | 是 | 10 位 ASIN，图书可使用 ISBN-10 |
| `domain` | 否 | `amazon.com`（默认）、`co.uk`、`de`、`fr`、`co.jp`、`ca`、`it`、`es`、`com.mx`、`com.br` |
| `country` | 否 | 两位国家代码，如 `de`；仅在未传 `domain` 时生效。 |
| `page` | 否 | 页码，1 到 20，默认 1 |

## 返回结果

顶层字段：`asin`、`domain`、`title`、`image`、`rating`、`ratings_count`、`total_offers`、`offers[]`、`next_page`。每条报价包含 `position`、`buy_box`、`condition`、`price`、`shipping`、`currency`、`delivery`、`seller_name`、`seller_id`、`sold_by_amazon`、`fulfilled_by_amazon`、`seller_rating`。

完整字段列表和响应示例请参阅[文档](https://apiserpent.com/amazon-offers-api)。

## 示例代码

| 文件 | 语言 | 运行方式 |
| --- | --- | --- |
| [`example.py`](example.py) | Python 3（`pip install requests`） | `SERPENT_API_KEY=sk_live_... python example.py` |
| [`example.mjs`](example.mjs) | Node.js 18+（无需依赖） | `SERPENT_API_KEY=sk_live_... node example.mjs` |

## 应用场景

- Buy Box 监控与自动调价工具
- 卖家与竞品监控
- 比价应用

## Serpent API 的更多能力

- [Serpent API 文档](https://apiserpent.com/docs)：Google、Bing、Yahoo、DuckDuckGo 和 Brave 搜索结果，以及 AI 引用排名跟踪
- [GitHub 上的全部 SDK 与工具](https://github.com/apiserpent)

## 许可证

MIT
