<div align="center">

# 🌍 Trip Away : Travel Aggregator Analysis
<!-- Project Banner -->
<img src="assets/banner_travel_aggregator.png" alt="Travel Aggregator Banner" width="85%">
<br>
<!-- Skill Badges -->
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
<img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white">

<br>
<br>

<!-- Analysis Badges -->
<a href="#exploratory-data-analysis"><img src="https://img.shields.io/badge/Exploratory_Data_Analysis-4A90E2?style=for-the-badge"></a>
<a href="#key-findings"><img src="https://img.shields.io/badge/Insights-50C878?style=for-the-badge"></a>
<a href="#visualizations"><img src="https://img.shields.io/badge/Visualizations-F5A623?style=for-the-badge"></a>
<a href="#project-structure"><img src="https://img.shields.io/badge/Project_Structure-4A4A4A?style=for-the-badge"></a>

</div>

## 🎯 Project Aim
This project analyzes customer behavior, booking patterns, device usage, and platform performance for **Trip Away**, a multi‑service travel aggregator.  
The goal is to uncover actionable insights that improve user experience, optimize route planning, and strengthen platform performance.

### 📂 Project Structure
```
📁 Data_Analysis_Travel-Aggregator-Analysis
│── 📂 data                 # Dataset files
│── 📂 notebook             # Jupyter notebook for EDA
     │── 📜 business_impact.md          # 
│── 📜 business_impact.md          # 
│── 📜 README.md             # Project overview, structure, key findings, and visuals
│── 📜 requirements.txt      # Python dependencies for running the analysis

```
### 🛠 Installation & Setup
1. **Clone the repository**  
   ```bash
   git clone https://github.com/mcadriaans/Data_Analysis_Travel-Aggregator-Analysis.git
   cd Data_Analysis_Travel-Aggregator-Analysis
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```
## 📋 Data Overview
- **Time Span:** The analysis draws on data spanning a period of more than 3 years, 10 months, and 7 days.
- **Data Files:**

 `Bookings.csv` (Contains booking information)
| Column Name        | Description                                    |
|--------------------|------------------------------------------------|
| customer_id        | Unique identifier for customers                |
| booking_id         | Unique booking reference                       |
| from_city          | Origin city of the booking                     |
| from_country       | Origin country of the booking                  |
| to_city            | Destination city of the booking                |
| to_country         | Destination country of the booking             |
| booking_time       | Timestamp when the booking was made            |
| device_type_used   | Device type used for booking (e.g., Desktop, Android, iOS) |
| INR_Amount         | Booking cost in Indian Rupees (INR)            |
| service_name       | Platform used for booking (e.g., MMT, Goibibo, EaseMyTrip) |
| no_of_passengers   | Number of passengers in the booking            |
| days_to_departure  | Days left before departure at the time of booking |
| distance_km        | Distance covered in the booking                |

 `Sessions.csv` (Contains search session data)
| Column Name        | Description                                    |
|--------------------|------------------------------------------------|
| session_id         | Unique session identifier                      |
| search_id          | Unique search reference                        |
| search_time        | Timestamp when the search was conducted        |
| session_starting_time | Timestamp of when the session started       |
| booking_id         | Unique booking reference if a booking was made from the session (nullable) |


## 🔍 Key Findings

### 📊 Dataset Summary
- **339** unique bookings  
- **331** unique sessions  
- **1360** unique searches  
- **3 years, 10 months, 7 days** of activity

### 📅 Booking Behavior
- **Thursday** is the peak booking day (65 bookings)  
- **Weekend bookings:** 23.3% of total volume

### 🏷️ Service Performance
- **GOIBIBO** leads in bookings + revenue  
- **MMT** shows the lowest performance  
- **YATRA** maintains moderate, stable usage

### ✈️ Route Demand
- Most repeated route: **Gurgaon → Roissy-en-France**  
- Repeat travelers cluster around **Gurgaon** as a major origin hub

### ⏱️ Lead-Time Patterns
- Longest advance bookings from: **Gurgaon**, **Devanhalli**, **Mumbai**

### 📈 Correlation Insights
- Strongest correlation: **INR_Amount ↔ distance_km**  
- Passenger count moderately increases total fare

### 📱 Device Preferences
- GOIBIBO: strong iOS + desktop + Android usage  
- MMT: desktop‑heavy  
- YATRA: balanced Android + desktop

### 🗓️ Quarterly Trends
- Noticeable peak in early **2020** across multiple device types  
- Gradual decline afterward

For detailed business recommendations, see: 👉 `business_impact.md`

## 📈 Key Visualizations

Below are the core visual analyses included in the notebook:

- 📅 **Bookings by Weekday** — Pie chart showing Thursday as the peak booking day  
- 💰 **Bookings & Revenue by Service** — Dual‑axis bar chart comparing platform performance  
- ✈️ **Top Repeat‑Customer Routes** — Horizontal bar chart of high‑frequency travel corridors  
- ⏱️ **Lead‑Time Distribution by City** — Box plot showing advance booking behavior  
- 📉 **Price Sensitivity Curve** — Combined bar + line chart analyzing fare impact  
- 🔻 **Search → Booking Funnel** — Funnel chart showing a 76% abandonment rate  

📓 **Full visualizations available in the notebook:**  
👉 `notebook/travel_aggregator_analysis.ipynb`



## ❗ Conclusion:
The detailed analysis provided valuable insights into customer behavior, service performance, popular routes, advanced booking patterns, and device preferences. These insights can be leveraged to enhance customer experience, optimize resource allocation, and improve marketing strategies for "Trip Away."


