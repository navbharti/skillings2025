# Apache PySpark (combine, organize, and optimize data for large-scale processing)

### **1. Joins in PySpark**
There are two primary methods to perform joins: using **Spark SQL** on temporary views or using the **DataFrame API**.

*   **Inner Join:** Returns only the matching records from both DataFrames based on a common column.
*   **Left Outer Join:** Retains all records from the left DataFrame and includes matching records from the right; unmatched right-side values appear as **null**.
*   **Right Outer Join:** Retains all records from the right DataFrame and includes matching records from the left; unmatched left-side values appear as **null**.
*   **Full Outer Join:** Combines all records from both DataFrames, using nulls where matches do not exist on either side.
*   **Left Semi Join:** Returns only the records from the left DataFrame that have a **match** in the right DataFrame. Unlike a standard join, it does not include columns from the right DataFrame.
*   **Left Anti Join:** The opposite of Semi Join; it returns only the records from the left DataFrame that **do not match** any record in the right DataFrame.
*   **Cross Join:** Produces a **Cartesian product**, where every record from the first DataFrame is multiplied by every record of the second.

### **2. Partitioning in PySpark**
Partitioning is essential for **parallelism**, allowing Spark to run commands simultaneously across different data segments.

*   **`repartition(n)`**: Used to **increase** or change the number of partitions. It redistributes the data across *n* new partitions.
*   **`coalesce(n)`**: Used to **reduce** the number of partitions. It is more efficient than repartitioning because it minimizes data shuffling.
*   **Check Partitions:** You can verify the current number of partitions in a DataFrame using the **`getNumPartitions()`** command.
*   **Custom Partitioning:** This involves physically writing data to disk using the **`partitionBy()`** command. It creates subdirectories based on specific columns (e.g., Year or Country), which significantly speeds up queries that filter by those columns.

### **3. Bucketing in PySpark**
**Bucketing** is used to divide data into a fixed number of files based on a **hash column**.

*   **Implementation:** It is implemented during the "write" phase using the command `df.write.bucketBy(n, "column").sortBy("column").saveAsTable("table_name")`.
*   **Hash Column:** The column used for bucketing is typically a unique or frequently joined column, such as **Customer ID** or **Department ID**.
*   **Performance:** Queries run on bucketed tables are processed in parallel across all buckets. For example, a query that might take one hour on a standard DataFrame can be processed much faster by splitting the work across eight parallel buckets.

### **4. When to Use Partitioning vs. Bucketing**
*   **Use Partitioning:** When you frequently filter data based on a column with **highly repeated records**, such as a specific Year, Department, or Country.
*   **Use Bucketing:** When you are dealing with **massive datasets** and complex queries that involve joins across multiple columns.