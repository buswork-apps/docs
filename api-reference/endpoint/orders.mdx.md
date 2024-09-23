---
title: 'Orders'
description: 'Endpoints for managing orders'
---

# Orders

This section covers the endpoints used for managing orders in the BusWork system.

## Create New Order (SaaS)

Create a new order using the SaaS interface.

### Request

```http
POST /atopems/orders/new/saas
Content-Type: application/json
api-key: YOUR_API_KEY

{
  "customer_id": 0,
  "customer_note": "string",
  "currency": "string",
  "payment_method": "string",
  "payment_method_title": "string",
  "set_paid": true,
  "line_items": [
    {
      "product_id": 0,
      "quantity": 0,
      "subtotal": 0,
      "total": 0
    }
  ],
  "shipping_lines": [
    {
      "method_id": "string",
      "method_title": "string",
      "total": "string"
    }
  ]
}
```

### Response

```json
{
  "success": true,
  "message": "Order created successfully"
}
```

## Create New Order (Webhook)

Create a new order via webhook.

### Request

```http
POST /atopems/orders/new
Content-Type: application/json

{
  "id": 0,
  "customer_id": 0,
  "date_created_gmt": "2023-01-01T00:00:00Z",
  "line_items": [
    {
      "sku": "string",
      "quantity": 0
    }
  ]
}
```

### Response

```
200 OK
Webhook data received and processed
```

## Get Orders Batch

Retrieve a batch of orders, optionally filtered by date and/or client ID.

### Request

```http
GET /atopems/orders/batch?date=YYYY-MM-DD&gecom_id=12345
api-key: YOUR_API_KEY
```

### Response

```json
[
  {
    "order_id": 0,
    "gecom_id": 0,
    "order_items": [
      {
        "sku": "string",
        "qty": 0
      }
    ],
    "order_creation_date": "2023-01-01",
    "customer_id": 0
  }
]
```

All endpoints will return appropriate error responses for invalid inputs or server errors.
