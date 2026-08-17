# Session-5 **Sqoop (SQL to Hadoop)** 

### Sqoop Architecture / Commands
*   **Main Topic:** Understanding and utilizing Sqoop to bridge the gap between Relational Database Management Systems (RDBMS) and the Hadoop Distributed File System (HDFS).
*   **Learning Objectives:** 
    *   Understand the fundamental role of Sqoop in data migration.
    *   Master basic commands like listing databases and tables.
    *   Learn advanced operations: `eval`, `import` (single/all tables), `export`, and `incremental` updates.
    *   Understand how Sqoop interacts with MapReduce and JDBC drivers.
*   **Skills Gained:** Ability to automate data ingestion from MySQL to HDFS and vice versa using Sqoop jobs.

---

### **1. Sqoop Architecture / Commands**

#### **A. Introduction to Sqoop**
*   **Definition:** Sqoop is a tool designed to **migrate data** between RDBMS (like MySQL, Oracle) and HDFS.
*   **Core Function:** It performs migrations and basic operations like checking metadata or creating tables within the source database using Hadoop tools.
*   **Architecture:** Sqoop is entirely **Linux-based** and operates through the terminal. It uses **JDBC (Java Database Connectivity)** to connect to the database.

#### **B. Connection & Discovery Commands**
Before migrating data, you must establish a connection and explore the source.
*   **Connectivity:** Uses the JDBC library (e.g., `mysql-connector-java`) to talk to MySQL.
*   **List Databases:** `sqoop list-databases --connect jdbc:mysql://127.0.0.1 --user [username] --password [password]`.
*   **List Tables:** `sqoop list-tables --connect jdbc:mysql://127.0.0.1/[db_name] --user [user] --password [pass]`.

#### **C. The `eval` Command**
*   **Purpose:** Allows you to run **SQL queries** (DML and DDL) directly from the terminal without entering the MySQL shell.
*   **Capabilities:** 
    *   Create new tables (`CREATE TABLE`).
    *   Insert data into tables (`INSERT INTO`).
    *   Run analytical queries like `COUNT`, `MAX`, `MIN`, `JOIN`, and `GROUP BY`.

#### **D. Data Ingestion (Import)**
Importing copies data from MySQL to HDFS.
1.  **Single Table Import:** Copies one specific table. A directory with the table name is automatically created in HDFS.
2.  **All Tables Import:** `import-all-tables` copies every table in a database into separate HDFS directories named after the tables.
3.  **Conditional Import:** Uses the `--where` clause to filter specific records (e.g., `WHERE id=5`).
4.  **Target Directory:** By default, it goes to a directory named after the table, but you can specify a custom path using `--target-dir`.

#### **E. Data Egress (Export)**
*   **Definition:** Exporting copies data from **HDFS back to MySQL**.
*   **Requirement:** The **Schema must match**. The HDFS file (usually a comma-separated text file) must have the same number of columns as the target MySQL table.

---

### **2. Sqoop Internals & Performance**

*   **MapReduce Backend:** Every Sqoop import/export command triggers a **MapReduce job** in the background.
*   **Mappers (`-m`):** This represents the number of parallel tasks (Map blocks) running the migration.
    *   **Single Node (Laptop):** Default is **1** because there is only one DataNode.
    *   **Production (Multi-node):** The default is **4** to ensure fault tolerance and high performance (one original + three replicas).
*   **Output Format:** Data is stored in HDFS as **"Part Files"** (e.g., `part-m-00000`), which are standard text files.

---

### **3. Incremental Import Logic**
This is used for daily data updates so that you don't re-import the entire table.
*   **Append Mode:** Adds only new data to the existing HDFS directory.
*   **Check Column:** Usually the `ID` or a `timestamp` used to identify where the last import left off.
*   **Last Value:** The specific value from the last successful import. Sqoop will import everything **greater than** this value.
    *   *Example:* If `last-value` is 10, the next import starts from 11.

---

### **4. Job Automation**
To avoid typing long commands daily, you can create a **Sqoop Job**.
*   **Create:** `sqoop job --create [job_name] -- [command]`.
*   **List:** See all saved jobs.
*   **Execute (`exec`):** Run the saved job.
*   **Show:** Inspect the details (table, database, target dir) of a specific job.

---

### **5. Real-world Applications & Tips**
*   **Daily Migration:** Automating the transfer of transaction records from a website's SQL database to HDFS for weekly Big Data analysis.
*   **Data Integrity:** Always verify the **JDBC driver** version matches the database version to prevent connection failures.
*   **Production Tip:** In industry settings, Data Engineers rarely perform the initial installation (handled by Admins); they focus on writing optimized `import` and `job` commands.

### **6. Common Interview Preparation (Based on Video)**
*   **Q: What is the default number of mappers in production?**
    *   **A:** 4.
*   **Q: What is the difference between Import and Export?**
    *   **A:** Import moves data from SQL to HDFS; Export moves it from HDFS to SQL.
*   **Q: Can you perform SQL Joins using Sqoop?**
    *   **A:** Yes, using the `eval` command or by using a free-form query in an import.
*   **Q: What happens if the schema doesn't match during an Export?**
    *   **A:** The export will fail because the column alignment between the HDFS text file and the SQL table is strict.