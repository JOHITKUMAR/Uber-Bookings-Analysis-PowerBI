# Uber-Bookings-Analysis-PowerBI
Interactive Power BI dashboard analyzing Uber ride bookings, revenue, distance, and customer cancellations across vehicle types (Auto, Uber XL, Go Mini &amp; more).

# 🚖 Uber Bookings Analysis — Power BI Dashboard

An interactive Power BI dashboard analyzing Uber ride bookings, revenue, distance traveled, and customer behavior across multiple vehicle types (Auto, Uber XL, Go Mini, and more), built to surface operational and customer experience insights from raw trip-level data.

---

## Project Objective

Ride-hailing platforms generate massive volumes of trip-level data every day — bookings, cancellations, distances, ratings, and revenue, all split across vehicle types and locations. On its own, this data is just rows; the goal of this project is to turn it into a clear operational picture: how many bookings are completing successfully, where revenue is concentrated, how distance and demand trend over time, and why customers cancel.

This project sets out to:

- Consolidate trip-level booking data into a single interactive Power BI report.
- Track completed, canceled, and incomplete bookings across vehicle types.
- Quantify revenue and distance performance by vehicle type, month, and quarter.
- Surface customer satisfaction trends through ratings analysis.
- Identify the root causes behind cancelled rides (driver-side and customer-side).
- Deliver a navigable, multi-page report for both an overview and vehicle-specific drill-downs.

---

## Table of Contents

