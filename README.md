
## 📊 Data Architecture

### Medallion Architecture Implementation
- **🥉 Bronze Layer**: Raw JSON data ingestion from Event Hub to ADLS
- **🥈 Silver Layer**: Cleaned, validated, and enriched data with schema enforcement
- **🥇 Gold Layer**: Business-ready aggregated data optimized for analytics

### Star Schema Design (Synapse SQL Pool)

**Fact Table:**
- `FactPatientFlow` - Patient visits, timestamps, wait times, discharge status

**Dimension Tables:**
- `DimDepartment` - Hospital department details and metadata
- `DimPatient` - Patient demographic and profile information  
- `DimTime` - Comprehensive time dimension for temporal analysis

## 🚀 Implementation Guide

### Phase 1: Infrastructure Setup
1. **Azure Event Hub** - Configure namespace and patient-flow event hub
2. **Azure Data Lake Storage** - Set up bronze, silver, gold containers
3. **Azure Databricks** - Configure workspace and cluster
4. **Azure Synapse Analytics** - Provision SQL Pool

### Phase 2: Data Simulation & Ingestion
- **Real-time Data Generator**: Patient flow generator script
- Simulates patient admissions, department transfers, and discharge events
- Streams synthetic data to Event Hub for processing

### Phase 3: ETL Processing (Databricks)

| Notebook | Purpose | Key Operations |
|----------|---------|----------------|
| **01_bronze_rawdata** | Raw ingestion | Stream from Event Hub, write to Delta |
| **02_silver_cleandata** | Data quality | Schema validation, null handling, type casting |
| **03_gold_transform** | Business logic | Aggregations, star schema preparation |

### Phase 4: Data Warehouse & Analytics
- **Schema Creation**: Execute DDL scripts for table creation
- **Data Loading**: Populate fact and dimension tables
- **Performance Optimization**: Distribution strategies and indexing

## 📈 Analytics & Visualization

### Power BI Dashboard Features

**Key Performance Indicators:**
- 📊 **Bed Occupancy Rate** by department and gender
- ⏱️ **Average Wait Times** across emergency and critical care
- 🏥 **Department Utilization** and patient distribution
- 📅 **Patient Flow Trends** with time-series analysis

**Interactive Capabilities:**
- Dynamic filtering by time period, department, and patient demographics
- Drill-through capabilities for detailed patient journey analysis
- Real-time data refresh from Synapse SQL Pool

<img width="1695" height="918" alt="Screenshot 2025-11-09 130816" src="https://github.com/user-attachments/assets/b6610ab2-3461-4db2-975e-03e1fd8ecd30" />

## ✅ Key Achievements

### Technical Deliverables
- **End-to-End Pipeline**: Real-time ingestion → transformation → warehouse → analytics
- **Production-Ready Architecture**: Fault-tolerant and scalable cloud design
- **Data Quality Framework**: Comprehensive validation and error handling
- **Optimized Storage**: Delta Lake format with time travel capabilities

### Business Impact
- **Operational Visibility**: Real-time monitoring of hospital capacity
- **Resource Optimization**: Data-driven bed and staff allocation
- **Patient Experience**: Reduced wait times through predictive analytics
- **Compliance Ready**: Audit trails and data lineage tracking

## 🎓 Learning Outcomes

This project demonstrates comprehensive expertise in:
- **Cloud Data Engineering** with Azure services
- **Real-time Stream Processing** using PySpark
- **Data Warehousing** with star schema design
- **BI Development** and dashboard creation
- **DevOps Practices** with Git version control

---

## 🔄 Version Control

```bash
git init
git add .
git commit -m "feat: implement real-time patient flow analytics pipeline"
git branch -M main
git push -u origin main

