---
title: 'Products'
description: 'Endpoints for managing products'
---

# Products

This section covers the endpoints used for managing products in the BusWork system.

## Get Products by SKU

Retrieve products by partial SKU match.

### Request

```http
GET /atopems/products?sku=ABC123
api-key: YOUR_API_KEY
```

### Response

```json
[
  {
    "SKU": "string",
    "price_atopems": 0,
    "stock_atopems": 0
  }
]
```

This endpoint will return appropriate error responses for invalid inputs or server errors.
