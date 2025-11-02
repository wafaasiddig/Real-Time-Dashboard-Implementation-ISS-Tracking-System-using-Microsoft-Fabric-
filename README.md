# Real-Time ISS Tracking System using Microsoft Fabric

## Project Overview
This project implements a comprehensive **real-time analytics dashboard** in Microsoft Fabric to track the International Space Station (ISS), transforming live telemetry data into actionable intelligence. By leveraging **Fabric's Real-Time Intelligence** capabilities, the system provides a live view of the ISS's location, velocity, and operational status with minimal latency.

<img width="1166" height="501" alt="Iss1" src="https://github.com/user-attachments/assets/afeabf23-46c0-412a-9c0f-9448830b886b" />


---

## Process Flow
The architecture follows an event-driven pipeline for continuous data ingestion and processing:

<img width="6000" height="3375" alt="Strategic Project Roadmaps Infographic Presentation (1)" src="https://github.com/user-attachments/assets/efaeab52-4173-4543-a04e-c046554934f5" />

---

## Technical Implementation Process

### Phase 1: Environment Configuration
I established the foundational infrastructure by creating a **Microsoft Fabric workspace** with **Real-Time Intelligence** capabilities. The environment was configured with the necessary access controls and capacity allocation to support continuous, event-driven data operations, forming a unified analytics platform for the entire solution.

A **KQL Database** was deployed as the central repository for structured ISS data, supporting scalable streaming ingestion and optimized querying performance. I also configured **Eventhouse** as the event processing layer and **Eventstream** as the real-time ingestion pipeline, connecting all components into a seamless analytical workflow.

### Phase 2: Data Engineering & Real-Time Ingestion
The core of this project was building a robust pipeline for live ISS data. Unlike static datasets, this required continuously fetching data from the **ISS positional API** and streaming it into Fabric.
<img width="1012" height="464" alt="image" src="https://github.com/user-attachments/assets/045c7463-af91-455b-aa75-669edfa7e2df" />

To achieve this, I developed a **Fabric Notebook** that acts as the automation engine. Using Python, the notebook executes a script every **two seconds** to:
- **Fetch live data** from the ISS API using the `requests` library.
- **Enrich the data** with precise timestamps for temporal analysis.
- **Stream the processed records** directly into **Eventstream**, enabling seamless real-time processing in Fabric.

This automated process ensures the dashboard reflects the most recent orbital data, creating a true real-time data pipeline inside Microsoft Fabric.

**Key Schema Design:**
- **datetime:** Precision timestamp for temporal analysis
- **latitude / longitude:** Geospatial coordinates for live tracking
- **altitude:** Orbital elevation metrics
- **velocity:** Speed measurement for motion analytics
- **visibility:** Operational visibility indicators

**Implementation Files:**
- `ISS Notebook(1).ipynb` - Python script for automated API data fetching and streaming to Eventstream

### Phase 3: Dashboard Development & Visualization
With data flowing through **Eventstream** into the **KQL Database**, I constructed an interactive **Real-Time Dashboard** to visualize the ISS's movement and key metrics. This provides an at-a-glance operational view for live monitoring.

**Dashboard Components Include:**
- **Real-time mapping** for ISS trajectory and geospatial positioning
- **Altitude and Velocity trend visualizations** for performance analytics
- **Operational status and visibility indicators**

The integration with **Power BI** (through DirectLake) and Fabric's **Real-Time Dashboards** provided both deep analytical depth and live monitoring interfaces from a single platform.

### Phase 4: Quality Assurance & Performance Tuning
Comprehensive validation was performed to ensure system accuracy and performance:
- Verified **continuous data ingestion** and event synchronization between the API, Eventstream, and KQL Database.
- Validated **real-time dashboard responsiveness** and data latency of under 10 seconds.
- Tested all parameter-driven user interactions and alerting mechanisms.

Performance tuning included optimizing **KQL queries** for efficiency, refining **database indexing**, and configuring the streaming pathways for maximum throughput.

---

## Technical Architecture

### Data Pipeline Specification
| Component | Specification | Purpose |
|------------|----------------|----------|
| **Update Frequency** | Continuous Stream (2-second intervals) | Live ISS position updates via Notebook automation |
| **Data Latency** | < 10 seconds end-to-end | Near real-time monitoring and decision-making |
| **Ingestion Method** | Eventstream with Notebook API Client | Real-time data ingestion pipeline |
---

## Conclusion
This solution successfully delivers a **real-time ISS tracking dashboard** leveraging the full power of Microsoft Fabric's analytics platform. By using a **Fabric Notebook**  to automate API data retrieval every two seconds, the system demonstrates how to build a continuous, real-time data pipeline from scratch.

The integration of **Eventstream**, **Eventhouse**, and **Real-Time Intelligence** transforms raw API data into a live operational intelligence system, complete with automated alerting and interactive analytics. This implementation stands as a **reference architecture** for streaming intelligence systems across **IoT, aerospace, and infrastructure monitoring** domains—showcasing how modern data platforms can transform live telemetry into immediate, actionable insights.
