📚 Bookshop Dashboard – Power BI Project

This project is part of my Power BI portfolio. It is based on the Bookshop Database relational schema that I previously developed in MySQL (see here 👉 https://github.com/CamilaVHeuer/portfolio-database/tree/main/bookshop-project SQL Bookshop Project).
The visualizations are connected to the Bookshop project queries, aiming to represent them in a visual way.

## 🎯 Objetives
- Analyze the sales of a fictional bookstore across different time periods.
- Identify **recurring customers** and the ones with the highest spending.
- Detect the **best-selling books** and analyze behavior by author and country of origin.
- Evaluate inventory availability and books with low stock.
- Create an executive summary dashboard with key KPIs.

---

## 📊 Main Metrics
- **Total sales**: $552.950  
- **Units old**: 13  
- **Average monthly ticket**: between $30.000 and $50.000  
- **Top spending customer**: Emilia Diaz ($130.800)  
- **Top 3 recurring customers**: Camila Perez (3 compras), Emilia Diaz (2), Pablo Perez (2)  
- **Best-selling-book**: *Origin* (5 units)  
- **Top 3 best-selling-books**: Origin, Angels and Demons, Nothing Lasts Forever 

---

## 📈 Visualizations
- **Executive summary** with KPIs: total sales, units sold, best-selling book, top 3 recurring customers. 
- **Book inventory**: general listing, low-stock books, authors’ country of origin, most expensive and cheapest book.
- **Sales and revenue**: sales table, monthly revenue, breakdown by channel (physical store vs. web), average ticket.  
- **Customers**: top customers by number of purchases, top spenders, average monthly ticket, recurring customers.
- **Authors**: books sold per author and total sales by country of origin.

---

## 📐 DAX Measures and Calculations

DAX measures and calculated columns were implemented to enrich the model:
- **units_sold** = SUM(sale_details[quantity]) → total units sold
- **best_selling_book** → measure using TOPN + SUMMARIZE to return the title with the highest sales
- **quantity_purchases** = COUNT(sales[sale_id]) + TopN filtered visual to determine the top 3 recurring customers
- **calendar table** with columns for Year, MonthNum, MonthName, YearMonth (used for monthly ticket visuals and time comparisons)
  
  ---

## 🗂️ Dataset
- **Source**: *Bookshop* database created en MySQL.  
- **Tables used**:  
  - `books` (catálogo de libros: Book_id, author_id, title, gender, price, stock)  
  - `authors` (author_id, author_name, country)  
  - `customers` (customer_id, customer_name, email)  
  - `sales` (sale_id, customer_id, date, mode, total)  
  - `sale_details` (detalle de cada venta: detail_id, sale_id, book_id, quantity, unit_price)  

---

## 🛠️ Technologies Used
- **SQL (MySQL):** data modeling and initial load. 
- **Power Query:** basic transformations. 
- **DAX:** calculated measures (units sold, best-selling book, top customers, etc.).
- **Power BI Desktop:** dashboard design and interactivity 

---

📌 This project is part of my **Power BI portfolio** and is linked to my SQL **Bookshop Database project**.

##  Author
Camila Villalba Heuer
cbvillalbaheuer@gmail.com
