# Data Modeling Phase 

## Phase Overview

This Phase focuses on developing a robust and scalable data model for an e-commerce platform, transforming raw transactional data into a structured format optimized for analytical reporting and business intelligence.

The primary goal is to enable efficient data analysis, facilitate insightful dashboard creation, and support data-driven decision-making using Power BI.

---


## Data Modeling Methodology

The data modeling approach follows industry best practices, emphasizing a **Star Schema design** for optimal query performance and usability in analytical tools such as Power BI.

The modeling process consisted of the following stages:

---

## Step 1: Understanding Fact vs. Dimension Tables

Before starting the modeling process, it was essential to distinguish between **fact tables** and **dimension tables**.

* **Fact Tables:** Store quantitative business data (measures) such as sales, quantities, revenue, and transactions.
* **Dimension Tables:** Store descriptive attributes that provide context to facts, such as customer details, product information, or dates.

This separation improves analytical clarity and model efficiency.

---

## Step 2: Classifying the Raw Tables

Each raw dataset was reviewed and classified based on its role in the analytical model:

* Tables containing measurable business events were classified as **fact tables**.
* Tables containing descriptive attributes were classified as **dimension tables**.

This classification ensured the correct foundation for implementing the star schema structure.

---

## Step 3: Creating Additional Dimension Tables

To enhance analytical capabilities and enable deeper insights, several new dimension tables were created:

* **dim_date** – Enables time intelligence analysis (daily, monthly, yearly trends).
* **dim_city** – Supports geographic and regional analysis.
* **dim_device** – Allows analysis of user behavior by device type.
* **dim_channel** – Enables performance tracking by marketing channel.
* **dim_campaign** – Allows evaluation of marketing campaign effectiveness.
* **dim_customers** – Contains customer attributes for segmentation.
* **dim_products** – Stores product-related information.
* **dim_products_vendor** – Contains vendor or supplier information.
* **dim_products_category** – Provides product categorization.

### Creating dim_date using DAX

The **dim_date** table was created using **DAX (Data Analysis Expressions)** in Power BI to leverage built-in time intelligence capabilities.

  <img width="582" height="249" alt="image" src="https://github.com/user-attachments/assets/91bb40c3-6358-43fd-abe4-a2da55575a71" />

  <img width="592" height="446" alt="image" src="https://github.com/user-attachments/assets/dc645eb7-b0d6-41ca-b66f-e96486478ef4" />

---

## Dimension Table Preparation Using Power Query

Most dimension tables were prepared using a structured workflow in **Power Query**:

1. **Duplicate Columns** – Relevant columns were duplicated from fact tables.
2. **Remove Duplicates** – Ensured that each dimension contains unique values.
3. **Add Index Column** – Generated a unique surrogate key for the dimension.
4. **Merge with Fact Table** – The generated index was merged back into the fact table to create a foreign key relationship.

This process ensured consistent relationships and improved model performance.

## Example Power Query Transformations 

The following screenshots illustrate a subset of the Power Query transformations applied during the data preparation process.
### Power Query dim_city 

<img width="1465" height="649" alt="Screenshot 2026-04-30 045123" src="https://github.com/user-attachments/assets/f31b71c6-dc35-4ed1-b601-d9bbe487b783" />

### Power Query dim_channel​
<img width="1464" height="479" alt="Screenshot 2026-04-29 153609" src="https://github.com/user-attachments/assets/22e230f2-d905-425d-8dd9-028c5ba70a44" />

### Power Query dim_device​
<img width="1463" height="601" alt="Screenshot 2026-04-30 045423" src="https://github.com/user-attachments/assets/09f3dcbb-a9ca-4fb5-b506-108e02c756ae" />

### Power Query fact_website_daily
​<img width="1916" height="819" alt="Screenshot 2026-04-29 152107" src="https://github.com/user-attachments/assets/7fd28cfd-7159-43e1-9efa-695ea9b63e93" />

---

## Step 4: Implementing Primary Keys and Foreign Keys

To maintain data integrity and optimize query performance:

* **Primary Keys (PK):** Unique identifiers were defined for all dimension tables.
* **Foreign Keys (FK):** Corresponding keys were added to fact tables to link them with dimension tables.

This ensures proper relationships and prevents duplication or ambiguity within the model.



---

## Step 5: Establishing Relationships Between Tables

Relationships were created between fact and dimension tables using **primary keys (PK)** and **foreign keys (FK)**.

These relationships form the **Star Schema architecture**.

<img width="996" height="684" alt="image" src="https://github.com/user-attachments/assets/5ac7e56e-e13e-4099-a96e-198faba21b5b" />

<img width="999" height="635" alt="image" src="https://github.com/user-attachments/assets/594a59f8-ee4f-4e63-b033-2d85107ca72a" />

### Example: Star Schema for fact_website_daily

The following diagram illustrates how the fact_website_daily table connects to its surrounding dimension tables.

<img width="635" height="380" alt="image" src="https://github.com/user-attachments/assets/da174c05-02fe-4b9a-993a-e1e902f2344b" />

---

## Step 6: Schema Overview Visualization

The final model was visualized in **Power BI Model View**, clearly showing the relationships between fact and dimension tables.

The architecture follows a **Star Schema**, which simplifies reporting and improves performance in analytical queries.
This structure enables efficient filtering, aggregation, and drill-down analysis in Power BI.

<img width="4160" height="2928" alt="ecommerce_er_diagram_v2 (2)" src="https://github.com/user-attachments/assets/d4b495f1-7b31-4136-b609-f8377e1a450b" />


---


# Conclusion

This project demonstrates the process of transforming raw e-commerce data into a structured analytical model using Power BI.

By implementing a **Star Schema**, the model becomes:

* Easier to understand
* Faster to query
* Scalable for future analytics

The resulting data model provides a strong foundation for building interactive dashboards and generating actionable insights related to sales performance, customer behavior, product trends, and marketing effectiveness.
