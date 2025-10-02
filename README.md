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

---

### 2. Airline Performance Dashboard  

![airline performance](https://github.com/user-attachments/assets/7050704a-fa16-4d29-8159-c9495aee6d00)


- **Questions Answered:**  
  - Which airlines have the highest average delay?  
  - What are the main delay causes per airline?  
  - How does on-time performance vary through the year?  

- **Insights:**  
  - Worst performers: **JetBlue, Mesa Airways, ExpressJet**.  
  - Delay causes are dominated by **carrier-related issues**.  
  - On-time performance is better in **spring and fall**.  

- **Recommendations:**  
  - Airlines must prioritize **operational improvements**.  
  - Focus on maintenance, staffing, and fleet readiness.  


### 3. Airport Performance Dashboard

![airport_performance](https://github.com/user-attachments/assets/a7b4f845-489b-450c-a79f-e815ac8b0e3f)



- **Questions Answered:**  
  - Which airports face the worst delays?  
  - How do delays vary by time of day?  
  - Which airports have the most delayed flights?  

- **Insights:**  
  - Highest average delays: **Houghton County, Atlantic City International**.  
  - Delay peak hours: **4 PM – 8 PM**.  
  - Top delay locations: **ATL, ORD, DFW** (busiest hubs).  

- **Recommendations:**  
  - Airports should optimize **slot allocation** in peak hours.  
  - Enhance **traffic flow management** to reduce cascading delays.  

---

## 🚀 Tools & Technologies  
- **Power BI** – Interactive dashboards and data visualization.  
- **Excel/Pandas** – Data cleaning and preprocessing.  
