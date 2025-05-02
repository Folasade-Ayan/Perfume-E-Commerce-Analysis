# 🧴 Perfume Sales Analysis Using Excel and Power BI

## 📌 Overview

This project is a deep-dive analytical exploration into perfume sales using **Microsoft Excel** and **Power BI**. The objective is to uncover insights into customer preferences, pricing trends, and brand performance. This analysis answers specific business questions and supports data-driven decision-making through a combination of **descriptive statistics**, **correlation and regression modeling**, and **data visualization**.

The final deliverables include interactive charts, statistical outputs, and professional dashboards that translate raw data into business intelligence.

---

## 🎯 Research Questions

1. Which perfume brands have the highest total sales?  
2. What is the average price and total sales by product type?  
3. How do sales compare between male and female perfumes?  
4. Which locations have the highest number of units sold?  
5. Is there a relationship between price and sales volume?  
6. Which perfume brands have high sales but low availability?  
7. How do price, availability, category (male/female), and product type affect units sold?

---

## 🧾 Dataset Overview

| Column          | Description                                   |
|------------------|-----------------------------------------------|
| **Brand**        | Perfume brand name                            |
| **Category**     | Gender target (Male/Female)                   |
| **Type**         | Product type (e.g., Eau de Parfum, Cologne)   |
| **Price**        | Price per unit (numeric)                      |
| **Price Range**  | Binned price groups (e.g., $0–20, $21–40)     |
| **Available**    | Units in stock                                |
| **Sold**         | Units sold                                    |
| **Last Updated** | Last inventory update                         |
| **Location**     | Geographic location (cleaned to country)      |

Additional encoded columns were created for regression analysis:
- `New Category` (numerical representation of gender)
- `New New Type` (numerical representation of product type)

---

## 📊 Tools Used

- **Microsoft Excel**
  - Power Query for cleaning and transformation
  - Pivot Tables for summarizing insights
  - Charts: Bar, Column, Line, Pie, Scatter
  - Regression and Correlation (Data Analysis Toolpak)
  - Slicers for interactive filtering

- **Power BI**
  - Dynamic dashboards
  - Map for sales by location
  - Bar/column/Line/Scatter charts
  - Drill-down capabilities

---

## 🧭 Process

1. **Downloaded dataset** from Kaggle.  
2. **Imported into Power Query** for cleaning and transformation.  
3. **Data Cleaning** included:
   - Removed timestamps from the *Last Updated* column.
   - Cleaned text data from *Price* and *Available* columns.
   - Replaced nulls with zeros.
   - Standardized casing and spelling in *Brand* and *Product Type* columns.
   - Extracted countries from location fields.
4. Cleaned datasets were kept separate → linked via connections → merged into a final model.

### 📊 Analytical Methods & Findings

- **Q1: Top Brands by Sales**  
  - **Method**: Pivot table, bar chart, value filter (>10,000).  
  - **Finding**: Only 30 brands recorded over 10,000 in sales.

- **Q2: Product Type Pricing vs Sales**  
  - **Method**: Pivot table, column chart.  
  - **Finding**: *Eau de Parfum* and *Eau de Toilette* led in sales.

- **Q3: Gender-based Sales Comparison**  
  - **Method**: Pivot table, pie chart.  
  - **Finding**: *Female perfumes* sold more than *male perfumes*.

- **Q4: Location-wise Sales**  
  - **Method**: Pivot table, bar chart, Power BI Map.  
  - **Finding**: *United States* led in sales; *Estados Unidos* had none.

- **Q5: Price vs Sales Relationship**  
  - **Method**: Created price range column, pivot table, line chart.  
  - **Finding**: Price range **$21–40** had the highest sales, followed by **$0–20**.

- **Q6: Brands Needing Re-Stock**  
  - **Method**: Pivot table, column chart, filter (>10,000 units sold).  
  - **Finding**: Only a few brands were flagged for restocking.

- **Q7: Sales Drivers (Statistical Modeling)**  
  - **Method**: Regression & correlation analysis.  
  - **Findings**:
    - *Availability* and *Price* are significant predictors of sales.
    - Availability and Sales have a **positive correlation (r = 0.24)**.
    - Price and Sales have a **negative correlation (r = -0.13)**.

---

## 📉 Correlation Analysis Summary

|                   | New Category | New New Type | Price  | Available | Sold   |
|-------------------|--------------|--------------|--------|-----------|--------|
| **New Category**  | 1.000        |              |        |           |        |
| **New New Type**  | -0.025       | 1.000        |        |           |        |
| **Price**         | -0.079       | -0.032       | 1.000  |           |        |
| **Available**     | -0.013       | -0.021       | -0.116 | 1.000     |        |
| **Sold**          | 0.010        | 0.006        | -0.131 | 0.241     | 1.000  |

---

## 📈 Regression Analysis Summary

