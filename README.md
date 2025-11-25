This request asks for a **README file** and a comprehensive **Project Report** for the provided Python Inventory Management System code.

## 💾 Project README: Python Inventory Management System

# Python Inventory Management System

A simple, console-based Inventory and Order Management System built in Python, featuring object-oriented design and persistent data storage using JSON.

-----

### ✨ Features

  * **Product Management:** Add, update, and list products with unique IDs, name, price, and stock.
  * **Order Processing:** Create new sales orders, validate product availability, and automatically deduct stock.
  * **Data Persistence:** All inventory and order data is saved to and loaded from a local JSON file (`inventory_data.json`).
  * **Sales Reporting:** Generate a summary report of total orders, items sold, and revenue.
  * **CLI Interface:** A simple Command-Line Interface (CLI) for easy interaction with the system.

### 🛠️ Installation and Setup

This project uses only **standard Python libraries** and requires no external dependencies.

1.  **Save the Code:** Save the provided Python code into a file named, for example, `inventory_system.py`.

2.  **Run the System:** Execute the script from your terminal:

    ```bash
    python inventory_system.py
    ```

### 🚀 Usage

Upon running the script, the interactive Command-Line Interface (CLI) will start.

```
=== Inventory Management System ===
1. List Products
2. Add Product
3. Update Product
4. Create Order
5. List Orders
6. Sales Report
7. Exit
Enter your choice (1-7):
```

Follow the on-screen prompts to manage your inventory and process orders. The data will be saved to `inventory_data.json` in the same directory.

-----

### 📂 File Structure

  * `inventory_system.py`: Contains all the system classes and the main CLI logic.
  * `inventory_data.json`: (Automatically created) Stores product and order data persistently.

-----

## 📄 Project Report: Inventory Management System

## 1\. Cover Page

### Inventory Management and Order Processing System

**Project Developers:** Gemini AI
**Date:** November 2025

-----

## 2\. Introduction

This project implements a **Python-based Inventory Management and Order Processing System**. The core functionality revolves around managing product stock levels, recording sales transactions (orders), and providing basic financial reporting. The system is designed using **Object-Oriented Programming (OOP)** principles to create modular, maintainable, and scalable code structures for products, orders, and their respective managers.

-----

## 3\. Problem Statement

The challenge is to create a small-scale, robust system for tracking goods within an inventory and automating the process of recording sales. Key requirements include **persistent storage** to ensure data integrity across sessions, **stock validation** during order creation, and a simple, intuitive **Command-Line Interface (CLI)** for user interaction.

-----

## 4\. Functional Requirements

The system must perform the following user-facing operations:

| ID | Module | Requirement Description |
| :--- | :--- | :--- |
| **F-1** | Inventory | **Product Creation:** Allow a user to add a new product with a name, price, and initial stock. A unique ID must be generated (using `uuid`). |
| **F-2** | Inventory | **Product Update:** Allow a user to modify a product's name, price, or stock level based on its unique ID. |
| **F-3** | Inventory | **Product Listing:** Display a formatted list of all current products, including their ID, name, price, and current stock. |
| **F-4** | Order | **Order Creation:** Allow a user to create a sales order, validating that sufficient stock is available for all items in the order. |
| **F-5** | Order | **Stock Deduction:** Automatically deduct the sold quantity from the product's stock upon successful order creation. |
| **F-6** | Order | **Order Listing:** Display a detailed list of all recorded orders, including transaction date and total cost. |
| **F-7** | Reporting | **Sales Report:** Generate a summary report showing the total revenue and total number of orders processed. |

-----

## 5\. Non-functional Requirements

| ID | Type | Requirement Description |
| :--- | :--- | :--- |
| **NFR-1** | Usability | The system must provide a simple, menu-driven Command-Line Interface (CLI) for user interaction. |
| **NFR-2** | Performance | Operations (loading/saving) should be quick for a small to medium volume of data (managed by JSON file I/O). |
| **NFR-3** | Data Integrity | All product and order data must be saved persistently between runs using **File I/O** (JSON format). |
| **NFR-4** | Robustness | The system must include basic **Error Handling** (using `try/except`) for file operations (`FileNotFoundError`, `JSONDecodeError`) and user input (`ValueError`). |
| **NFR-5** | Modularity | The codebase must be organized into logical **OOP classes** (`Product`, `Order`, `InventoryManager`, `OrderManager`, `DataStorage`). |

-----

## 6\. System Architecture

The system utilizes a **three-tier architecture** built on an Object-Oriented design pattern:

1.  **Data Layer:** Handled by the **`DataStorage`** class, which manages the reading and writing of data to the persistent `inventory_data.json` file.
2.  **Business Logic Layer:** Comprises the core application logic using the **`Product`**, **`Order`**, **`InventoryManager`**, and **`OrderManager`** classes. These classes enforce business rules, such as stock validation and revenue calculation.
3.  **Presentation Layer:** Implemented by the **`InventorySystem`** class and its `run_cli()` method, which serves as the interactive Command-Line Interface.

-----

## 7\. Design Diagrams

### Class/Component Diagram

The system is composed of six distinct classes, demonstrating clear separation of concerns (Modularity NFR-5).

  * **`Product`**: Data structure for a single item.
  * **`Order`**: Data structure for a single transaction.
  * **`DataStorage`**: Handles all JSON file I/O (NFR-3).
  * **`InventoryManager`**: Manages a collection of `Product` objects (F-1, F-2, F-3).
  * **`OrderManager`**: Manages a collection of `Order` objects and implements order processing logic (F-4, F-5, F-7). It holds a dependency on `InventoryManager`.
  * **`InventorySystem`**: The main entry point, aggregating the managers and providing the CLI (NFR-1).

### Workflow Diagram (Order Creation)

This diagram visualizes the critical **F-4 (Order Creation)** process, highlighting the stock validation and update steps (F-5).

### Sequence Diagram (Creating an Order)

This diagram shows the sequence of interactions between the main objects when a user creates an order via the CLI.

### ER Diagram (Entity Relationship)

Since the persistent storage uses a JSON file structure (not a relational database), the relationships are conceptual but mirrored in the JSON schema. The key entities are **Products** and **Orders**.

  * **Product:** The primary entity, uniquely identified by `id`.
  * **Order:** Contains a list of items (`items`), which represents a **Many-to-Many** relationship with `Product` (an order can have many products, and a product can be in many orders). The `items` dictionary in `Order` serves as the intermediary/linking table, storing the `product_id` and `quantity_sold`.

### Use Case Diagram

This diagram outlines the primary functions accessible to the **User** role in the system.







