# Real-Time-Dashboard-Implementation-ISS-Tracking-System-using-Microsoft-Fabric-

## Project Overview ##
This project creates a real-time dashboard in Microsoft Fabric to track the International Space Station (ISS) location and movement using live data streams.  

<img width="1166" height="501" alt="image" src="https://github.com/user-attachments/assets/f67ca220-404f-4119-ba3e-7f769e144b38" />

---

## Process Flow ##
<img width="778" height="417" alt="image" src="https://github.com/user-attachments/assets/68dcc34e-e5ce-483f-b9d4-29e896ca8acf" />

---

## Technical Implementation Process ##

### Phase 1: Environment Configuration ###
I established the foundational infrastructure by creating a **Microsoft Fabric workspace** with Real-Time Intelligence capabilities.  
The environment was configured with the necessary access controls, workspace permissions, and capacity allocation to support continuous event-driven data operations.

A **KQL Database** was deployed as the central repository for structured ISS data, supporting scalable streaming ingestion and optimized querying performance.  
I also configured **Eventhouse** as the event processing layer, connecting downstream components to real-time analytical pipelines.

---

### Phase 2: Data Engineering ###
The live ISS data pipeline was developed by integrating the **ISS positional API** directly into the Microsoft Fabric environment.

Key schema design included the following core fields:

- **datetime:** Precision timestamp for temporal analysis  
- **latitude / longitude:** Geospatial coordinates for live tracking  
- **altitude:** Orbital elevation metrics  
- **velocity:** Speed measurement for motion analytics  
- **visibility:** Operational visibility indicators  

Data ingestion was implemented through **Eventstream**, ensuring low-latency transmission from the source API to the Eventhouse and KQL Database.  
This process enabled near real-time synchronization between the ISS data feed and analytical queries.

To retrieve the data from the ISS API, I developed a **Python script** within a Microsoft Fabric **Notebook** that executes every **two seconds**, fetching live positional data and streaming it directly into the **Eventstream** pipeline for real-time ingestion.  
This ensured that the dashboard always reflected the most recent orbital data with minimal latency.

### Dashboard Components Include ###

- **Altitude trend visualization**  
- **Velocity trend analytics**  
- **Real-time mapping for ISS trajectory**  
- **Operational status and visibility indicators**  

Integration with **Power BI** and **Real-Time Dashboards** provided both analytical depth and live monitoring interfaces.

---

### Phase 4: Advanced Features ###

To improve interactivity, I implemented **parameter-driven filtering** and **dynamic time range controls**, allowing users to adjust temporal granularity of real-time data views.

Using **Reflex**, I configured live response triggers for immediate event feedback.  
Additionally, **Data Activator** was integrated to automate alerting based on velocity thresholds, altitude variations, or visibility changes.

---

### Phase 5: Quality Assurance ###

Comprehensive validation was performed to ensure system accuracy and performance:

- Verified continuous data ingestion and event synchronization  
- Validated real-time dashboard responsiveness  
- Tested parameter-driven user interactions  
- Benchmarked query latency under load conditions  

Performance tuning included optimizing **KQL queries**, refining **database indexing**, and configuring **efficient streaming pathways**.

---

## Technical Architecture ##

### Data Schema Design ###
| Component | Specification | Purpose |
|------------|----------------|----------|
| Data Latency | < 10 seconds | Near real-time monitoring |
| Availability | 99%+ SLA | Operational reliability |
| Update Frequency | Continuous Stream | Live ISS position updates |
| Data Retention | Configurable Policies | Historical and trend analysis |

---

## Visualization Components ##

**Operational Dashboard**
- Real-time geospatial positioning  
- Velocity and altitude performance tracking  
- Trend and pattern analytics  
- Visibility and operational status  

**User Interface Elements**
- Interactive parameter filters  
- Real-time refresh indicators  
- Live data validation  
- Automated alert displays  

---

## Conclusion ##

This solution successfully delivers a **real-time ISS tracking dashboard** leveraging Microsoft Fabric’s **Eventstream**, **Eventhouse**, and **Real-Time Intelligence** architecture.  
The system provides instant situational insights with automated alerting, analytical depth, and extensible design for other real-time use cases.

The integration of a **Python-based API data retrieval system** ensures a continuous two-second update interval, providing ultra-low latency for live space tracking.

This implementation stands as a **reference architecture** for streaming intelligence systems across **IoT, aerospace, and infrastructure monitoring** domains — showcasing how modern data platforms can transform live telemetry into actionable intelligence.
