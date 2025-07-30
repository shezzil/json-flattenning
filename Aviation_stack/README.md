# ✈️ AviationStack JSON API Flattening Project

## 🚀 Overview

This project demonstrates how to **consume real-time flight data from the AviationStack API** and transform complex, nested JSON structures into clean, flat, and analysis-ready data tables using Python and pandas. It’s built for clarity, modularity, and reusability—ideal for data analytics, reporting, or integration into a data lake or BI tool.

> 🔥 Designed to showcase practical **data wrangling skills** and real-world **API flattening logic** — the kind hiring managers love to see.

---

## 📦 Project Structure

This project extracts and flattens four key data layers:

| Table            | Description                                       |
|------------------|---------------------------------------------------|
| `flights_data`   | Core flight-level info (number, date, status, delays) |
| `timezone_data`  | Scheduled, estimated, and actual timestamps for arrivals/departures |
| `airline_data`   | Unique airline codes and names                    |
| `airport_data`   | Departure airport metadata (name, IATA, ICAO, timezone) |

Each table is transformed into a **deduplicated and normalized DataFrame**, ready for export or downstream integration.

---

## 🛠️ Technologies Used

- **Python 3.10+**
- `requests` – Fetches real-time flight data from AviationStack API  
- `pandas` – Handles JSON flattening and DataFrame creation

---

## 🧠 Skills Demonstrated

✅ Real-time API integration  
✅ JSON parsing and flattening from deeply nested structures  
✅ Defensive coding with `.get()` for null-safe access  
✅ Data normalization and deduplication  
✅ Structuring datasets for analytics and reporting

---

## 📊 Output Tables Preview

### ✈️ Flights Table
| flight_number | flight_date | status    | delay_minute |
|---------------|-------------|-----------|--------------|
| 726           | 2025-07-28  | scheduled | NaN          |

### 🕒 Timezone Table
| flight_iata | dep_scheduled     | arr_scheduled     |
|-------------|-------------------|-------------------|
| sq726       | 2025-07-28T14:40  | 2025-07-28T17:00  |

### 🏢 Airport Table
| airport_name | iata | icao | time_zone     |
|--------------|------|------|---------------|
| Yiwu         | YIW  | ZSYW | Asia/Shanghai |

### 🏷 Airline Table
| airline_name        | iata | icao |
|---------------------|------|------|
| Singapore Airlines  | SQ   | SIA  |

---

##  How to Run

1. Clone the repository  
2. Install dependencies:  
   ```bash
   pip install requests pandas
   ```
3. Replace your `access_key` from [aviationstack.com](https://aviationstack.com/)  
4. Run the script to generate structured tables

---

##  Use Cases

-  Flight delay prediction  
-  Real-time airline analytics  
-  Building a data mart for aviation KPIs  
-  Cross-timezone performance reporting

---

##  Next Steps (Optional Ideas)

- Export cleaned tables to CSV or Parquet  
- Load into S3, PostgreSQL, or Snowflake  
- Build dashboards in Power BI or Tableau

---


