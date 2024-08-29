# ETL Data Pipeline

The ETL Data Pipeline project integrates DBT, Snowflake, and Airflow to automate and streamline data workflows. This project is designed to handle the extraction, transformation, and loading (ETL) of data from various sources into a centralized data warehouse, enabling efficient data processing and analytics.

## Components

### 1. **DBT (Data Build Tool)**
   - **Purpose:** DBT is used for data transformation, allowing users to create and execute SQL models that transform raw data into clean, usable formats.
   - **Role in the Pipeline:** DBT handles the transformation layer of the ETL process, where SQL models are defined and managed to ensure data consistency and quality.

### 2. **Snowflake**
   - **Purpose:** Snowflake serves as the central data warehouse, providing a scalable and secure environment for storing and querying data.
   - **Role in the Pipeline:** Snowflake stores both raw and transformed data, enabling advanced analytics and reporting.

### 3. **Airflow**
   - **Purpose:** Airflow is an orchestration tool that schedules and monitors the ETL tasks.
   - **Role in the Pipeline:** Airflow automates the execution of DBT models and manages the entire workflow, ensuring that data is extracted, transformed, and loaded in a timely and efficient manner.


## Setup Instructions

1. **Install DBT and Snowflake Dependencies**
    ```bash
    pip install dbt-snowflake
    pip install dbt-core
    ```

2. **Initialize DBT Project**
    ```bash
    dbt init
    ```

3. **Configure DBT Project**
    - Modify the `dbt_project.yml` file to match your project settings.

4. **Organize Models**
    - Delete the `example` folder in the `models/` directory.
    - Create two new folders: `staging` and `marts`.

5. **Create and Manage Dependencies**
    - Create a `packages.yml` file for managing DBT dependencies.
    - Run the following command to install the dependencies:
      ```bash
      dbt deps
      ```

6. **Define Staging Models**
    - Create the `staging/tpch_sources.yml` file to define the source data.
    - Create the `staging/stg_tpch_orders.sql` file to stage the orders data.
    - create the `staging/stg_tpch_line_items.sql`file to stage the lineitems.

7. **Run DBT Models**
    ```bash
    dbt run
    ```

    - This command will create the `stg_tpch_orders` and `stg_tpch_line_items`view in Snowflake.

