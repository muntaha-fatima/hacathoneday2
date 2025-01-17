# hacathoneday2 Market place technical foundation
Sanity Schema Design: Product Schema:

![alt text](image.png)

 export const product = { name: 'product', type: 'document', fields: [ {name: 'name', type: 'string', title: 'Product Name'}, {name: 'price', type: 'number', title: 'Price'}, {name: 'description', type: 'text', title: 'Description'}, {name: 'image', type: 'image', title: 'Product Image'}, {name: 'category', type: 'string', title: 'Category'} ] }; Order Schema: export const order = { name: 'order', type: 'document', fields: [ {name: 'orderNumber', type: 'string', title: 'Order Number'}, {name: 'customer', type: 'reference', to: [{type: 'customer'}], title: 'Customer'},



{name: 'products', type: 'array', of: [{type: 'reference', to: [{type: 'product'}]}], title: 'Products'}, {name: 'totalAmount', type: 'number', title: 'Total Amount'}, {name: 'status', type: 'string', title: 'Order Status'} ] }; Customer Schema export const customer = { name: 'customer', type: 'document', fields: [ {name: 'name', type: 'string', title: 'Customer Name'}, {name: 'email', type: 'string', title: 'Email'}, {name: 'address', type: 'text', title: 'Address'}, {name: 'phone', type: 'string', title: 'Phone Number'} ] }; Technical Documentation: 1. System Architecture:

1.1 Components - Frontend (Next.js): User interface aur interactions handle Karta hai. - Sanity CMS: Content management aur data storage ke liye use hota hai. - Third-party APIs: Shipment tracking aur payments ke liye integrate kiye gaye hain. 2. API Endpoints: [Yahan pe aap upar di gayi API endpoints table paste kar sakte hain]



3. Sanity Schemas: Product Schema: export const product = { name: 'product', type: 'document', fields: [ {name: 'name', type: 'string', title: 'Product Name'}, {name: 'price', type: 'number', title: 'Price'}, {name: 'description', type: 'text', title: 'Description'}, {name: 'image', type: 'image', title: 'Product Image'}, {name: 'category', type: 'string', title: 'Category'} ] };


Order Schema: export const order = { name: 'order', type: 'document', fields: [ {name: 'orderNumber', type: 'string', title: 'Order Number'}, {name: 'customer', type: 'reference', to: [{type: 'customer'}], title: 'Customer'}, {name: 'products', type: 'array', of: [{type: 'reference', to: [{type: 'product'}]}], title: 'Products'}, {name: 'totalAmount', type: 'number', title: 'Total Amount'}, {name: 'status', type: 'string', title: 'Order Status'} ] }; Customer Schema: export const customer = { name: 'customer', type: 'document', fields: [ {name: 'name', type: 'string', title: 'Customer Name'}, {name: 'email', type: 'string', title: 'Email'}, {name: 'address', type: 'text', title: 'Address'},

{name: 'phone', type: 'string', title: 'Phone Number'} ] }; 4. Data Flow: - User frontend se interact karta hai. - Frontend Sanity CMS se data fetch karta hai ya update karta hai. - Orders create hone par, shipment tracking aur payment APIs trigger hote hain.