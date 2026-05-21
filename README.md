# Streaming platform content analysis and big data engineering (PySpark)

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

## Description of the project
This project focuses on data engineering and exploratory data analysis of a large-scale streaming platform catalog. The main objective is to process compressed columnar data to extract insights about content distribution, release trends, genres, and production origins.

The pipeline demonstrates advanced handling of optimized big data storage formats, schema enforcement, and structural data manipulation.

**Dataset:** the analysis utilizes a distributed schema stored in an optimized `snappy.parquet` format, encompassing comprehensive details on movies and tv shows, including directors, cast, countries, and nested arrays for genres.

## Technologies and libraries
* **Python**: core language for dataset processing.
* **Apache Spark / PySpark**: distributed computing framework used for the initial heavy transformation and metadata management.
* **Pandas**: utilized for local aggregation and data profiling.
* **PyArrow / Fastparquet**: engines required for reading compressed columnar schemas.

## Key analysis phases

### 1. Columnar data ingestion and schema validation
* **Parquet integration**: implementation of efficient data loading using binary columnar storage optimized with snappy compression.
* **Metadata inspection**: validation of explicit data types, ensuring dates, integers, and nested array structures are correctly mapped without information loss.

### 2. Feature engineering and data restructuring
* **Duration parsing**: isolation of runtime metrics by splitting raw string descriptions into independent numerical attributes for movie runtimes (`duration_min`) and series lengths (`duration_seasons`).
* **Geographical classification**: development of logical triggers to identify multi-country co-productions (`its_multicountry`) versus single-origin titles.
* **Array unpacking**: extraction and structuring of nested categorical variables contained within the genre arrays.

### 3. Catalog profiling and insights
* **Content distribution**: evaluation of the ratio between movies and tv shows across different release eras.
* **Regional analysis**: tracking dominant production hubs and identifying key clusters of international collaboration.


## How to run it?
1. Ensure you have **Python 3.x** installed along with an environment capable of reading parquet files.
2. Place the data file `part-00000-5512fdbf-3ba7-4778-92ca-0df880472840-c000.snappy.parquet` in your project data directory.
3. Install the required dependencies via your terminal:
   ```bash
   pip install pandas pyarrow fastparquet matplotlib seaborn
4. Create or run your analysis script (or Jupyter Notebook) to query the parquet dataframe directly.

# Academic context

This project was developed as part of the Big Data and Data Engineering modules of the master's degree, showcasing proficiency in modern storage formats, schema design, and analytical pipeline optimization.
