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
<a href="#-project-aim"><img src="https://img.shields.io/badge/Exploratory_Data_Analysis-4A90E2?style=for-the-badge"></a>
<a href="#-key-findings"><img src="https://img.shields.io/badge/Insights-50C878?style=for-the-badge"></a>
<a href="#-key-visualizations"><img src="https://img.shields.io/badge/Visualizations-F5A623?style=for-the-badge"></a>
<a href="#-project-structure"><img src="https://img.shields.io/badge/Project_Structure-4A4A4A?style=for-the-badge"></a>

</div>

## 🎯 Project Aim
Trip Away is a multi-service travel aggregator, and this project digs into how its customers actually search, book, and behave across the platform. The aim was to understand booking patterns, device habits, and route demand well enough to point to real, usable improvements in user experience, route planning, and overall platform performance.

### 📂 Project Structure
```
📁 Data_Analysis_Travel-Aggregator-Analysis
│── 📂 assets            
     │── banner_travel_aggregator.png        
│── 📂 data                                          # Dataset files
│── 📂 notebook             
     │── 📜 travel_aggregator_analysis.ipynb        # Complete exploratory analysis, visuals, and insights
│── 📜 business_impact.md                           # Consolidated business insights & strategic recommendations 
│── 📜 README.md                                    # Project overview, structure, key findings, and visuals
│── 📜 requirements.txt                             # Python dependencies for running the analysis

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

 `bookings.csv` (Contains booking information)
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

 `sessions.csv` (Contains search session data)
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
- **1,360** unique searches  
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
- Cities with the longest **typical** lead times: **New Delhi**, **Bālāpur**, **Madhyamgram**  
- A handful of individual bookings from Gurgaon, Devanhalli, and Mumbai were made 200+ days out, but those are outliers — most customers from those cities still book close to departure

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

### 🔻 Search-to-Booking Funnel
- Out of **1,360** distinct searches, only **338** ended in a completed booking  
- That's a **75% abandonment rate** — people are searching, they're just not finishing

For detailed business recommendations, see: 👉 [business_impact.md](business_impact.md)

## 📈 Key Visualizations

Here's what's covered visually in the notebook:

- 📅 **Bookings by Weekday** — Pie chart showing Thursday as the peak booking day  
- 💰 **Bookings & Revenue by Service** — Dual‑axis bar chart comparing platform performance  
- ✈️ **Top Repeat‑Customer Routes** — Horizontal bar chart of high‑frequency travel corridors  
- ⏱️ **Lead‑Time Distribution by City** — Box plot showing advance booking behavior  
- 📉 **Price Sensitivity Curve** — Combined bar + line chart analyzing fare impact  
- 🔻 **Search → Booking Funnel** — Funnel chart showing a 75% abandonment rate  

📓 **Full visualizations available in the notebook:**  
👉 [notebook/travel_aggregator_analysis.ipynb](notebook/travel_aggregator_analysis.ipynb)

## 🧩 Challenges

A couple of things came up while building this that are worth mentioning:

- **Plotly charts wouldn't display on GitHub.** The interactive charts (the monthly oBSR trend line and the search-to-booking funnel) rendered fine in Colab, but showed up blank once pushed to GitHub. This turned out to be because Plotly's interactive charts rely on JavaScript to render, and GitHub's notebook viewer won't execute embedded JavaScript for security reasons. The fix was installing **Kaleido**, a package that lets Plotly export a chart as a plain static PNG instead of an interactive widget — so the charts you see in this repo are static images generated with Kaleido, while the notebook still produces the interactive versions when run directly in Colab or Jupyter.
- **Getting consistent "top city" rankings meant checking more than just the extremes.** A couple of early findings, including the original lead-time ranking, were based on the individual bookings with the highest values rather than each city's typical behavior. Grouping by city and comparing medians instead gave a more accurate picture, and the write-up above reflects that correction.

## ❗ Conclusion
This analysis gives Trip Away a clearer picture of who's booking, when, from where, and on what device, along with a good look at where the platform is losing people between a search and a completed booking. The findings here are meant to feed directly into pricing, marketing, and route-planning decisions — the specifics are laid out in `business_impact.md`.
