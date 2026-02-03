# Large-Scale Flight Delay Analysis Using Apache Spark & PySpark

**Short Description:**  
Large-scale flight delay analysis and prediction using Apache Spark and PySpark with Random Forest Regression and interactive Plotly visualizations.

---

## 📌 Table of Contents
1. [Project Objective](#project-objective)
2. [Dataset Overview](#dataset-overview)
3. [Tools & Technologies](#tools--technologies)
4. [Methodology & Workflow](#methodology--workflow)
5. [Visualizations & Insights](#visualizations--insights)
6. [Challenges & Solutions](#challenges--solutions)
7. [Conclusion](#conclusion)
8. [References](#references)
9. [License](#license)

---

## 📌 Project Objective
The goal of this project is to analyze flight delay patterns across the United States using Big Data technologies. By leveraging **Apache Spark** and **PySpark**, we processed large-scale flight records to identify trends, perform MapReduce operations, and build a **Random Forest Regression** model to predict arrival delays.

### Key Goals:
* Identify airlines with the highest operational delays.
* Analyze monthly trends and airport performance.
* Apply **MapReduce** concepts using Spark RDDs.
* Predict flight arrival delays with high accuracy (**R² = 0.83**).

---

## 📊 Dataset Overview
* **Name:** 2015 US Flight Data (Kaggle)  
* **Scope:** Analyzed a subset of 60,000 records for processing efficiency.  
* **Features:** Airline, Origin/Destination, Departure/Arrival Delays, Cancellations, Month/Day/Time.  
* **Significance:** Contains complex features ideal for distributed processing and predictive modeling.

**Dataset Link:** [Flights Dataset - Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays)

---

## 🛠️ Tools & Technologies
* **Apache Spark 3.5.0:** Distributed data processing engine.  
* **PySpark:** Python API for Spark (SQL, RDD, and MLlib).  
* **Google Colab:** Cloud environment for execution.  
* **Plotly Express:** For interactive and professional visualizations.  
* **Java 11:** Required environment for Spark binaries.  

---

## ⚙️ Methodology & Workflow

### 1. Environment Setup
Configured Java 11 and Spark 3.5.0 in Google Colab to enable seamless distributed computing.

### 2. Data Cleaning & Pre-processing
* Handled null values in critical delay columns.  
* Feature engineering using `StringIndexer` and `VectorAssembler` to prepare data for ML.  

### 3. Big Data Analytics (MapReduce & Spark SQL)
* **MapReduce:** Converted DataFrame to RDD, mapped `(Flight Number, Arrival Delay)` pairs, reduced to compute average delays.  
* **Aggregation:** Used `groupBy` and `agg` operations to extract insights for airlines and airports.

### 4. Machine Learning
* **Algorithm:** Random Forest Regression (Spark MLlib)  
* **Hyperparameters:**  
  - `numTrees=20` → number of trees in the forest  
  - `maxDepth=7` → max depth of each tree (controls overfitting)  
  - `maxBins=400` → allows high-cardinality categorical features like airports  
* **Performance:**  
  - **R² Score:** 0.83 (Model explains 83% variance in arrival delays)  
  - **RMSE:** Low error achieved via parallel tree learning  

---

## 📈 Visualizations & Insights
The project features **6 interactive Plotly charts**:  
1. **Top 10 Airlines by Delay:** Highlights operational bottlenecks.  
2. **Monthly Trends:** Shows peak delays during summer months.  
3. **Cancellation Ratio:** Pie chart displaying airline reliability.  
4. **Delay Correlation:** Scatter plot showing how departure delays propagate to arrival delays.  
5. **Heatmap:** Correlation between specific airlines and months.  
6. **Airport Traffic:** Horizontal bar chart showing busiest hubs.  

*Note:* Sampling of 1% of data was used for scatter plots to prevent memory issues while maintaining statistical validity.

---

## 🚀 Challenges & Solutions
* **Challenge:** Java-PySpark version mismatch in Colab.  
  **Solution:** Enforced Spark 3.5 + Hadoop 3 + Java 11.  
* **Challenge:** Visualizing large datasets without crashes.  
  **Solution:** Applied data sampling and optimized Plotly visualizations.  

---

## 🏁 Conclusion
This project demonstrates the **power of Apache Spark** for Big Data analytics. By combining RDD MapReduce, Spark SQL, and Spark MLlib, we transformed raw flight data into actionable insights and built a **high-performing predictive model** with excellent accuracy (R² = 0.83).

---

## 🔮 Future Enhancements
* Real-time streaming analysis using Spark Streaming.  
* Hyperparameter tuning of Random Forest for improved accuracy.  
* Deep Learning models using Spark MLlib.  
* Deployment on cloud clusters for live flight predictions.

---

## 🔗 References
* [Flights Dataset - Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays)  
* [Apache Spark Documentation](https://spark.apache.org/docs/latest/)  
* [Plotly Express Guide](https://plotly.com/python/plotly-express/)  

---

## 📄 License
This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.
