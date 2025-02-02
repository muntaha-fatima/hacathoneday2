# Hackathon Day 2

## Sanity Schema Design: Product Schema:

![Product Schema](image-1.png)

## API Endpoints:

| Endpoints                | Method | Description                     |
|--------------------------|--------|---------------------------------|
| `/Products`              | GET    | Fetches all products           |
| `/Products/id`           | GET    | Fetches a specific product     |
| `/Orders`                | POST   | Creates a new order            |
| `/Orders/id`             | GET    | Fetches a specific order       |
| `/shipment/tracking/id`  | GET    | Tracks shipment status         |

### Product Schema:
```javascript
export const product = {
  name: 'product',
  type: 'document',
  fields: [
    { name: 'name', type: 'string', title: 'Product Name' },
    { name: 'price', type: 'number', title: 'Price' },
    { name: 'description', type: 'text', title: 'Description' },
    { name: 'image', type: 'image', title: 'Product Image' },
    { name: 'category', type: 'string', title: 'Category' }
  ]
};
```

### Order Schema:
```javascript
export const order = {
  name: 'order',
  type: 'document',
  fields: [
    { name: 'orderNumber', type: 'string', title: 'Order Number' },
    { name: 'customer', type: 'reference', to: [{ type: 'customer' }], title: 'Customer' },
    { name: 'products', type: 'array', of: [{ type: 'reference', to: [{ type: 'product' }] }], title: 'Products' },
    { name: 'totalAmount', type: 'number', title: 'Total Amount' },
    { name: 'status', type: 'string', title: 'Order Status' }
  ]
};
```

### Customer Schema:
```javascript
export const customer = {
  name: 'customer',
  type: 'document',
  fields: [
    { name: 'name', type: 'string', title: 'Customer Name' },
    { name: 'email', type: 'string', title: 'Email' },
    { name: 'address', type: 'text', title: 'Address' },
    { name: 'phone', type: 'string', title: 'Phone Number' }
  ]
};
```

## Technical Documentation:

### 1. System Architecture:

![System Architecture](image-1.png)

#### 1.1 Components:
- **Frontend (Next.js):** Handles user interface and interactions.
- **Sanity CMS:** Used for content management and data storage.
- **Third-party APIs:** Integrated for shipment tracking and payments.

### 2. API Endpoints:

| Endpoints                | Method | Description                     |
|--------------------------|--------|---------------------------------|
| `/Products`              | GET    | Fetches all products           |
| `/Products/id`           | GET    | Fetches a specific product     |
| `/Orders`                | POST   | Creates a new order            |
| `/Orders/id`             | GET    | Fetches a specific order       |
| `/shipment/tracking/id`  | GET    | Tracks shipment status         |

### 3. Sanity Schemas:

#### Product Schema:
```javascript
export const product = {
  name: 'product',
  type: 'document',
  fields: [
    { name: 'name', type: 'string', title: 'Product Name' },
    { name: 'price', type: 'number', title: 'Price' },
    { name: 'description', type: 'text', title: 'Description' },
    { name: 'image', type: 'image', title: 'Product Image' },
    { name: 'category', type: 'string', title: 'Category' }
  ]
};
```

#### Order Schema:
```javascript
export const order = {
  name: 'order',
  type: 'document',
  fields: [
    { name: 'orderNumber', type: 'string', title: 'Order Number' },
    { name: 'customer', type: 'reference', to: [{ type: 'customer' }], title: 'Customer' },
    { name: 'products', type: 'array', of: [{ type: 'reference', to: [{ type: 'product' }] }], title: 'Products' },
    { name: 'totalAmount', type: 'number', title: 'Total Amount' },
    { name: 'status', type: 'string', title: 'Order Status' }
  ]
};
```

#### Customer Schema:
```javascript
export const customer = {
  name: 'customer',
  type: 'document',
  fields: [
    { name: 'name', type: 'string', title: 'Customer Name' },
    { name: 'email', type: 'string', title: 'Email' },
    { name: 'address', type: 'text', title: 'Address' },
    { name: 'phone', type: 'string', title: 'Phone Number' }
  ]
};
```

### 4. Data Flow:
- Users interact with the frontend.
- The frontend fetches or updates data from Sanity CMS.
- When orders are created, shipment tracking and payment APIs are triggered.

