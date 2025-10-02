# ✈️ Airflights Analysis Project  

## 📌 Project Goal  
The goal of this project is to analyze U.S. flight delay data to uncover key insights about airline and airport performance, identify delay patterns, and recommend improvements for better operational efficiency and customer satisfaction.  


https://github.com/user-attachments/assets/0a162724-1c7f-4739-b03e-1965bf983bc6



## 🛠 Project Steps  

1. **Define the Goal**  
   - Understand the dataset and determine the main business questions (delays, causes, performance by airline/airport, seasonal patterns).  

2. **Data Quality Check & Cleaning**  
   - Handle missing values, duplicates, and incorrect data types.  
   - Improve data quality by validating categorical fields (airlines, airports, delay reasons).  

3. **Data Modeling**  
   - Create **DimDate** and **DimTime** tables to enable time-based analysis.  
   - Build a **Star Schema** for efficient querying and dashboard performance.  
   - Structure:  
     - **FactFlights** (delays, cancellations, times, measures)  
     - **DimAirline** (airline details)  
     - **DimAirport** (airport details)  
     - **DimDate / DimTime** (time intelligence)  
![data modeling airflights](https://github.com/user-attachments/assets/caffd7e7-473e-4dbd-b385-58bf1009cb99)


4. **Measures Table**  
   A separate **Measures Table** was created to centralize KPIs used in analysis. Examples:  
   - `Total Flights = COUNTROWS(FactFlights)`  
   - `Total Delays = COUNTROWS(FILTER(FactFlights, FactFlights[DelayMinutes] > 0))`  
   - `Avg Arrival Delay = AVERAGE(FactFlights[ArrivalDelayMinutes])`  
   - `On-Time % = DIVIDE([On-Time Flights], [Total Flights], 0)`  
   - `Total Delay Minutes = SUM(FactFlights[DelayMinutes])`
  
   
     ![measures](https://github.com/user-attachments/assets/03b576a3-4b69-4f56-9e48-00b386562d74)




6. **Visualization & Dashboards**  
   - Built interactive dashboards in **Power BI** to answer key business questions.  
   - Designed Overview, Airline Performance, and Airport Performance dashboards.  



## 📊 Dashboards & Key Insights  




### 1. Overview Dashboard 


![overview airflights](https://github.com/user-attachments/assets/e540e470-d130-4174-b5d6-6b11e43ebc11)



- **Questions Answered:**  
  - What is the total number of delayed flights and total delay time?  
  - What are the main reasons for flight delays?  
  - Which airlines and regions have the most delays?  

- **Insights:**  
  - Total delays: **82M minutes** across **2M flights**.  
  - Top reason: **Carrier-related issues (~50%)**.  
  - Worst airline: **Southwest Airlines**.  
  - Hotspots: **Texas, California, Illinois**.  
  - Seasonal peak: **Summer (July-August)** and **December**.  

- **Recommendations:**  
  - Airlines should improve internal operations and scheduling.  
  - Airports in hotspot regions need better capacity planning during peak months.  

### 2. Airline Performance Dashboard  

![airline performance](https://github.com/user-attachments/assets/7050704a-fa16-4d29-8159-c9495aee6d00)


- **Key Features:**  
  - Track the **performance of each carrier** using slicers (filter by airline).  
  - **Breakdown of delay reasons** per airline (carrier, weather, NAS, late aircraft, security).  
  - Monitor **arrival delay % trend by month** to capture seasonal and operational changes.  
  - Explore **flight-level details** for each airline to identify problem routes or times.  
  - Calculate **average arrival delay** per airline to compare punctuality across carriers.  

- **Insights:**  
  - **JetBlue Airways** records the highest average arrival delay, followed by **Mesa Airways** and **ExpressJet Airlines**.  
  - **Carrier-related issues** remain the primary cause of delays across most airlines, emphasizing internal operational inefficiencies.  
  - Arrival delay percentages spike during **summer months (July–August)** and **December**, reflecting high travel demand and system congestion.  
  - Airlines with stronger operational planning (e.g., **Alaska Airlines**) show more stable on-time performance across the year.  
  - Flight-level details reveal that delays are not uniform — certain **routes and peak-time flights** contribute disproportionately to overall delays.  

- **Recommendations:**  
  - Airlines should invest in **route-level optimization** to reduce delays in high-risk corridors.  
  - Apply **seasonal staffing and scheduling strategies** during summer and year-end peaks.  
  - Improve **carrier operations** through better maintenance, crew scheduling, and turnaround time management.  


### 3. Airport Performance Dashboard

![airport_performance](https://github.com/user-attachments/assets/a7b4f845-489b-450c-a79f-e815ac8b0e3f)



- **Key Features:**  
  - Track the **performance of each airport** using slicers (filter by airport).  
  - Monitor the **average arrival delay by hour** to understand time-of-day patterns.  
  - Highlight airports with the **highest percentage of flights not arriving on time**.  
  - Compare **average departure delay vs. average arrival delay** to capture cascading effects.  
  - **Breakdown of delay reasons** per airport to identify local challenges (carrier, weather, NAS, late aircraft, security).  

- **Insights:**  
  - **Houghton County Memorial (CMX)** and **Atlantic City International (ACY)** have the highest average arrival delays, making them top problem airports.  
  - Delays peak between **16:00–20:00 (late afternoon to evening)**, mainly due to traffic congestion and spillover from earlier delays.  
  - Major hubs like **Atlanta (ATL)**, **Chicago O'Hare (ORD)**, and **Dallas/Fort Worth (DFW)** show the **highest number of delayed flights**, consistent with their heavy traffic load.  
  - On-time performance varies significantly across airports, with some regional airports struggling to maintain punctuality.  
  - In many airports, **departure delays strongly correlate with arrival delays**, showing how early disruptions cascade throughout the day.  

- **Recommendations:**  
  - Focus on **congestion management** in peak hours (16:00–20:00) through better scheduling and slot allocation.  
  - Airports with **persistent delay causes (e.g., weather or carrier issues)** should coordinate closely with airlines for mitigation strategies.  
  - Major hubs (ATL, ORD, DFW) should invest in **real-time monitoring systems** to reduce cascading effects and improve turnaround efficiency.  
  - Regional airports with high delay ratios should implement **localized operational improvements**, such as better ground handling and staffing.
---

## 🚀 Tools & Technologies  
- **Power BI** – Interactive dashboards and data visualization.  
- **Excel/Pandas** – Data cleaning and preprocessing.  
