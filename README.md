# MySql-window-functions-Solide-aze.27396-Sesonga-Raphael.28301-Impundu-Gatera-Brazia.29057-
Individual Assignment I: MySQL Window Functions
-----------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------

## 📌 Project Overview
This project demonstrates the use of **MySQL window functions** in solving a realistic retail business problem.  
The goal is to generate insights from transactional sales data, such as top products per region, customer segmentation, and sales growth trends.  

## 🏢 Business Problem
The retail company records thousands of transactions monthly but struggles to analyze:  
- Top-performing products per region/quarter  
- Running and moving sales totals  
- Month-over-month growth patterns  
- Customer segmentation by spending behavior  

## 🎯 Success Criteria
1. Identify **Top 5 products per region/quarter** → `RANK()`  
2. Compute **Running monthly sales totals** → `SUM() OVER()`  
3. Analyze **Month-over-month growth** → `LAG()/LEAD()`  
4. Segment customers into **quartiles** → `NTILE(4)`  
5. Calculate **3-month moving averages** → `AVG() OVER()`  

## 🗄️ Database Schema
### Tables
- **customers**: stores customer info (`customer_id`, `name`, `region`)  
- **products**: product catalog (`product_id`, `name`, `category`)  
- **transactions**: sales records (`transaction_id`, `customer_id`, `product_id`, `sale_date`, `amount`)  

### ER Diagram
```mermaid
erDiagram
    CUSTOMERS ||--o{ TRANSACTIONS : "makes"
    PRODUCTS ||--o{ TRANSACTIONS : "contains"
    CUSTOMERS {
        int customer_id PK
        varchar name
        varchar region
    }
    PRODUCTS {
        int product_id PK
        varchar name
        varchar category
    }
    TRANSACTIONS {
        int transaction_id PK
        int customer_id FK
        int product_id FK
        date sale_date
        decimal amount
    }
