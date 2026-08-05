# ☕ CoffeeShopManagementAPL

## Overview

CoffeeShopManagementAPL is a coffee shop management system developed in **Dyalog APL**.

The purpose of this project is to simulate the daily operations of a coffee shop by managing products, inventory, sales, refunds, receipts, and business reports.

The application contains **19 interconnected functions** that communicate through shared data structures. The project demonstrates modular programming, array manipulation, data management, and practical business logic implemented using the APL programming language.

The project was created using **standard Dyalog APL without external libraries**.

---

# ▶️ How to Run

After opening the workspace file:

```
EHManagment.dws
```

run:

```
MainMenu
```

The `MainMenu` function is the central entry point of the application and provides access to all available system features.

---

# ✨ Features

## 🔐 Login System

The application starts with a login system that provides controlled access to the coffee shop management system.
Prints also time when a cashier punched in, prints Real Time.

Function:

- `Login`

---

# 📦 Product Management

The product management module allows users to create, modify, and remove products.

| Function | Description |
|---|---|
| AddProduct | Adds a new product to the system |
| RemoveProduct | Removes an existing product |
| UpdatePrice | Updates product prices |
| CheckIfItemIsOnTheList | Checks whether a product exists |

---

# 📊 Inventory Management

The inventory system manages product quantities and stock information.

| Function | Description |
|---|---|
| CheckStock | Displays current stock information |
| RefillStock | Increases product quantity |
| LowOnStock | Displays products with low inventory, less than 31|
| AllProductDetails | Shows detailed product information |

---

# 🛒 Sales Management



The sales module handles selling products and returning money.

| Function | Description |
|---|---|
| SellItem | Processes product sales |
| ReturFunction | Handles returned products and refunds |
| TotalRevenue | Calculates total revenue |

Operational functions are connected through shared product, inventory, and sales data. Changes made in one part of the system can affect related information used by other functions.

---

# 🧾 Receipt & Reporting System

The reporting system consists of three connected functions:

| Function | Description |
|---|---|
| Receipt | Creates customer receipts |
| FullDailyRaport | Displays daily sales information |
| StatisticsOfTheDailyRaport | Provides business statistics |

`Receipt`, `FullDailyRaport`, and `StatisticsOfTheDailyRaport` work together as the reporting section of the application.

The daily report uses predefined daily sales data created for demonstration and analysis purposes.

---

# 📈 Product Analysis

The system also includes product analysis features:

| Function | Description |
|---|---|
| CheapestItem | Finds the cheapest product |
| MostExpensiveItem | Finds the most expensive product |
| Top3ExpensiveItems | Displays the three most expensive products |

*******VERY IMPORTANT*********
# 🔄 Function Interaction and Data Flow

One of the main goals of this project was to create a connected management system where functions work together through shared data structures.

The operational functions are not independent. Functions such as `AddProduct`, `UpdatePrice`, `RefillStock`, `SellItem`, and `ReturFunction` interact with the same product, inventory, and sales information.

For example:

When a product is added using `AddProduct`, the product information becomes available for other functions such as stock checking, selling, and inventory management.

When `UpdatePrice` is used, the new price is automatically available for future sales and calculations.

When `RefillStock` is executed, the product quantity is increased and the updated stock information can be viewed through inventory functions.

The `SellItem` function represents the main sales process. When a product is sold, the system uses existing product information such as name, price, and quantity to complete the transaction.

Example workflow:
SellItem
|
├── Select product
|
├── Check product availability
|
├── Reduce quantity from inventory
|
├── Increase sold quantity
|
└── Update sales-related information
Before sale:

Product: Latte
Price: 45 SEK
Quantity: 10
Sold: 20
Revenue: 900 SEK

After selling one Latte:

Product: Latte
Price: 45 SEK
Quantity: 9
Sold: 21
Revenue: 945 SEK

---

# 🔗 System Structure

```
                         MainMenu
                            |
 --------------------------------------------------
 |              |              |                  |
Login     Product System   Inventory System   Sales System
              |              |                  |
              |              |                  |
        AddProduct      CheckStock          SellItem
        RemoveProduct   RefillStock        ReturFunction
        UpdatePrice     LowOnStock         TotalRevenue
              |
              |
        Shared Product Data


              Reporting System

                    |
        --------------------------------
        |              |               |
     Receipt    FullDailyRaport   Statistics
```

The system is designed around shared data structures, allowing different functions to work together while keeping responsibilities separated.