### Model Stats

| Metric            | Value     |
|-------------------|-----------|
| Multiple R        | 0.2624    |
| R Square          | 0.0688    |
| Adjusted R Square | 0.0668    |
| Standard Error    | 1396.74   |
| Observations      | 1882      |

### ANOVA Table

| Source     | df   | SS            | MS           | F      | Significance F |
|------------|------|----------------|--------------|--------|----------------|
| Regression | 4    | 270,680,699.4  | 67,670,174.8 | 34.69  | 5.62E-28       |
| Residual   | 1877 | 3,661,784,397  | 1,950,870.8  |        |                |
| Total      | 1881 | 3,932,465,096  |              |        |                |

### Coefficient Table

| Variable       | Coefficient | Std Error | t Stat | P-value   | 95% Confidence Interval    |
|----------------|-------------|-----------|--------|-----------|-----------------------------|
| Intercept      | 527.27      | 121.25    | 4.35   | 1.44E-05  | (289.47, 765.07)            |
| New Category   | 15.78       | 64.76     | 0.24   | 0.8075    | (-111.23, 142.79)           |
| New New Type   | 5.00        | 14.80     | 0.34   | 0.7355    | (-24.03, 34.03)             |
| Price          | -4.75       | 1.03      | -4.60  | 4.57E-06  | (-6.78, -2.73)              |
| Available      | 6.01        | 0.59      | 10.21  | 7.10E-24  | (4.86, 7.17)                |

---

## 📂 Resources

This section contains links to all visuals and supporting files used in this project.

### 📁 Excel and Power BI Visuals

> Click on the links below to view each visualization:

- [Question 1 – Sales Performance by Brand](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%201-%20Sales%20Performance%20by%20Brand.png)
- [Question 2 – Average Price and Sales of Product Types](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%202-%20Average%20Price%20and%20Sales%20of%20Product%20Types.png)
- [Question 3 – Sales Performance by Category](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%203-%20Sales%20Performance%20by%20Category.png)
- [Question 4 – Sales by Location](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%204-%20Sales%20by%20Location.png)
- [Question 5 – Price and Sales Performance](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%205-%20Price%20and%20Sales%20Performance.png)
- [Question 6 – Brands with High Sales and Low Stock](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%206-%20Brands%20with%20High%20Sales%20and%20Low%20Stock.png)
- [Question 7(i) – Collinearity of Regression Analysis](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%207(i)-%20Collinearity%20of%20Regression%20Analysis.png)
- [Question 7(ii) – Predicted and Actual Sales Performance](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Question%207(ii)-%20Predicted%20and%20Actual%20Sales%20Performance.png)
- [Power Bi Dashboard View](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/Excel%20and%20Power%20Bi%20Visuals/Power%20Bi%20Dashboard%20View.png)

---

### 📊 Excel Workbook

- [📥 My Project – Excel Workbook](https://github.com/Folasade-Ayan/Perfume-E-Commerce-Analysis/blob/main/My%20Project.xlsx?raw=true)

---

## 🗒️ Notes

- Excel dashboards utilized **slicers** for filtering and interactivity.
- Power BI dashboards were **dynamic** and used advanced visuals such as **maps** and **hierarchical filters**, but **did not include slicers**.
- All Power BI visuals are represented via **screenshots** in this repository.

---

## 📫 Contact Me

For questions, feedback, collaboration opportunities, or to connect professionally, feel free to reach out via:

- **GitHub**: [Folasade-Ayan](https://github.com/Folasade_Ayan)
- **Email**: alicefolasadeadeoye@gmail.com

I'm always open to meaningful discussions on data analysis, visualization, and business insights.

---

## 📌 Final Note

This project blends **data cleaning**, **descriptive statistics**, and **predictive modeling** with impactful **visual storytelling** through **Microsoft Excel** and **Power BI**. It demonstrates how data can inform business decisions—such as pricing strategy, inventory management, and market segmentation—by answering real-world commercial questions.

Although the interactive dashboards are not publicly hosted, the visuals shared offer clear representations of how insights were drawn. This case study underscores the importance of combining analytical rigor with intuitive visuals to support strategic decisions in product sales.

## 📁 Folder Structure

.
├── Excel and Power Bi Visuals/
│   ├── Question 1- Sales Performance by Brand.png
│   ├── Question 2- Average Price and Sales of Product Types.png
│   ├── Question 3- Sales Performance by Category.png
│   ├── Question 4- Sales by Location.png
│   ├── Question 5- Price and Sales Performance.png
│   ├── Question 6- Brands with High Sales and Low Stock.png
│   ├── Question 7(i)- Collinearity of Correlation Analysis.png
│   ├── Question 7(ii)- Predicted and Actual Sales Performance.png
│   └── Power Bi Dashboard View.png
├── My Project.xlsx
├── README.md
