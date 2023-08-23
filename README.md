# Options-when-Reading-Files-Using-Pyspark
In this short tutorial, I explain the options available in Spark when reading parquet and csv files.

# PySpark File Reading Options Tutorial

This tutorial provides an overview of the various options available when reading CSV and Parquet files using PySpark. PySpark is the Python API for Apache Spark, a fast and general-purpose cluster computing system. We will cover common options applicable to both CSV and Parquet file formats, as well as those specific to each format.

## Table of Contents

- [Introduction](#introduction)
- [Common Options](#common-options)
- [CSV-Specific Options](#csv-specific-options)
- [Parquet-Specific Options](#parquet-specific-options)
- [Conclusion](#conclusion)

## Introduction

PySpark provides powerful tools for processing and analyzing large datasets. Reading data from various formats, such as CSV and Parquet, is a common task in data analysis and manipulation. Understanding the available options while reading these formats is essential for efficient data processing.

## Common Options

These options are applicable when reading both CSV and Parquet files.

- **`inferSchema`**: Infers the schema of the DataFrame from the data. When set to `True`, PySpark will attempt to detect the data types of columns automatically.
- **`header`**: Specifies whether the first row of the file should be treated as a header or not. Set to `True` if the file has a header, otherwise set to `False`.
- **`nullValue`**: Defines the string representation of null values in the data.
- **`dateFormat`**: Specifies the format of date columns if they need to be parsed.
- **`timestampFormat`**: Specifies the format of timestamp columns if they need to be parsed.
- **`mode`**: Specifies the behavior when encountering a schema mismatch or corrupt records. Possible values are "PERMISSIVE" (default), "DROPMALFORMED", and "FAILFAST".

## CSV-Specific Options

Options specific to reading CSV files.

- **`delimiter`**: Specifies the delimiter character used to separate fields in the CSV file. The default is ','.
- **`quote`**: Specifies the character used to quote fields containing special characters. The default is double-quote (").
- **`escape`**: Specifies the escape character used in fields containing special characters. The default is backslash (\).
- **`ignoreLeadingWhiteSpace`**: When set to `True`, leading whitespaces in a field are ignored.
- **`ignoreTrailingWhiteSpace`**: When set to `True`, trailing whitespaces in a field are ignored.

## Parquet-Specific Options

Options specific to reading Parquet files.

- **`mergeSchema`**: When set to `True`, attempts to merge schemas from different Parquet files.
- **`mergeSchemaBeforeRead`**: When set to `True`, performs schema merging before reading. Requires `mergeSchema` to be enabled.
- **`enforceSchema`**: When set to `False`, allows reading files with a schema that doesn't match the DataFrame's schema.

## Conclusion

In this tutorial, we explored various options available when reading CSV and Parquet files using PySpark. These options provide flexibility and control over the data reading process, enabling efficient manipulation and analysis of large datasets. By understanding and utilizing these options effectively, you can streamline your data processing workflows and extract valuable insights from your data.

Remember to refer to the official [PySpark documentation](https://spark.apache.org/docs/latest/api/python/index.html) for the most up-to-date information on reading options and their usage.
