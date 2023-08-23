# Options-when-Reading-Files-Using-Pyspark
In this short tutorial, I explain the options available in Spark when reading parquet and csv files.
markdown

# Reading CSV and Parquet Files in Apache Spark

This is a tutorial on reading both CSV and Parquet files using Apache Spark. By mastering these options, you can control how Apache Spark reads data files:

## Common Options for Both Formats

Certain options are applicable to both CSV and Parquet file reading:

- `header`: Treat the first row as column headers (`"true"` or `"false"`).
- `inferSchema`: Infer column data types (`"true"` or `"false"`).
- `maxColumns`: Set the maximum number of columns in the DataFrame.
- `dateFormat`: Specify the date format for parsing date columns.
- `timestampFormat`: Specify the timestamp format for parsing timestamp columns.

**Example:**

```python
df_common = spark.read \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .option("maxColumns", 100) \
    .option("dateFormat", "yyyy-MM-dd") \
    .option("timestampFormat", "yyyy-MM-dd HH:mm:ss") \
    .csv("path/to/your/csv/file.csv")

python

df_common = spark.read \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .option("dateFormat", "yyyy-MM-dd") \
    .option("timestampFormat", "yyyy-MM-dd HH:mm:ss") \
    .parquet("path/to/your/parquet/files")

Reading CSV Files

CSV (Comma-Separated Values) is a widely-used format for tabular data. Learn how to read CSV files with Spark and leverage various options:

    sep: Delimiter used to separate fields (e.g., ",", "\t").
    quote: Character used to quote values containing special characters.
    nullValue: Define the representation of null values.

Example:

python

df_csv = spark.read \
    .option("header", "true") \
    .option("inferSchema", "true") \
    .option("sep", ",") \
    .option("quote", "\"") \
    .option("nullValue", "NA") \
    .csv("path/to/your/csv/file.csv")

Reading Parquet Files

Parquet is an optimized columnar storage format. Explore the options available for reading Parquet files:

    mergeSchema: Merge schemas of Parquet files ("true" or "false").
    compression: Compression codec for Parquet files (e.g., "snappy", "gzip").
    basePath: Base directory for relative paths in partitioned datasets.
    columnNameOfCorruptRecord: Column name for storing corrupt records.

Example:

python

df_parquet = spark.read \
    .option("mergeSchema", "true") \
    .option("compression", "snappy") \
    .option("columnNameOfCorruptRecord", "_corrupt_record") \
    .parquet("path/to/your/parquet/files")

By mastering these options, you can harness the full potential of Apache Spark to effectively process data from CSV and Parquet files, facilitating insightful data analysis and exploration.

csharp


By mastering these options, you can read data files more efficiently.
