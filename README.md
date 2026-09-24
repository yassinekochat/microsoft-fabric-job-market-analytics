# 🚀 Job Market Analytics Platform — Microsoft Fabric

End-to-end **Data Engineering & Analytics platform** built with **Microsoft Fabric** to collect, transform, validate, analyze and visualize job-offer data from multiple sources.

The project implements a **Medallion Architecture (Bronze / Silver / Gold)** with Microsoft Fabric Lakehouse, multi-source ingestion, data-quality monitoring, a semantic model, Power BI analytics and a job-demand forecasting component.

---

## 🎯 Project Objectives

The objective of this project is to build a complete data platform capable of:

- Collecting job offers from multiple data sources
- Centralizing data in Microsoft Fabric
- Processing data using a **Bronze / Silver / Gold** architecture
- Cleaning and harmonizing multi-source datasets
- Monitoring data quality across different sources
- Creating analytics-ready Gold datasets
- Building a semantic model for business analysis
- Analyzing the job market through Power BI
- Exploring job-demand forecasting
- Orchestrating the different processing stages with Fabric Pipelines

---

## 🏗️ Project Architecture

```text
                         DATA SOURCES
                              │
             ┌────────────────┼────────────────┐
             │                │                │
      France Travail        Adzuna       Service Public
             │                │                │
             └────────────────┼────────────────┘
                              │
                              ▼
                       DATA INGESTION
                     Fabric Notebooks
                              │
                              ▼
                    ┌─────────────────┐
                    │     BRONZE      │
                    │    Raw Data     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │     SILVER      │
                    │    Cleaning     │
                    │ Harmonization   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │      GOLD       │
                    │ Analytics-Ready │
                    │      Data       │
                    └────────┬────────┘
                             │
                             ▼
                    FABRIC LAKEHOUSE
                             │
                 ┌───────────┴───────────┐
                 │                       │
                 ▼                       ▼
          DATA QUALITY              FORECASTING
                 │                       │
                 └───────────┬───────────┘
                             │
                             ▼
                      SEMANTIC MODEL
                             │
                             ▼
                          POWER BI
                             │
             ┌───────────────┼───────────────┐
             │               │               │
             ▼               ▼               ▼
         Overview         Market          Data Quality
                          Analysis             │
                                              ▼
                                      Demand Forecasting
```

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| **Microsoft Fabric** | Unified Data & Analytics platform |
| **Fabric Notebooks** | Data ingestion and transformation |
| **PySpark** | Distributed data processing |
| **OneLake** | Centralized data storage |
| **Fabric Lakehouse** | Lakehouse architecture |
| **Delta Tables** | Structured and optimized data storage |
| **Fabric Pipelines** | Data workflow orchestration |
| **Semantic Model** | Analytical data modeling |
| **Power BI** | Data visualization and business analytics |

---

## 📥 Multi-Source Data Ingestion

The platform integrates job-market data from multiple sources.

### 🇫🇷 France Travail

Job-offer data is ingested and prepared through a dedicated Fabric Notebook:

```text
01_Ingestion_France_Travail
```

### 🌐 Adzuna

Additional job-market data is ingested into the Bronze layer through:

```text
03_Ingestion_Adzuna_Bronze
```

### 🏛️ Service Public

Complementary public data is integrated through:

```text
04_Ingestion_Service_Public_Bronze
```

The different data sources are centralized and subsequently harmonized inside Microsoft Fabric.

---

## 🥉 Bronze Layer

The **Bronze layer** represents the raw-data ingestion layer.

Data from the different sources is collected and stored before business transformations are applied.

Main ingestion notebooks:

```text
01_Ingestion_France_Travail
03_Ingestion_Adzuna_Bronze
04_Ingestion_Service_Public_Bronze
```

This layer preserves the original source information and provides the starting point for the transformation pipeline.

---

## 🥈 Silver Layer

The **Silver layer** is responsible for cleaning, standardizing and harmonizing the different job-offer datasets.

Main notebook:

```text
05_Bronze_to_Silver_MultiSource
```

This stage prepares consistent multi-source data that can subsequently be used for analytical processing.

Typical operations include:

- Data cleaning
- Schema standardization
- Multi-source harmonization
- Data-type normalization
- Preparation for analytical processing

---

## 🥇 Gold Layer

The **Gold layer** contains analytics-ready datasets.

Main notebook:

```text
06_Silver_to_Gold
```

The objective of this layer is to prepare structured datasets optimized for:

- Job-market analysis
- KPI calculation
- Semantic modeling
- Power BI reporting
- Forecasting

---

## 🏠 Microsoft Fabric Lakehouse

The project uses a dedicated Microsoft Fabric Lakehouse:

```text
offre_emploi_lakehouse
```

The Lakehouse centralizes the datasets generated throughout the Medallion Architecture.

```text
Bronze
   ↓
Silver
   ↓
Gold
   ↓
Fabric Lakehouse
```

It provides the central storage layer used by the analytical components of the project.

---

## 🔄 Data Pipeline Orchestration

The project includes a Microsoft Fabric pipeline:

```text
PFE_Job_Offers_Pipeline
```

The pipeline is used to coordinate the different stages of the data workflow.

The overall processing logic follows:

```text
Data Sources
     ↓
Ingestion
     ↓
Bronze
     ↓
Silver
     ↓
Gold
     ↓
Lakehouse
     ↓
Analytics
```

---

## 🔍 Data Quality

Data quality is an important component of the platform.

A dedicated Fabric Notebook analyzes data quality across the different sources:

```text
Score moyen de qualité par source
```