---

# 🗂️ Data Structures

The application uses shared variables to store business information:

| Variable | Purpose |
|---|---|
| ItemName | Stores product names |
| Price | Stores product prices |
| Quantity | Stores available stock |
| Sold | Stores sold quantities |
| Orders | Stores customer orders |
| ReceiptNo | Stores receipt numbers |
| OrderTime | Stores order times |
| Payment | Stores payment information |

---

# ⚙️ Complete Function List

```
Login
MainMenu

AddProduct
RemoveProduct
UpdatePrice
CheckIfItemIsOnTheList

CheckStock
RefillStock
LowOnStock
AllProductDetails

SellItem
ReturFunction
TotalRevenue

Receipt
FullDailyRaport
StatisticsOfTheDailyRaport

CheapestItem
MostExpensiveItem
Top3ExpensiveItems
```

---

# 📁 Project Structure

```
CoffeeShopManagementAPL

│
├── CoffeeShopManagementAPL.dws
│
├── source
│   ├── MainMenu.aplf
│   ├── Login.aplf
│   ├── AddProduct.aplf
│   ├── SellItem.aplf
│   ├── Receipt.aplf
│   └── Other Functions
│
└── README.md
```

---

# 🛠️ Technologies Used

- Dyalog APL
- Git
- GitHub

---

# 🎯 Project Goals & Achievements

The main goal of this project was to create a complete coffee shop management system while developing practical programming skills using **Dyalog APL**.

During the development of CoffeeShopManagementAPL, several important programming and software design goals were achieved:

## 🧩 Modular Programming

The project was designed using multiple independent functions instead of one large program.

The system contains **19 functions**, where each function has its own responsibility while still working together through shared data structures.

This improved understanding of:
- Function organization
- Code structure
- Reusable programming logic
- Maintaining a larger project

---

## 📚 Working With APL Data Structures

A major goal was learning how to handle APL-specific data structures and operations.

The project uses:
- Arrays
- Vectors
- Nested arrays
- Indexing
- Searching
- Data manipulation

Examples include managing:
- Product lists
- Prices
- Quantities
- Orders
- Sales information

---

## 🏪 Creating Real Business Logic

The project was designed to simulate a real coffee shop workflow instead of only demonstrating simple programming examples.

The system includes realistic operations such as:

- Adding and removing products
- Updating prices
- Managing inventory
- Selling items
- Returning money to customers
- Calculating revenue
- Creating receipts
- Generating reports

The functions were created to work together and maintain consistent business information.

---

## 🔗 Connecting Multiple Functions Together

One important achievement was creating communication between different parts of the system.

For example:

- `AddProduct` creates new product information that can later be used by inventory and sales functions.
- `UpdatePrice` changes product prices used during future transactions.
- `RefillStock` updates inventory quantities.
- `SellItem` works with product, quantity, and sales data.
- `ReturFunction` handles returned products and customer refunds.

This helped develop an understanding of how larger software systems share and manage data.

---

## 📊 Data Analysis and Statistics

The most advanced part of the project was developing `StatisticsOfTheDailyRaport`.

This function required combining multiple calculations and organizing data to create useful business information.

The statistics module focuses on:
- Revenue analysis
- Sales overview
- Product performance
- Most sold products
- Most selling hours
- Daily business insights

This improved understanding of:
- Data processing
- Searching and filtering information
- Mathematical operations on arrays
- Turning raw data into useful results

---

## 🧾 Reporting System

Another goal was creating a reporting section that could present business information clearly.

The project includes:

- `Receipt`
- `FullDailyRaport`
- `StatisticsOfTheDailyRaport`

These functions demonstrate how stored data can be transformed into readable reports for analysis.

---

## 💻 Software Development Practices

During the project, additional development skills were practiced:

- Organizing a Dyalog APL workspace
- Using source files with GitHub
- Version control with Git
- Writing documentation
- Structuring a complete software project

---

## 🚀 Overall Achievement

By completing this project, I achieved experience in developing a complete management system from the beginning to the final documented version.

The project improved my understanding of programming logic, data organization, modular design, and how different components work together inside a larger application.
---

# 🚀 Future Improvements

Possible improvements:

- Connect live sales directly with daily reports
- Add database storage
- Add graphical user interface
- Add employee management
- Add automatic data saving

---

# 👨‍💻 Author

Stefan Sugic

Dyalog APL Project
