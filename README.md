# Data Quality with PySpark and Apache Iceberg (WAP Methodology)

## Overview

This repository demonstrates the **Write-Audit-Publish (WAP)** methodology for ensuring data quality using **PySpark** and **Apache Iceberg**. The workflow includes writing data to a branch, auditing it for quality checks, and publishing it to the main branch after successful validation. 

The example uses **New York City Yellow Taxi Trip Data** (January 2024) and leverages Apache Iceberg's branching capabilities with PySpark's data processing to implement a robust data quality framework.

---

## Features

- **Apache Iceberg Integration**: 
  - Create branches for isolated data changes.
  - Audit and validate data before merging to the main branch.
- **WAP Methodology**:
  - **Write**: Introduces changes to a separate branch.
  - **Audit**: Validates data for consistency and accuracy.
  - **Publish**: Merges audited changes to the main branch.
- **Data Quality Checks**: Validates expectations using Python logic.

---

## Getting Started

### Prerequisites
1. **Google Colab** (Recommended): PySpark comes pre-installed for easy setup.
2. Install compatible **PySpark** and **Iceberg** versions:
   - PySpark: `3.5.3`
   - Iceberg: `3.5_2.12:1.7.1`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/dataworlddev/DataQuality-WAP-Iceberg.git
2. Upload the repository to Google Colab for execution.
3. Make a Dir in your colab session folder and add data and replace dir base on new dir.

### Configuration

#### Environment Setup
- Add the required Iceberg JAR files:
  - org.apache.iceberg:iceberg-spark-runtime-3.5_2.12:1.7.1
  - org.apache.iceberg:iceberg-spark-extensions-3.5_2.12:1.7.1
#### Spark Configuration
- Configure the SparkConf object as shown in the notebook to:
  - Set Iceberg extensions.
  - Define a catalog for Iceberg tables.
  - Enable WAP on the tables.
### Workflow
1.  Write Section
    - Create a new branch (etl_job_v_1) to add or modify data.
    - Write data changes to the branch.
2. Audit Section
    - Perform data validation using custom logic or libraries like Great Expectations.
    - Ensure all data quality checks pass before publishing.
3. Publish Section
    - Merge the branch (etl_job_v_1) to the main branch using Iceberg's fast_forward function.
  
### Example Data
- New York City Yellow Taxi Trip Data:
  - January 2024 sample included in the data folder.
  - Full dataset available here.

### Usage
1. Open the notebook in Google Colab.
2. Execute the cells step by step to:
    - Initialize Spark and Iceberg.
    - Create branches and apply WAP methodology.
3. Validate data with provided audit logic.



