# ***📌 CHANGELOG***

| Date       | Version | Changes                                                                                                                                     | Notes                                                                                     |
|------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 2024-08    | v1.0    | | - This marks the first version of the pipeline, in which the core logic has been successfully implemented. <br>
| 2025-04-19 | v1.1    | - Rewrote documentation. <br> - Implemented logging & alerting. |                                           |


##### Version 1.0
<span style="font-weight:620; font-size: 14px;">✨ Features</span> 

- Successfully implemented an end-to-end real-time processing pipeline.
- Stored all data and analysis in the PostgreSQL database.
- Detected abnormal trips using basic rules (e.g., unusual duration, unexpected fare).
- Enables real-time and periodic (daily, weekly, etc.) trip trend analysis.

<span style="font-weight:620; font-size: 14px;">✅ Benefits</span>

- Easy setup with strong compatibility between Kafka, Spark, PostgreSQL, and Power BI.
- Leveraged parallelism: Kafka partitions and Spark distributed processing.
- Stable data pipeline with real-time ingestion and visualization.


<span style="font-weight:620; font-size: 14px;">⚠️ Limitations</span> 

- Alerts are not triggered in real-time — detection exists but lacks immediate notification.
- Not optimized for high-throughput or large-scale workloads (PostgreSQL limitations).
- Simultaneous read and write operations on PostgreSQL can lead to table-level locks, affecting both ingestion speed and query performance.
- Kafka only had one producer despite having 10 partitions → underutilized parallelism.
- No performance benchmark or monitoring for system health yet.

##### Version 1.1
- Although a single producer for 10 partitions may reduce write throughput, it is intentionally kept to simulate real-time data flow — aligning with the project's goal of time-based analyzing behavior. 

<span style="font-weight:620; font-size: 14px;">✨ Features</span> 

- Rewrote documentation and deployment notes to include new changes.
- Real-time alerts are now implemented.

<span style="font-weight:620; font-size: 14px;">✅ Benefits</span>

- Enables immediate anomaly detection and faster response time.