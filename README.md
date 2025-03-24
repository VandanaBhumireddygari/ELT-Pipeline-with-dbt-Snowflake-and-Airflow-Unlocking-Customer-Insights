
# **Scalable Data Pipeline with Snowflake, Apache Airflow, dbt, and Snowpark**
🔗 **Author:** Vandana Bhumireddygari  
📧 **Contact:** [vandanabhumireddygari@gmail.com] 

## **Overview**  
This project demonstrates how to build an **end-to-end data pipeline** using **Snowflake, Apache Airflow, dbt, and Snowpark** to efficiently ingest, transform, and analyze booking data. The pipeline is automated using Airflow DAGs and leverages Snowpark for advanced analytics.  

## **Tech Stack**  
- **Snowflake** – Cloud data warehouse for structured storage and querying  
- **Apache Airflow** – Workflow orchestration for automated data processing  
- **dbt (Data Build Tool)** – SQL-based transformation framework  
- **Snowpark** – Python-based data science & analytics within Snowflake  
- **Cosmos** – Integration framework for dbt within Airflow  


## **Workflow**  

1. **Data Ingestion & Storage**  
   - Load CSV datasets (**bookings_1, bookings_2, customers**) into Snowflake tables.  

2. **Data Transformation with dbt**  
   - Join and clean the raw datasets to create a **prepped_data** model.  
   - Generate analytical views like:  
     - `hotel_count_by_day` (daily hotel bookings)  
     - `30_day_avg_cost` (rolling average of booking costs)  

3. **Orchestration with Apache Airflow**  
   - DAGs manage the end-to-end execution of the pipeline.  
   - Uses `dbtDAG` for running dbt transformations.  
   - Implements `dbtTaskGroup with Snowpark` for advanced analytics.  

4. **Advanced Analytics with Snowpark**  
   - Analyze the **hotel with the highest booking cost**.  
   - Perform Python-based data processing within Snowflake.  

## **Challenges & Solutions**  
| **Challenge** | **Solution** |  
|--------------|-------------|  
| Outdated documentation and missing commands | Updated configurations to align with the latest versions |  
| Constraint violations in SQL queries | Introduced unique autogenerated IDs to resolve key conflicts |  
| Airflow & dbt configuration issues | Manually adjusted settings in `profiles.yml` and corrected file structure |  

## **Setup & Installation**  

### **1. Clone the Repository**  
```bash
git clone https://github.com/your-username/scalable-data-pipeline.git
cd scalable-data-pipeline
```

### **2. Install Dependencies**  
```bash
pip install -r requirements.txt
```

### **3. Set Up Airflow**  
```bash
export AIRFLOW_HOME=$(pwd)/airflow
airflow db init
airflow scheduler & airflow webserver
```

### **4. Configure dbt Connection**  
Update `profiles.yml` with your Snowflake credentials.  

### **5. Run the Pipeline**  
Trigger the DAG in Airflow:  
```bash
airflow dags trigger dbt_pipeline
```

## **Key Takeaways**  
- Built a **fully automated data pipeline** integrating multiple cloud-based tools.  
- Leveraged **dbt for SQL transformations** and **Snowpark for Python-based analytics**.  
- Successfully **orchestrated workflows using Apache Airflow** with Cosmos.  

## **Future Improvements**  
- Implement data quality checks with **Great Expectations**.  
- Optimize query performance using **Snowflake clustering**.  
- Expand analytics with **ML-based predictions** on booking trends.  
  
```
