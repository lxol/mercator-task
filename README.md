# mercator-task
Architect Interview Tasks - This repository contains solutions for three tasks assigned during the architect interview process.

## Task 1
![task1](https://github.com/user-attachments/assets/42d0954b-e9c2-4fdc-a999-68854475f99a)
### Solution
The following JSON Schema defines a `Person` object with required fields for `name`, `age`, and `email`.


```json
{
  "title": "Person",
  "type": "object",
  "properties": {
    "name": {
      "type": "string"
    },
    "age": {
      "type": "number"
    },
    "email": {
      "type": "string",
      "format": "email"
    },
    "address": {
      "street": {
        "type": "string"
      },
      "city": {
        "type": "string"
      }
    }
  },
  "required": [
    "name",
    "age",
    "email"
  ]
}
```

## Task 2
![task2](https://github.com/user-attachments/assets/b7dcd625-b270-4bc3-9f6c-233aad53b048)
## Solution
This JSON Schema defines a Product object with attributes for productId, productName, description, and other product details such as price, currency, and availability.
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "productId": {
      "type": "string"
    },
    "productName": {
      "type": "string"
    },
    "description": {
      "type": "string"
    },
    "price": {
      "type": "number"
    },
    "currency": {
      "type": "string",
      "enum": [
        "USD",
        "EUR",
        "GBP"
      ]
    },
    "available": {
      "type": "boolean"
    },
    "categories": {
      "type": "array",
      "items": {
        "type": "string"
      }
    },
    "dimensions": {
      "type": "object",
      "properties": {
        "width": {
          "type": "number",
          "minimum": 0
        },
        "height": {
          "type": "number",
          "minimum": 0
        },
        "depth": {
          "type": "number",
          "minimum": 0
        },
        "unit": {
          "type": "string",
          "enum": [
            "cm",
            "inches"
          ],
          "default": "cm"
        }
      },
      "required": [
        "width",
        "height",
        "depth",
        "unit"
      ]
    },
    "reviews": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "reviewId": {
            "type": "string"
          },
          "reviewer": {
            "type": "string"
          },
          "rating": {
            "type": "number",
            "minimum": 0,
            "maximum": 5,
            "pattern": "^[0-5](\\.\\d)?$"
          },
          "comment": {
            "type": "string"
          }
        },
        "required": [
          "reviewId",
          "reviewer",
          "rating",
          "comment"
        ]
      }
    },
    "stock": {
      "type": "object",
      "properties": {
        "quantity": {
          "type": "integer",
          "minimum": 0
        },
        "warehouseLocation": {
          "type": "string",
          "pattern": "^[A-Z]\\d+-\\d+$"
        }
      },
      "required": [
        "quantity",
        "warehouseLocation"
      ]
    }
  },
  "required": [
    "productId",
    "productName",
    "description",
    "price",
    "currency",
    "available",
    "categories",
    "dimensions",
    "reviews",
    "stock"
  ]
}
```

## Task 3
![task3](https://github.com/user-attachments/assets/a6165597-d171-43cc-bff5-c91bc0e79372)
## Solution
The following OpenAPI YAML describes a User schema for an API, defining required properties and specifying data formats for certain fields.

```yaml
openapi: 3.0.0
info:
  title: User API
  version: 1.0.0
paths: {}

components:
  schemas:
    User:
      type: object
      title: User
      required:
        - id
        - name
        - email
        - age
      properties:
        id:
          type: integer
        name:
          type: string
        email:
          type: string
          format: email
        age:
          type: integer

```
