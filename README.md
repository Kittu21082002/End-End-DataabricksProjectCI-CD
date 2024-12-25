# Azure Databricks End-to-End Project with Unity Catalog and CI/CD

## Project Overview
This project implements an end-to-end data pipeline using Azure Databricks integrated with Unity Catalog for data governance and CI/CD pipelines for automation. The solution focuses on ingesting, processing, and analyzing data related to traffic and roads, ensuring secure access, scalability, and compliance.

## Objectives
- Design and implement a data pipeline using Azure Databricks.
- Enable efficient data governance with Unity Catalog.
- Automate workflows using CI/CD pipelines.
- Process and analyze large datasets to generate actionable insights.
- Visualize final outputs using Power BI.

## Tech Stack
- **Azure Databricks**: Unified analytics platform for data engineering and machine learning.
- **Unity Catalog**: Centralized governance solution for data access and permissions.
- **Azure Data Lake Storage (ADLS)**: Scalable storage for raw and processed data.
- **Azure SQL Database**: For storing metadata or other relational data.
- **Azure Synapse Analytics**: Analytical layer for large-scale data processing.
- **Power BI**: For data visualization and reporting.
- **CI/CD Tools**: Azure DevOps (YAML pipelines, GitHub Actions).
- **Programming Languages**: Python, SQL, PowerShell.

## Data Sources
- **Road Data**:
  - `raw_roads1.csv`, `raw_roads2.csv`, ..., `raw_roads5.csv`
  - Contains data on road conditions, types, and maintenance records.
- **Traffic Data**:
  - `raw_traffic1.csv`, `raw_traffic2.csv`, ..., `raw_traffic6.csv`
  - Provides insights into vehicle counts, congestion levels, and traffic incidents.

## Project Flow
### Data Ingestion
- Raw data is ingested into the Landing Zone (`/landing`).

### Bronze Layer
- Data is stored as-is with minimal transformations.
- Bronze Schema applied.

### Silver Layer
- Cleaned and transformed data, removing duplicates and standardizing formats.
- Focus on specific transformations for traffic and roads.

### Gold Layer
- Aggregated and enriched data ready for business intelligence and analytics.
- Gold Schema applied.

### Data Governance
- Permissions and access are managed using Unity Catalog.

### Visualization
- Power BI is used for visualizing key insights and trends.

### CI/CD Automation
- Automated workflows for testing, building, and deploying code.
- Deployment to Azure resources and Databricks clusters.

## Prerequisites
- Azure Subscription with Databricks Workspace.
- Azure Data Lake Storage Gen2 account.
- GitHub repository set up for source control.
- Basic knowledge of Python, SQL, and PySpark.

## Setup Instructions
### Environment Setup
- Provision Azure Databricks workspace and Unity Catalog.
- Configure ADLS Gen2 for data storage.
- Enable access controls in Unity Catalog.

### Data Ingestion
- Upload raw data to the Landing Zone.
- Use `Load to Bronze.py` to ingest data into the Bronze Layer.

### Data Transformation
- Run `Silver - Traffic Transformations.py` and `Silver - Roads Transformation.py` for Silver Layer transformations.
- Use `Gold - Final Transformations and Loading.py` to process Gold Layer data.

### CI/CD Configuration
- Set up CI/CD pipelines using `cicd-main.yml` and `deploy.yml`.
- Secure database tokens with `DBToken.ps1`.

### Visualization
- Connect Power BI to the Gold Layer for reporting and dashboards.

## Key Learnings
- Importance of Unity Catalog for centralized data governance and fine-grained access control.
- How to structure data pipelines with Bronze, Silver, and Gold Layers for scalability.
- Integration of Azure Databricks with CI/CD tools for streamlined deployment.
- Data transformation techniques using PySpark.
- Best practices for securing sensitive data using Azure resources and tokens.

## Conclusion
This project demonstrates the power of Azure Databricks, Unity Catalog, and CI/CD in building a robust, scalable, and secure data pipeline. By following this approach, organizations can effectively process and analyze large datasets, ensure compliance, and generate actionable business insights.
