Inventory Management API is a RESTful service designed to efficiently handle product inventory 
operations such as adding, retrieving, updating, and deleting product information. This project includes 
a comprehensive Postman collection that not only tests API functionality but also validates 
performance, structure, and reliability through advanced automated test scripts.
The system interacts with a mock API endpoint to simulate real-world inventory operations. Each API 
request in the collection is equipped with detailed validations, including status code checks, header 
verification, response schema validation, and field integrity checks. Additionally, the collection uses 
Postman Visualizer to provide interactive visual output such as product tables, stock distribution 
charts, and formatted product detail cards.
API Overview & Architecture
1. Introduction to the API
The Inventory Management API is a RESTful service designed to handle basic inventory operations 
such as product creation, retrieval, updating, and deletion. It enables users to manage product 
details efficiently through standardized HTTP methods. The API used in this project is hosted on 
MockAPI, a platform that simulates real-world API behavior and provides predictable, structured 
responses ideal for testing.
The API follows REST principles, using resource-based URLs, structured JSON responses, and 
stateless communication. This makes it highly scalable, testable, and compatible with various clients 
including web applications, command-line tools, and automated testing frameworks such as 
Postman and Newman.
2. Base URL
The Inventory Management API is accessible using the following base URL:
https://692ab9037615a15ff24d790a.mockapi.io
3. Main API Endpoint
The core resource managed in this project is Products.
Endpoint:/Products
Field Type Description
ProductID String Unique identifier for each product
ProductName String Name of the product
Suppliers String Supplier or vendor name
Stocks Boolean Product stock status (true/false)
API Base URL: https://69258a4282b59600d7241059.mockapi.io/products
4.CRUD Operations Overview
a. GET /Products – Retrieve All Products
This endpoint fetches a complete list of products from the inventory.
Used for:
• Validating product lists
• Visualizing stock distribution
• Verifying data structure
b. POST /Products – Add a New Product
Allows adding a new product to the database.
{
 "ProductName": "Laptop",
 "Suppliers": "Tech World",
 "Stocks": true
}
c. GET /Products/{ProductID} – Retrieve Product by ID
Fetches detailed information about a single product.
Used to:
• Verify specific product data
• Validate schema
• Display product card in visualizer
d. PUT /Products/{ProductID} – Update Product
Updates a product’s name, supplier, or stock status.
e. DELETE /Products/{ProductID} – Delete Product
Removes a product from the inventory.
Also includes a follow-up request to verify deletion.
5. Environment Variables Used
To make the collection flexible and reusable, the following environment variables are implemented:
6.API Architecture
a. RESTful Architecture
The API follows a REST-based architecture, which includes:
• Client–Server Model:
The client (Postman/Newman) sends requests, and the server (MockAPI) returns JSON 
responses.
• Stateless Communication:
Each API request is independent and contains all required information.
• Uniform Resource Identifiers (URIs):
Resources are accessed using structured endpoints such as /Products/{id}.
• Standard HTTP Methods:
o GET → Read
o POST → Create
o PUT → Update
o DELETE → Remove
b. JSON Data Model
Data flows through the API in JSON format, enabling easy validation and parsing.
Example response:
Variable Description
baseURL Main API URL
endpoint API resource name ("Products")
ProductID Dynamic ID used for GET/PUT/DELETE
ID Separate ID for delete testing
ProductName Dynamic product name
Suppliers Supplier name
Stocks Boolean stock value
{
 "ProductName": "Keyboard",
 "Suppliers": "Digital Store",
 "Stocks": true,
 "ProductID": "45"
}
c. MockAPI Backend Simulation
MockAPI provides:
• Auto-generated IDs
• Cloud-hosted database
• Realistic request/response patterns
• Consistent structure for automated testing
This creates an environment closely resembling a real-world API backend.
7. System Diagram
8. Newman and HTML Extra Reporter
Newman is the command-line tool for running Postman collections without using the Postman 
application. It enables automated execution of API tests directly through the terminal, making it ideal 
for CI/CD pipelines and repeated testing workflows. Developers can run collections, apply 
environments, and export results with simple commands like:
newman run Inventory_management.postman_collection.json
 newman run Inventory_management.postman_collection.json -d data.csv
 newman run Inventory_management.postman_collection.json -d data.csv -r htmlextra
