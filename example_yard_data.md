### REST API Documentation

#### Endpoint: Get All Yards

**URL:** `https://example.com/getYards`

**Method:** `GET`

**Description:** This endpoint retrieves a list of all yards, including their IDs and names.

**Response:**

- **Status Code:** `200 OK`
- **Content-Type:** `application/json`
- **Body:**
  ```json
  [
    {
      "id": "yard1",
      "name": "Yard One"
    },
    {
      "id": "yard2",
      "name": "Yard Two"
    },
    ...
  ]
  ```

**Example Request:**

```bash
curl -X GET "https://example.com/getYards"
```

**Example Response:**

```json
[
  {
    "id": "yard1",
    "name": "Yard One"
  },
  {
    "id": "yard2",
    "name": "Yard Two"
  }
]
```

**Notes:**

- The response is an array of objects, each representing a yard with its `id` and `name`.
- Ensure proper error handling for cases where the request might fail.

#### Endpoint: Get Yard Data

**URL:** `https://example.com/getYardData`

**Method:** `GET`

**Description:** This endpoint retrieves a list of all blocks in a specified yard, including the block ID, block name, and a list of items with their names and quantities.

**Query Parameters:**

- `yardID` (required): The ID of the yard to retrieve data for.

**Response:**

- **Status Code:** `200 OK`
- **Content-Type:** `application/json`
- **Body:**
  ```json
  {
    "blocks": [
      {
        "id": "blockA",
        "name": "Block A",
        "items": [
          {
            "name": "Item 1",
            "quantity": 10
          },
          {
            "name": "Item 2",
            "quantity": 5
          }
        ]
      },
      {
        "id": "blockB",
        "name": "Block B",
        "items": [
          {
            "name": "Item 3",
            "quantity": 20
          }
        ]
      }
    ]
  }
  ```

**Example Request:**

```bash
curl -X GET "https://example.com/getYardData?yardID=yard1"
```

**Example Response:**

```json
{
  "blocks": [
    {
      "id": "blockA",
      "name": "Block A",
      "items": [
        {
          "name": "Item 1",
          "quantity": 10
        },
        {
          "name": "Item 2",
          "quantity": 5
        }
      ]
    },
    {
      "id": "blockB",
      "name": "Block B",
      "items": [
        {
          "name": "Item 3",
          "quantity": 20
        }
      ]
    }
  ]
}
```

**Notes:**

- The response includes an array of blocks, each containing a block ID, block name, and a list of items with their names and quantities.
- Ensure proper error handling for cases where the request might fail.