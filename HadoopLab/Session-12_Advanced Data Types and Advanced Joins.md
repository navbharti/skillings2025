# Advanced Data Types and Advanced Join Strategies in Apache Hive

### **1. Hive Data Types**
Hive categorizes data types into two main groups: **Primitive** and **Advanced (Complex)**.

#### **Primitive Data Types**
These are standard data types used for simple values.
*   **Numeric:** TinyInt, SmallInt, Integer (Int), BigInt, Float, Double, Decimal.
*   **String:** String (most commonly used, accepts all characters), Char, VarChar.
*   **Miscellaneous:** Boolean, Date, Timestamp.

#### **Advanced (Complex) Data Types**
These are used when data needs to be stored in collections or structured formats within a single column.
*   **Array:** A collection of elements of the **same data type** (e.g., a list of subjects).
    *   **Access:** Data is accessed via an index starting from zero (e.g., `subject`).
    *   **Syntax:** `ARRAY<STRING>`.
*   **Map:** A collection of **Key-Value pairs**.
    *   **Access:** Data is accessed using the keys (e.g., `details['Subject']`).
    *   **Syntax:** `MAP<STRING, STRING>`.
    *   **Separators:** Requires defining `MAP KEYS TERMINATED BY` (usually a colon `:`) and `COLLECTION ITEMS TERMINATED BY` (e.g., a symbol like `$`).
*   **Struct (Structure):** A collection of elements of **different data types** with fixed field names.
    *   **Access:** Data is accessed using dot notation (e.g., `info.name`).
    *   **Syntax:** `STRUCT<name:STRING, age:INT, city:STRING>`.
*   **Union:** Stores one of several defined data types at a time.
    *   **Access:** Data is identified using tags like `tag__0` or `tag__1` to specify which type in the union is being retrieved.

---

### **2. Advanced Hive Joins**
When joining tables in a Big Data environment, Hive offers several strategies to optimize performance and reduce execution time.

| Join Type | Execution Location | Description & Use Case |
| :--- | :--- | :--- |
| **Reduce Side Join** | Reducer | The **default join** in Hive. It is expensive because it involves shuffling data across the network to the reducer. |
| **Map Side Join** | Mapper | Performed in the mapper to avoid shuffling. **Condition:** One table must be small enough to fit in memory. |
| **Broadcast Join** | Mapper | Similar to a Map Side Join; the small table is broadcasted to all executors for faster processing. |
| **Sort Merge Join** | Reducer | Used for joining **two large tables** that are already sorted. This improves efficiency when no table fits in memory. |
| **Skew Join Handling** | Varies | Optimizes performance when certain keys have a disproportionately large amount of data (skewed data), which typically slows down the join. |
| **Sort Merge Bucket (SMB) Join** | Mapper/Reducer | Specifically for **bucketed and sorted tables**. It is highly efficient and can reduce query time significantly (e.g., from 3 hours down to 1 hour). |

---

### **3. Data Migration: MySQL to Hive via Sqoop**
The sources explain how to automate the movement of data from a relational database (MySQL) directly into a Hive warehouse.

*   **Command Integration:** Standard Sqoop import commands are extended with Hive-specific arguments.
*   **Key Parameters:**
    *   `--hive-import`: Tells Sqoop to import the data into Hive instead of just HDFS.
    *   `--create-hive-table`: Automatically creates the table schema in Hive if it does not already exist.
    *   `--hive-table [name]`: Specifies the destination table name in Hive.
*   **Process:** Sqoop first moves the data to HDFS and then triggers a Hive command to load that data into the specified Hive table, effectively merging migration and warehousing into one step.

### **4. Key Optimization Properties**
To use advanced joins, specific properties must often be enabled in the Hive shell.
*   **Map Side Join:** `set hive.auto.convert.join = true;`.
*   **Dynamic Partitioning:** `set hive.exec.dynamic.partition.mode = nonstrict;`.
*   **SMB Join:** Requires both tables to be bucketed (`CLUSTERED BY`) and sorted.

![Advanced Data Types and Advanced Joins](infographics/Advanced Data Types.png)