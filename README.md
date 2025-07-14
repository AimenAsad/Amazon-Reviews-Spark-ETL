# 🚀 Scalable Amazon Review Data Loader with Apache Spark

This project focuses on developing a **robust and scalable data-loading mechanism** using **Apache Spark** to efficiently process the large **Amazon Review dataset**. It addresses critical challenges in large-scale data handling, validation, and performance optimization.

---

## 🎯 Purpose of the Assignment

The primary goal of this assignment is to demonstrate proficiency in handling big data workloads with Spark. Key objectives include:

* **Setting up a Spark environment** for distributed computing.
* **Efficiently loading a gzipped JSON file** into a Spark DataFrame.
* **Validating data integrity** and implementing comprehensive logging for key actions.
* **Optimizing the solution** for maximum performance and scalability with large datasets.

---

## 🛠️ Key Technologies

* **Apache Spark:** For distributed data processing and analysis.
* **PySpark:** The Python API for Apache Spark.
* **Python:** The primary programming language used for scripting.
* **Jupyter Notebooks (Kaggle):** For interactive data exploration and script execution.

---

## ⚙️ Steps to Set Up Spark and Run the Script

### Set Up Spark Environment

1.  **Download and install Apache Spark** from the [official Apache Spark website](https://spark.apache.org/downloads.html).
2.  **Install Python and PySpark:**
    ```bash
    pip install pyspark
    ```

### Download the Dataset

* Download the **Amazon Review dataset** (expected in gzipped JSON format, e.g., `dataset.json.gz`).
* Place the downloaded file in a `data/` folder within your project's root directory.

### Run the Script

* Execute your main Spark script (e.g., `main_loader.py` or your Jupyter Notebook).

### Kaggle-Specific Setup (if applicable)

If you're running this on Kaggle, consider these steps:

* **Upload dataset** via the Kaggle "Add Data" button.
* Ensure the notebook has **Internet access** (for Spark dependencies if not pre-installed).
* Set your notebook accelerator to **"GPU"** for potentially better performance (though not strictly required for this data loading task itself, beneficial for complex transformations).

---

## 🧠 Memory Management Considerations

For optimal performance and to prevent crashes with large datasets:

* **Start with reasonable memory allocation:** Begin with **4GB for both executor and driver memory** in your Spark configuration.
* **Monitor memory usage:** Keep an eye on memory consumption, especially when running in environments like Kaggle (usually visible in the right sidebar).
* **Troubleshooting Crashes:** If your Spark job crashes due to memory issues, consider:
    * Reducing the number of partitions (e.g., `.repartition(100)`).
    * Enabling Adaptive Query Execution: `.config("spark.sql.adaptive.enabled", "true")`.

---

## 📦 Output Files

All generated output files will be saved to the designated working directory (e.g., `/kaggle/working/` on Kaggle). The final submission package will typically include all necessary output artifacts.

---

## ⚠️ Challenges and Assumptions

### Challenges Addressed

This project specifically tackles the following challenges inherent in large-scale data processing:

* **Large Dataset Size:** Efficiently loading and handling a massive, gzipped JSON dataset requiring optimized memory management and partitioning strategies.
* **Schema Inference:** Managing dynamic schema inference, which can be slow and occasionally prone to misinterpreting data types. The solution either leverages robust inference or allows for explicit schema definition.
* **Corrupted Records:** Implementing mechanisms to handle malformed or corrupted records gracefully, minimizing data loss during processing.
* **Performance Optimization:** Tuning Spark configurations and code to ensure the script processes data efficiently and scales effectively.

### Assumptions

The following assumptions were made during the project development:

* **Schema Consistency:** The Amazon Review dataset generally adheres to a consistent schema containing fields such as `reviewerID`, `asin`, `reviewText`, `overall`, and `unixReviewTime`.
* **Environment Configuration:** The underlying Spark environment is assumed to be properly configured with adequate memory and computational resources.
* **Data Format:** The dataset is consistently in gzipped JSON format and is generally well-structured, allowing for efficient parsing.

---