The objective is to identify differences in data quality before the information is consumed by the analytical layer.

This provides an additional monitoring layer between data ingestion and business analytics.

---

## 📈 Job Offer Forecasting

The project also includes a forecasting component designed to analyze the evolution of job-offer demand.

Notebook:

```text
08_Job_Offers_Forecast
```

A corresponding Fabric experiment is also included in the workspace.

The forecasting component complements the descriptive analysis by exploring the evolution of job demand over time.

---

## 🧠 Semantic Model

The analytical layer uses a dedicated semantic model:

```text
Job_Offers_Semantic_Model
```

The semantic model connects the Fabric Lakehouse with the Power BI reporting layer.

```text
Fabric Lakehouse
       ↓
Semantic Model
       ↓
Power BI
```

This architecture separates the storage and transformation layers from the business reporting layer.

---

## 📊 Power BI Dashboard

The final analytical layer is implemented through a Power BI report:

```text
Dashboard_pfe_offre_emploi
```

The dashboard contains several analytical pages.

### 🌍 Overview

Provides a global overview of the job market and the main indicators available in the platform.

### 📊 Market Analysis

The market-analysis page explores job offers according to dimensions such as:

- Contract type
- Experience level
- Recruiting company
- Job category
- Geographic location

### ✅ Data Quality

This page provides visibility into the quality of the data coming from the different sources.

### 🔮 Demand Forecasting

The forecasting page explores the evolution of job demand over time.

---

## 🔗 Analytics Architecture

The analytical workflow implemented in Microsoft Fabric follows:

```text
offre_emploi_lakehouse
          │
          ▼
Job_Offers_Semantic_Model
          │
          ▼
Dashboard_pfe_offre_emploi
```

This architecture provides a clear separation between:

1. Data storage
2. Data modeling
3. Business visualization

---

## 📂 Microsoft Fabric Workspace

The Fabric workspace contains the following main components:

```text
PFE_Offres_Emploi
│
├── Notebooks
│   │
│   ├── 01_Ingestion_France_Travail
│   ├── 03_Ingestion_Adzuna_Bronze
│   ├── 04_Ingestion_Service_Public_Bronze
│   ├── 05_Bronze_to_Silver_MultiSource
│   ├── 06_Silver_to_Gold
│   ├── 08_Job_Offers_Forecast
│   └── Score moyen de qualité par source
│
├── Lakehouse
│   └── offre_emploi_lakehouse
│
├── Pipeline
│   └── PFE_Job_Offers_Pipeline
│
├── Semantic Model
│   └── Job_Offers_Semantic_Model
│
├── Power BI Report
│   └── Dashboard_pfe_offre_emploi
│
└── Forecasting
    └── 08_Job_Offers_Forecast
```

---

## 🔄 End-to-End Data Flow

The complete data workflow can be summarized as follows:

```text
France Travail ─────┐
                    │
Adzuna ─────────────┼──► Ingestion
                    │
Service Public ─────┘
                         │
                         ▼
                       Bronze
                         │
                         ▼
                       Silver
                         │
                         ▼
                        Gold
                         │
                         ▼
                  Fabric Lakehouse
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
        Data Quality          Forecasting
              │                     │
              └──────────┬──────────┘
                         │
                         ▼
                  Semantic Model
                         │
                         ▼
                      Power BI
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
       Overview        Market         Quality /
                       Analysis       Forecast
```

---

## 📸 Project Screenshots

### Microsoft Fabric Workspace

The workspace contains the notebooks, Lakehouse, pipeline, semantic model, forecasting components and reporting layer used throughout the project.

> 📷 Screenshot to be added

---

### Lakehouse → Semantic Model → Power BI

```text
offre_emploi_lakehouse
          ↓
Job_Offers_Semantic_Model
          ↓
Dashboard_pfe_offre_emploi
```

> 📷 Screenshot to be added

---

### 📊 Job Market Analysis

The dashboard provides detailed analysis of the job market by contract, experience, company, job category and location.

> 📷 Screenshot to be added

---

### ✅ Data Quality

Data-quality indicators provide visibility into the reliability of the different sources.

> 📷 Screenshot to be added

---

### 🔮 Demand Forecasting

The forecasting component explores the evolution of job-offer demand.

> 📷 Screenshot to be added

---

## 🚀 Key Data Engineering Concepts Demonstrated

This project demonstrates several important Data Engineering concepts:

- Multi-source data ingestion
- Medallion Architecture
- Bronze / Silver / Gold layers
- Data cleaning and transformation
- Data harmonization
- PySpark processing
- Lakehouse architecture
- Delta-based storage
- Data-quality monitoring
- Pipeline orchestration
- Semantic modeling
- Business Intelligence
- Power BI reporting
- Forecasting integration
- End-to-end Microsoft Fabric architecture

---

## 🔮 Future Improvements

Possible future improvements include:

- Automated pipeline scheduling
- Additional job-market data sources
- More advanced data-quality rules
- Pipeline monitoring and alerting
- Enhanced forecasting models
- Extended Power BI analytics
- CI/CD implementation
- Microsoft Fabric deployment pipelines
- Automated testing
- Data governance and lineage improvements

---

## 👨‍💻 Author

**Yassine Kochat**

Master's Degree — Data Engineering

🏅 Microsoft Certified: **Fabric Data Engineer Associate (DP-700)**

📍 Paris, France

[LinkedIn](https://www.linkedin.com/in/yassine-kochat-9967b61a1) · [GitHub](https://github.com/yassinekochat)

---

⭐ This project is part of my Data Engineering portfolio.
