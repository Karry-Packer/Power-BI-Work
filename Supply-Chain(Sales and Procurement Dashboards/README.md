# 🚀 Smart Supply Chain MIS Dashboard

### 📊 Power BI Project | Inventory, Procurement, Sales & Logistics Analytics

---

## 📁 Overview

The **Smart Supply Chain MIS Dashboard** is a full-scale business intelligence solution designed in **Power BI** to centralize and visualize supply chain operations — from inventory and procurement to sales and logistics. This project showcases how real-time data can be transformed into meaningful KPIs and actionable insights that support decision-making and reduce operational inefficiencies.

---

## 🎯 Objectives

- Build an interactive and real-time dashboard for supply chain performance tracking
- Integrate procurement, sales, inventory, and logistics into one reporting view
- Forecast demand and highlight inventory risks using threshold indicators
- Automate manual reporting processes with a user-centric interface

---

## 🛠 Tech Stack

| Tool        | Purpose                                    |
|-------------|--------------------------------------------|
| Power BI    | Dashboard creation & visualization         |
| Power Query | Data transformation and modeling           |
| DAX         | Custom measures, KPIs, and calculations    |
| SQL         | Backend modeling and data handling (optional) |
| Excel/CSV   | Simulated supply chain data files          |
| Python      | (Optional) For advanced forecasting        |

---

## 🧩 Data Model (Star Schema)

- **Fact Tables**
  - `sales`: daily item-wise sales data
  - `procurement`: item-wise purchasing details
  - `logistics`: shipment data with status
- **Dimension Tables**
  - `inventory`: product master data with stock and reorder level
  - `vendors`: supplier details
  - `date`: calendar table for time-based aggregation

---

## 📊 Dashboard Highlights

- 💡 **KPIs**: Sales, Procurement, Inventory Turnover, On-Time Deliveries, Reorder Alerts
- 📅 **Slicers**: Date, Category, Vendor, Status
- 📈 **Visuals**:
  - Sales and procurement trends
  - Inventory levels vs reorder threshold
  - Vendor performance matrix
  - Shipment delivery breakdown (delivered/in transit/delayed)
  - Dynamic reorder alert table

---

## 📐 Key DAX Measures

```dax
Total Sales = SUM(sales[Quantity_Sold])

Total Procured = SUM(procurement[Quantity])

Reorder Alert Count = 
CALCULATE(
    COUNTROWS(inventory),
    inventory[Quantity] < inventory[Reorder_Level]
)

On-Time Delivery % = 
DIVIDE(
    CALCULATE(COUNTROWS(logistics), logistics[Status] = "Delivered"),
    COUNTROWS(logistics)
)