- [Dashboard Pages](#dashboard-pages)
- [Key Metrics](#key-metrics)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Tools and Technologies](#tools-and-technologies)
- [Getting Started](#getting-started)

---

## Dashboard Pages

The report is structured across four pages, each serving a distinct purpose.

### 1. Home
A landing page introducing the platform — what Uber is, what services it offers (ride-hailing, food delivery, logistics), and navigation buttons to the three analytical pages: **Overview**, **Distance/Month and Quarter**, and **Customer Related**.

### 2. Overview
A vehicle-type-specific snapshot (e.g., **Auto**) showing the core booking funnel and revenue picture:

- **Complete Bookings**, **Lost Bookings**, **Revenue**, **Total Distance**, and **Average Distance** as headline KPI cards
- **Completed / Canceled / Incomplete** booking status breakdown via donut charts
- **Complete Bookings by Month** trend (toggle between Month and Quarter view)
- **Revenue by Vehicle Type** bar chart
- Top **Pickup** and **Drop Location** cards with their respective completed booking counts
- **Average Customer Rating** and **Average Driver Rating** cards

### 3. Distance/Month and Quarter
A deep-dive into trip distance, viewable per vehicle type (e.g., **Uber XL**):

- KPI cards for Complete Bookings, Lost Bookings, Revenue, Total Distance, and Average Distance
- **Total Distance by Customer ID** — ranks the highest-distance customers
- **Total Distance by Quarter** trend line
- **Total Distance by Vehicle Type** bar chart
- A detailed **Pickup Location → Drop Location → Total Distance** table with a running total

### 4. Customer Related
Focused on cancellations and customer experience (e.g., **Go Mini**):

- KPI cards for Complete Bookings, Lost Bookings, Revenue, Total Distance, Average Distance
- Completed / Canceled / Incomplete donut breakdown
- A detailed table per **Customer ID** showing **Sum of Customer Rating**, **Count of Cancelled Rides by Driver**, **Count of Cancelled Rides by Customer**, **Driver Cancellation Reason**, and **Reason for Cancelling by Customer**
- Totals row aggregating rating sums and cancellation counts across all customers

All pages share a consistent **vehicle-type selector** (Auto, Bike, regular car, Uber XL, Go Mini, etc.) along the left rail, letting users filter the entire page by ride type with a single click.

---

## Dataset Structure

Based on the fields and breakdowns visible across the dashboard, the underlying booking dataset appears to include the following columns:

| Column | Description |
|---|---|
| **Booking ID** | Unique identifier for each ride booking |
| **Customer ID** | Unique identifier for each customer (e.g., C4977170, C1000434) |
| **Vehicle Type** | Ride category — Auto, Uber XL, Go Mini, Bike, regular car, etc. |
| **Booking Date / Month / Quarter** | Date fields used to drive the Month and Quarter trend views |
| **Pickup Location** | Starting point of the trip (e.g., Azadpur, Badarpur) |
| **Drop Location** | Destination of the trip (e.g., Adarsh Nagar, New Colony) |
| **Booking Status** | Completed, Canceled, or Incomplete |
| **Distance** | Trip distance, aggregated into Total Distance and Average Distance |
| **Revenue** | Fare/revenue generated per completed booking |
| **Customer Rating** | Rating given by the customer for the trip |
| **Driver Rating** | Rating given to the driver for the trip |
| **Cancelled by Driver (flag/count)** | Indicates whether the driver cancelled the ride |
| **Driver Cancellation Reason** | Free-text reason logged when a driver cancels (e.g., "More than permitted people in there", "Personal & Car related issues") |
| **Cancelled by Customer (flag/count)** | Indicates whether the customer cancelled the ride |
| **Reason for Cancelling by Customer** | Free-text reason logged when a customer cancels |

This structure supports all four dashboard pages: status-based donut breakdowns (Booking Status), revenue/distance trends (Revenue, Distance, Date), location-pair analysis (Pickup/Drop Location), and the customer experience drill-down (Ratings, Cancellation Reasons).

> Note: exact column names may differ slightly in the source file; the table above reflects the fields inferable from the report's visuals.

### Sample Data

A representative sample of rows reconstructed from values visible in the dashboard tables (Distance and Customer Related pages):

**Trip / Distance records**

| Customer ID | Vehicle Type | Pickup Location | Drop Location | Total Distance |
|---|---|---|---|---|
| C4977170 | Uber XL | — | — | 82 |
| C9273981 | Uber XL | — | — | 50 |
| C6530241 | Uber XL | — | — | 50 |
| — | Uber XL | Azadpur | Adarsh Nagar | 41 |
| — | Uber XL | Badshahpur | Adarsh Nagar | 45 |
| — | Uber XL | Botanical Garden | Adarsh Nagar | 59 |
| — | Uber XL | Central Secretariat | Adarsh Nagar | 20 |
| — | Uber XL | Chhatarpur | Adarsh Nagar | 31 |
| — | Uber XL | Greater Noida | Adarsh Nagar | 10 |
| — | Uber XL | Huda City Centre | Adarsh Nagar | 27 |
| — | Uber XL | IFFCO Chowk | Adarsh Nagar | 33 |
| — | Uber XL | Kadarpur | Adarsh Nagar | 26 |
| **Total** | | | | **74,307** |

**Customer ratings & cancellations**

| Customer ID | Customer Rating | Cancelled by Driver | Cancelled by Customer | Driver Cancellation Reason |
|---|---|---|---|---|
| C1000434 | — | 1 | — | More than permitted people in there |
| C1000448 | 4.30 | — | 1 | — |
| C1000804 | 4.60 | — | 1 | — |
| C1000862 | 8.00 | — | 1 | — |
| C1000930 | — | 1 | — | More than permitted people in there |
| C1000949 | 4.90 | — | 1 | — |
| C1000971 | — | 1 | — | Personal & Car related issues |
| C1001022 | — | — | 1 | — |
| C1001250 | 4.60 | — | 1 | — |
| C1001625 | 5.00 | — | 1 | — |
| **Total** | **81,695.30** (sum) | **5,330** | **2** | — |

> These tables are a small illustrative sample pulled from the dashboard's visible rows, not the full dataset. Replace with the actual source `.xlsx`/`.csv` once available for exact figures.

---

## Key Metrics

| Vehicle Type | Complete Bookings | Lost Bookings | Revenue | Total Distance | Avg. Distance |
|---|---|---|---|---|---|
| **Auto** | 23K | 14K | 12.88M | 626K | 24.62 |
| **Uber XL** | 3K | 2K | 1.53M | 74K | 24.40 |
| **Go Mini** | 19K | 11K | 10.34M | 501K | 24.61 |

> Note: figures above reflect the per-vehicle-type filter selected on each respective dashboard page, not platform-wide totals.

---

## Insights

- **Auto dominates booking volume and revenue.** With 23K completed bookings and 12.88M in revenue, Auto is the highest-volume and highest-revenue vehicle category by a wide margin compared to Uber XL and Go Mini.
- **Lost bookings are a significant share of demand.** Across vehicle types, lost (cancelled/incomplete) bookings consistently represent a substantial fraction of total demand — for Auto alone, 14K lost bookings against 23K completed signals meaningful unmet or abandoned demand.
- **Average trip distance is remarkably consistent across vehicle types** (~24.4–24.6 distance units), suggesting customer trip patterns don't vary much by the vehicle they choose — the choice is more about price/comfort than trip length.
- **A small set of customers drive disproportionate distance.** In the Uber XL view, one customer (C4977170) logged 82 distance units while most others cluster around 50, hinting at a handful of power users or longer-haul use cases.
- **Cancellations have identifiable root causes.** The Customer Related page captures specific reasons — such as "More than permitted people in there" and "Personal & Car related issues" — giving the business concrete levers to address before they recur.
- **Revenue scales with completed bookings but distance efficiency varies.** Comparing Auto (23K bookings / 626K distance) to Go Mini (19K bookings / 501K distance) shows broadly proportional scaling, useful for capacity planning.

---

## Recommendations

- **Investigate the lost-bookings gap, starting with Auto.** With roughly 1 lost booking for every 1.6 completed bookings, understanding *why* rides are lost (driver availability, cancellation timing, pricing) could unlock significant additional completed revenue.
- **Standardize cancellation-reason capture.** Several cancellation records have no reason logged; enforcing reason capture at the point of cancellation would make root-cause analysis on this page far more actionable.
- **Use the location tables to optimize driver positioning.** The Pickup → Drop distance table can guide where to pre-position drivers ahead of predictable demand corridors.
- **Monitor high-distance customers as a distinct segment.** Customers with consistently above-average trip distances may represent a different need (e.g., intercity, business travel) worth a tailored pricing or loyalty approach.
- **Track ratings alongside cancellations.** Pairing the Average Driver/Customer Rating cards with cancellation reasons can help identify whether specific drivers or routes correlate with lower satisfaction.

---

## Tools and Technologies

- **Microsoft Power BI** — dashboard design, DAX measures, and interactive filtering
- **Power Query (M)** — data extraction and transformation
- **DAX** — KPI cards, donut chart calculations, and time-based aggregations (Month/Quarter toggle)

---

## Getting Started

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
2. Clone or download this repository.
3. Open the `.pbix` report file in Power BI Desktop.
4. Use the **vehicle-type selector** on the left rail to filter each page, and the **Month/Quarter toggle** on relevant visuals to change the time granularity.

---

*If you find this project useful, consider starring the repository.*
