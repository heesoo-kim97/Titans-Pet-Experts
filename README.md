# Titan's Pet Experts — E-Commerce Database

**Designing a centralized relational database to support e-commerce transactions, inventory management, and order fulfillment.**

---

## Table of Contents

* [Project Overview](#project-overview)
* [Business Problem](#business-problem)
* [Solution](#solution)
* [Technologies](#technologies)
* [System Analysis](#system-analysis)
* [Database Architecture](#database-architecture)
* [Database Design](#database-design)
* [SQL Implementation](#sql-implementation)
* [Key Insights](#key-insights)
* [Business Impact](#business-impact)
* [Skills Demonstrated](#skills-demonstrated)

---

## Project Overview

Titan's Pet Experts sought to expand its digital presence by introducing e-commerce capabilities following the recovery from the COVID-19 downturn.

The business needed a centralized system capable of connecting **customer transactions, product information, inventory levels, and shipment tracking** across online and in-store sales channels.

This project focused on designing a normalized relational database that could support the company's growing digital retail operations and provide a foundation for more efficient inventory and order management.

---

## Business Problem

The existing business environment lacked an integrated system for managing sales and fulfillment information across channels.

This created several operational challenges:

* Limited visibility into inventory levels
* Potentially inaccurate stock counts
* Fragmented sales information
* Delayed order fulfillment
* Difficulty tracking shipments
* Increased need for manual reconciliation

### Business Objective

Design a centralized database that would:

1. Connect customer, order, product, inventory, and shipment data
2. Support accurate inventory monitoring
3. Improve order-processing visibility
4. Track shipments throughout the fulfillment process
5. Distinguish between online and in-store transactions
6. Provide a scalable foundation for operational decision-making

---

## Solution

A **normalized relational database schema** was designed using MySQL Workbench. Microsoft Visio was used to create the data-flow diagrams and document system processes.

The database consists of five primary entities:

```text
Customer
   │
   └── Order
         │
         ├── Product
         │
         └── Shipment

Product
   │
   └── Inventory
```

Primary and foreign keys were used to establish relationships between entities and maintain referential integrity.

The resulting structure separates relatively static product information from dynamic inventory data while connecting transactions to fulfillment and shipment information.

---

## Technologies

| Technology            | Purpose                                                     |
| --------------------- | ----------------------------------------------------------- |
| **MySQL**             | Relational database development                             |
| **MySQL Workbench**   | EERD creation, database implementation, and SQL development |
| **Microsoft Visio**   | Data-flow diagrams and system-process documentation         |
| **SQL**               | Table creation, relationships, and data retrieval           |
| **EERD Modeling**     | Database architecture and relationship design               |
| **Microsoft Project** | Project scheduling and workplan development                 |

---

## System Analysis

Microsoft Visio was used to document system processes, information flows, and user interactions before implementing the relational database.

The analysis phase included:

* Data-flow diagrams
* Use-case analysis
* Business-process documentation
* Requirements translation
* Project workplan development

These artifacts helped connect the business problem to the proposed database structure.

<details>
<summary><strong>View Data-Flow Diagrams</strong></summary>

### Data-Flow Diagrams

Data-Flow Diagrams (DFDs) documented how information moves through the proposed e-commerce system.

The DFDs helped identify:

* External actors and business processes
* Customer and order information flows
* Product and inventory data flows
* Shipment and fulfillment processes
* Relationships between business activities and stored data

</details>

<details>
<summary><strong>View Use Cases</strong></summary>

### Use Cases

Use cases were developed to describe how users and business roles would interact with the proposed system.

Representative use cases included:

* Customer places an order
* Employee updates inventory
* Employee processes an order
* Employee tracks a shipment
* Business reviews sales-channel activity

Use cases helped translate business requirements into system behaviors and supported the design of the database entities and relationships.

#### Customer Places an Order

| Element            | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| **Primary Actor**  | Customer                                                               |
| **Goal**           | Complete an online purchase                                            |
| **Preconditions**  | Customer has selected products and provided required order information |
| **Main Flow**      | Customer selects products, submits order, and receives confirmation    |
| **Postconditions** | Order is recorded and made available for fulfillment                   |

#### Employee Updates Inventory

| Element            | Description                                                    |
| ------------------ | -------------------------------------------------------------- |
| **Primary Actor**  | Employee                                                       |
| **Goal**           | Maintain accurate inventory records                            |
| **Preconditions**  | Product exists in the database                                 |
| **Main Flow**      | Employee reviews stock levels and updates inventory quantities |
| **Postconditions** | Inventory records reflect current stock information            |

#### Employee Processes an Order

| Element            | Description                                                                           |
| ------------------ | ------------------------------------------------------------------------------------- |
| **Primary Actor**  | Employee                                                                              |
| **Goal**           | Prepare an order for fulfillment                                                      |
| **Preconditions**  | Order has been submitted and recorded                                                 |
| **Main Flow**      | Employee reviews order details, confirms product availability, and prepares the order |
| **Postconditions** | Order is ready for shipment or marked as processed                                    |

#### Employee Tracks a Shipment

| Element            | Description                                                          |
| ------------------ | -------------------------------------------------------------------- |
| **Primary Actor**  | Employee                                                             |
| **Goal**           | Monitor shipment progress                                            |
| **Preconditions**  | Shipment record is associated with an order                          |
| **Main Flow**      | Employee reviews shipment status and updates fulfillment information |
| **Postconditions** | Shipment status reflects the current delivery stage                  |

#### Business Reviews Sales-Channel Activity

| Element            | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| **Primary Actor**  | Business Manager                                                       |
| **Goal**           | Compare online and in-store transaction activity                       |
| **Preconditions**  | Orders contain sales-channel information                               |
| **Main Flow**      | Manager queries order data by channel and reviews transaction patterns |
| **Postconditions** | Business gains visibility into sales-channel activity                  |

> Use cases are included as supporting analysis artifacts rather than the primary focus of this portfolio project. The database design and SQL implementation remain the central technical deliverables.

</details>

<details>
<summary><strong>View Project Workplan</strong></summary>

### Project Workplan

A project workplan was created in Microsoft Project to organize project activities, dependencies, and deliverables.

The workplan included activities such as:

1. Requirements analysis
2. Business-process review
3. Data-flow modeling
4. Use-case development
5. Conceptual data modeling
6. Logical database design
7. Physical database design
8. SQL implementation
9. Testing and validation
10. Documentation and final review

The workplan demonstrates how the project was organized from initial requirements through database implementation and documentation.

</details>

---

## Database Architecture

### Entity-Relationship Diagram

The Entity-Relationship Diagram (EERD) was created in **MySQL Workbench**. It represents the relational database structure by showing the entities, attributes, primary keys, foreign keys, and relationships required for implementation.

Microsoft Visio was used separately to create the project's Data-Flow Diagrams (DFDs), which document how information moves through the proposed e-commerce system.

The database architecture centers around five core entities:

| Entity        | Purpose                                                     |
| ------------- | ----------------------------------------------------------- |
| **Customer**  | Stores customer information                                 |
| **Order**     | Records customer transactions and sales channels            |
| **Product**   | Stores product attributes such as name, category, and price |
| **Inventory** | Tracks stock quantity and reorder levels                    |
| **Shipment**  | Tracks fulfillment and delivery information                 |

### Relationship Design

The schema uses **primary and foreign keys** to connect related entities and enforce referential integrity.

For example:

* `CustomerID` connects customers to their orders
* `ProductID` connects products to inventory records
* `OrderID` connects transactions to shipment records

This structure allows related information to be retrieved across multiple tables using SQL JOIN operations.

---

## Database Design

### Product & Inventory Separation

Product and Inventory were intentionally modeled as separate entities.

**Product** contains relatively static attributes such as:

* Product name
* Category
* Price

**Inventory** contains operational attributes such as:

* Stock quantity
* Reorder level

Separating these entities reduces redundancy and allows inventory values to change without modifying the underlying product information.

### Order Channel Tracking

The `OrderChannel` attribute was incorporated into the Order table to distinguish between:

* Online purchases
* In-store purchases

This allows the business to compare transaction activity across sales channels and better understand fulfillment requirements.

### Shipment Tracking

Shipment records are linked to orders through `OrderID`.

This relationship provides visibility into the fulfillment lifecycle by connecting a customer's transaction with its corresponding delivery information.

---

## SQL Implementation

SQL was used to create and connect the relational tables and retrieve information across the database.

### Example: Joining Customer and Order Data

```sql
SELECT
    c.CustomerID,
    c.CustomerName,
    o.OrderID,
    o.OrderChannel
FROM Customer c
JOIN `Order` o
    ON c.CustomerID = o.CustomerID;
```

### Example: Connecting Orders with Shipment Information

```sql
SELECT
    o.OrderID,
    o.OrderChannel,
    s.ShipmentStatus
FROM `Order` o
JOIN Shipment s
    ON o.OrderID = s.OrderID;
```

> Additional queries can be added here to demonstrate inventory monitoring, order analysis, and fulfillment tracking.

---

## Key Insights

### 1. Normalization improves data integrity

Separating Product and Inventory prevents frequently changing inventory information from being stored alongside relatively static product attributes.

This reduces redundancy and helps minimize update anomalies.

### 2. Sales-channel visibility supports operational analysis

Adding `OrderChannel` enables the business to distinguish between online and in-store transactions.

This creates an opportunity to analyze purchasing behavior and compare fulfillment requirements across channels.

### 3. Linking orders and shipments improves fulfillment visibility

Connecting Shipment to Order through `OrderID` creates a direct relationship between a transaction and its delivery status.

This makes it easier to track orders throughout the fulfillment process.

### 4. Process modeling supports database design

The DFDs and use cases helped connect business requirements to the proposed database structure.

By documenting how users interact with the system and how information moves between processes, the analysis artifacts provided context for the entities, attributes, and relationships implemented in the relational model.

---

## Business Impact

The centralized relational database provides Titan's Pet Experts with a structured foundation for managing its expanding digital retail operations.

The database can support:

* **Inventory visibility** through stock and reorder-level tracking
* **Improved order accuracy** through structured transactional relationships
* **Fulfillment monitoring** through shipment tracking
* **Cross-channel analysis** through online vs. in-store classification
* **Reduced manual reconciliation** through centralized data
* **Scalable operations** as e-commerce activity increases

The database ultimately creates a foundation for future analysis involving **restocking strategies, logistics planning, customer purchasing behavior, and sales-channel performance.**

---

## Skills Demonstrated

* Relational Database Design
* Entity-Relationship Modeling
* Data-Flow Diagramming
* Use-Case Analysis
* Database Normalization
* Primary & Foreign Keys
* Referential Integrity
* SQL
* JOIN Operations
* MySQL Workbench
* Microsoft Visio
* Microsoft Project
* Data Modeling
* Business Requirements Analysis
* Project Planning
* Translating Business Problems into Technical Solutions

---

## Portfolio Presentation Notes

The **EERD created in MySQL Workbench, DFDs created in Microsoft Visio, and SQL implementation** should be the primary artifacts showcased in this repository because they most directly demonstrate technical and analytical skills.

Use cases and the project workplan are included inside collapsible `<details>` sections so visitors can review the supporting documentation without overwhelming the main README.

Recommended artifact priority:

1. **EERD created in MySQL Workbench** — primary database design artifact
2. **DFDs created in Microsoft Visio** — system and process analysis
3. **SQL scripts and queries** — technical implementation
4. **Use cases** — requirements and user-interaction analysis
5. **Microsoft Project workplan** — project planning and organization

The collapsible sections keep the README concise while still demonstrating the full project lifecycle, from requirements analysis and process modeling through database implementation and documentation.
