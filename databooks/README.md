📚 Bookshop Dashboard – Power BI Project

Este proyecto forma parte de mi portafolio de Power BI.
Está basado en el esquema relacional Bookshop Database que previamente desarrollé en MySQL (ver aquí 👉 https://github.com/CamilaVHeuer/portfolio-database/tree/main/bookshop-project SQL Bookshop Project).
Las visualizaciones estan vinculadas a las quieries del proyecto Bookshop buscando represantarlas de manera visual. 

## 🎯 Objetivos
- Analizar las ventas de una librería ficticia en distintos períodos de tiempo.
- Identificar a los **clientes recurrentes** y los que más gastaron.
- Detectar los **libros más vendidos** y el comportamiento por autor y país de origen.
- Evaluar la disponibilidad de inventario y libros con bajo stock.
- Crear un tablero de **portada ejecutiva** con KPIs clave.

---

## 📊 Métricas principales
- **Ventas totales**: $552.950  
- **Unidades vendidas**: 13  
- **Ticket promedio mensual**: entre $30.000 y $50.000  
- **Cliente con mayor gasto**: Emilia Diaz ($130.800)  
- **Top 3 clientes recurrentes**: Camila Perez (3 compras), Emilia Diaz (2), Pablo Perez (2)  
- **Libro más vendido**: *Origin* (5 unidades)  
- **Top 3 libros más vendidos**: Origin, Angels and Demons, Nothing Lasts Forever  

---

## 📈 Visualizaciones
- **Portada ejecutiva** con KPIs: ventas totales, unidades vendidas, libro más vendido, top 3 clientes recurrentes.  
- **Inventario de libros**: listado general, libros con bajo stock, país de origen de autores, libro más caro y más barato.  
- **Ventas y facturación**: tabla de ventas, ingresos mensuales, desglose por canal (tienda física vs web), ticket promedio.  
- **Clientes**: clientes con más compras, clientes que más gastaron, ticket promedio mensual, clientes recurrentes.  
- **Autores**: libros vendidos por autor y total de ventas por país de origen.  

---

## 📐 Medidas y cálculos DAX

Se implementaron medidas y columnas calculadas en DAX para enriquecer el modelo:

- **units_sold** = `SUM(sale_details[quantity])`  para unidades vendidas
- **best_selling_book** = medida con `TOPN + SUMMARIZE` para devolver el título con mayor cantidad de ventas  
- **quantity_purchases** = `COUNT(sales[sale_id])` + visual filtrado con TopN  para determinar el top 3 de clientes recurrentes
- **calendar table** con columnas de Año, MesNum, MesNombre, AñoMes (usada para gráficos de ticket promedio mensual y comparaciones temporales)

  ---

## 🗂️ Dataset
- **Origen**: base de datos *Bookshop* creada en MySQL.  
- **Tablas utilizadas**:  
  - `books` (catálogo de libros: Book_id, author_id, title, gender, price, stock)  
  - `authors` (author_id, author_name, country)  
  - `customers` (customer_id, customer_name, email)  
  - `sales` (sale_id, customer_id, date, mode, total)  
  - `sale_details` (detalle de cada venta: detail_id, sale_id, book_id, quantity, unit_price)  

---

## 🛠️ Tecnologías usadas
- **SQL (MySQL):** modelado y carga inicial de datos.  
- **Power Query:** transformaciones básicas.  
- **DAX:** medidas calculadas (units sold, best selling book,  top customers, etc.).  
- **Power BI Desktop:** diseño del dashboard e interactividad.  

---

📌 Este proyecto forma parte de mi portafolio de **Power BI**, y está vinculado con mi proyecto de **SQL Bookshop Database**.
