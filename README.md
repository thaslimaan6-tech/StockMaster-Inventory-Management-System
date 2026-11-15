# 📦 StockMaster – Inventory Management System

**A JavaFX-based desktop application for managing products, suppliers, purchases, sales, inventory levels, and business reports using Java and MySQL.**

[![Java](https://img.shields.io/badge/Java-21-orange?logo=openjdk)](https://www.oracle.com/java/)
[![JavaFX](https://img.shields.io/badge/JavaFX-21.0.13-blue)](https://openjfx.io/)
[![MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Build-Maven-C71A36?logo=apachemaven)](https://maven.apache.org/)
[![Status](https://img.shields.io/badge/Project-Completed-success)]()

---

## 📌 Overview

**StockMaster** is a desktop-based Inventory Management System developed using Java 21, JavaFX, and MySQL.

The application provides a centralized platform to manage essential inventory operations, including product management, supplier management, purchase transactions, sales transactions, stock monitoring, and report generation.

It helps simplify inventory-related activities by maintaining organized records, automatically updating stock quantities after purchases and sales, and providing downloadable reports in Excel and PDF formats.

The project demonstrates the practical integration of object-oriented programming, graphical user interface development, database connectivity, transaction handling, and report generation.

## ✨ Key Features

### 1. Product Management
- Add new products.
- View available product details.
- Update existing product information.
- Delete product records.
- Search products by name or category.

### 2. Supplier Management
- Add supplier information.
- View supplier records.
- Update supplier details.
- Delete suppliers.
- Search supplier information.

### 3. Purchase Management
- Record product purchases.
- Maintain supplier and purchase details.
- Store individual purchase items.
- Automatically increase product stock after successful purchases.

### 4. Sales Management
- Record sales transactions.
- Maintain sales history.
- Calculate total sales amounts.
- Validate available stock before processing sales.
- Automatically decrease stock after successful sales.

### 5. Stock Management
- View available product quantities.
- Monitor current inventory levels.
- Identify low-stock products.
- Identify out-of-stock products.
- Calculate inventory value.

### 6. Reports & Analytics
Generate three types of reports:

- **Sales Report:** Displays sales transactions and total sales amounts with date-based filtering.
- **Purchase Report:** Displays purchase transactions, supplier details, and purchase amounts with date-based filtering.
- **Inventory Report:** Displays product quantities, reorder levels, inventory values, and stock status.

### 7. Report Export
- Export reports to Excel (`.xlsx`) using Apache POI.
- Export reports to PDF (`.pdf`) using Apache PDFBox.
- Save generated reports locally.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Java 21 | Core programming language and application logic |
| JavaFX 21.0.13 | Desktop graphical user interface |
| MySQL | Relational database management |
| JDBC | Java–MySQL database connectivity |
| MySQL Connector/J 9.5.0 | MySQL JDBC driver |
| Apache Maven | Build automation and dependency management |
| Apache POI 6.0.0 | Excel report generation |
| Apache PDFBox 3.0.8 | PDF report generation |
| Visual Studio Code | Development environment |

---

## 🏗️ System Architecture

StockMaster follows a layered application structure.

```text
             USER
               |
               v
     PRESENTATION LAYER
            JavaFX
               |
               v
    APPLICATION / LOGIC LAYER
         Java Classes
               |
               v
       DATA ACCESS LAYER
           DAO Classes
               |
               v
        JDBC CONNECTIVITY
               |
               v
        DATABASE LAYER
             MySQL
```

### Project Structure

```text
StockMaster/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── stockmaster/
│       │           │
│       │           ├── Main.java
│       │           │
│       │           ├── controller/
│       │           │
│       │           ├── database/
│       │           │   └── DBConnection.java
│       │           │
│       │           ├── dao/
│       │           │   ├── ProductDAO.java
│       │           │   ├── SupplierDAO.java
│       │           │   ├── PurchaseDAO.java
│       │           │   ├── SaleDAO.java
│       │           │   ├── StockManagementDAO.java
│       │           │   └── ReportDAO.java
│       │           │
│       │           ├── model/
│       │           │
│       │           └── view/
│       │               ├── ProductView.java
│       │               ├── SupplierView.java
│       │               ├── PurchaseView.java
│       │               ├── SaleView.java
│       │               ├── StockManagementView.java
│       │               └── ReportView.java
│       │
│       └── resources/
│
├── pom.xml
└── README.md
```

*The structure above highlights the main application packages and classes.*

---

## 🗄️ Database Design

The application uses a MySQL database named:

`stockmaster_db`

The database operations reference the following tables:

| Table | Description |
|---|---|
| `products` | Stores product details and current stock quantities. |
| `suppliers` | Stores supplier information. |
| `purchases` | Stores purchase transaction details. |
| `purchase_items` | Stores individual products included in purchases. |
| `sales` | Stores sales transaction details. |
| `sale_items` | Stores individual products included in sales. |
| `admin` | Stores administrator records referenced by transactions. |

The purchase and sales item tables maintain the relationship between transaction records and individual products.

---

## ⚙️ Installation and Setup

Follow these steps to run StockMaster locally.

### Prerequisites

Make sure the following software is installed:

- Java Development Kit (JDK) 21
- Apache Maven
- MySQL Server
- Visual Studio Code (or another Java IDE)

### Step 1: Clone the Repository

```bash
git clone https://github.com/thaslimaan6-tech/StockMaster-Inventory-Management-System.git
```

### Step 2: Navigate to the Project Directory

```bash
cd StockMaster-Inventory-Management-System
```

### Step 3: Configure the MySQL Database

Create the database in MySQL:

```sql
CREATE DATABASE stockmaster_db;
```

Configure the database tables and relationships required by the application before running it.

### Step 4: Configure Database Credentials

The application reads database credentials through environment variables.

**Windows PowerShell:**

```powershell
$env:STOCKMASTER_DB_USER="root"
$env:STOCKMASTER_DB_PASSWORD="your_mysql_password"
```

Replace the example password with your own MySQL password.

**Important:** Do not commit database passwords or other sensitive credentials to GitHub.

### Step 5: Build the Project

```bash
mvn clean compile
```

### Step 6: Run the Application

```bash
mvn javafx:run
```

The StockMaster desktop application should launch after a successful database connection.

---

## 🔄 Application Workflow

The core inventory workflow is:

```text
       PRODUCT MANAGEMENT
               |
               v
       SUPPLIER MANAGEMENT
               |
               v
       PURCHASE MANAGEMENT
               |
               v
       STOCK QUANTITY INCREASES
               |
               v
         SALES MANAGEMENT
               |
               v
       STOCK QUANTITY DECREASES
               |
               v
        STOCK MONITORING
               |
               v
       REPORTS & ANALYTICS
               |
               v
        EXCEL / PDF EXPORT
```

---

## 🧪 Testing and Validation

The application was tested through the following functional scenarios:

- Product and supplier CRUD operations.
- Purchase transaction recording.
- Automatic stock increase after purchases.
- Sales transaction recording.
- Stock validation before sales.
- Automatic stock deduction after sales.
- Low-stock and out-of-stock identification.
- Sales and purchase reports with date filtering.
- Inventory report generation.
- Excel and PDF report exports.

These tests helped validate the core inventory operations and database interactions.

---

## ⚠️ Challenges Faced and Solutions

| Challenge | Resolution |
|---|---|
| MySQL connection configuration | Configured JDBC connectivity and environment-based database credentials. |
| Missing administrator record | Added a valid administrator record for transaction processing. |
| Stock quantity consistency | Implemented stock updates within purchase and sales database operations. |
| Insufficient stock during sales | Added stock availability validation before processing sales. |
| Java compilation and integration errors | Debugged compiler errors and corrected method and variable issues. |
| Apache POI class-name conflict | Used fully qualified class names for Apache POI Cell objects. |
| PDF font compatibility | Used PDFBox standard fonts and substituted `Rs.` for the unsupported Rupee symbol. |
| Maven build issues on Windows | Resolved file-lock issues by closing running Java processes before cleaning build files. |

---

## 🚀 Future Enhancements

The current version implements the core inventory management workflow. Potential future improvements include:

- **Advanced Dashboard:** Interactive charts for sales, purchases, and stock statistics.
- **User Authentication:** Secure login with Admin and Employee roles.
- **Barcode Integration:** Faster product identification and stock entry.
- **Automated Notifications:** Alerts when products reach their reorder levels.
- **Cloud Integration:** Centralized inventory access across multiple locations.
- **Advanced Analytics:** Sales trends, profit analysis, and demand forecasting.
- **Database Backup:** Automated backup and recovery functionality.

---

## 🎯 Learning Outcomes

Through the development of StockMaster, we gained practical experience in:

- Object-Oriented Programming using Java.
- Building desktop applications using JavaFX.
- Relational database management using MySQL.
- Database connectivity using JDBC.
- Implementing CRUD operations using DAO classes.
- Managing database transactions.
- Handling application errors and debugging.
- Generating Excel and PDF documents.
- Managing project dependencies using Maven.

---

## 👩‍💻 Developer

**Project:** StockMaster – Inventory Management System

**GitHub Repository:**  
[StockMaster-Inventory-Management-System](https://github.com/thaslimaan6-tech/StockMaster-Inventory-Management-System)

---

## 📄 License

This project is developed for academic and educational purposes.

---
