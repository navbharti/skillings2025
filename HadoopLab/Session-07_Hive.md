# Hive Installation and Configuring Apache Hive and understanding its Master-Slave architecture within the Hadoop ecosystem
### **1. Overview**
*   **Learning Objectives:**
    *   Successfully install and configure Hive on a Linux (Ubuntu) environment.
    *   Understand the relationship between Hive, MapReduce, and HDFS.
    *   Learn the role of the MetaStore and Derby database.
    *   Differentiate between data migration (Sqoop) and data warehousing (Hive).
*   **Skills Gained:** Hive shell interaction, HDFS directory management for warehouse data, and HiveQL (Hive Query Language) basics.

---

### **2. Installation Procedure**

#### **A. Prerequisites**
*   **Hadoop Software:** Hadoop must be installed and active before Hive can function.
*   **Hive Package:** A 143 MB Hive tool package is required.
*   **Installation Document:** A step-by-step guide is used to manage configuration properties.

#### **B. Step-by-Step Setup**
1.  **Extraction:** Download the zip file, extract it to the Home directory, and rename the folder to a simple lowercase name like "hive".
2.  **Environment Paths (.bashrc):** Just like Hadoop and Sqoop, the Hive binary path must be added to the `.bashrc` file (e.g., `export HIVE_HOME=/home/user/hive`) and refreshed using the `source` command.
3.  **Configuration (`hive-site.xml`):**
    *   Create a file named `hive-site.xml` by copying an existing template.
    *   Set the **user properties** and **paths** within the configuration tags.
    *   Update the username to match your specific Linux user (e.g., "swap").
4.  **HDFS Preparation:** Start Hadoop (`start-all.sh`) and create specific directories in HDFS where Hive will store its data.
5.  **Schema Initialization:** When starting Hive for the first time, users may encounter an error. Two specific commands must be run once to move the schema to the **Derby Database** (MetaStore).

---

### **3. Hive Architecture & Components**

Hive follows a structured flow to convert SQL-like queries into Big Data processes.

*   **Hive Command Line (CLI):** The user interface (shell) where developers type HiveQL commands.
*   **HiveQL Processing Engine:** The internal "brain" that reads the Hive Query Language and plans the execution.
*   **Execution Engine:** This component triggers the backend processing. For most operations (like `WHERE`, `ORDER BY`, or `GROUP BY`), the engine runs **MapReduce** jobs.
*   **MetaStore (Derby Database):** Stores the "metadata"—essentially the definitions and caches for your tables and databases.
*   **HDFS (Storage):** The physical layer where the actual data resides. By default, Hive data is stored in `/user/hive/warehouse/`.

---

### **4. Internal Workings: The Role of MapReduce**

While simple commands like `CREATE DATABASE` or `LOAD DATA` happen quickly, analytical queries trigger deeper processes.
*   **Implicit MapReduce:** When you run complex clauses (e.g., `JOIN`, `GROUP BY`), the Execution Engine initiates a MapReduce job, showing the same "Map 0% / Reduce 0%" progress seen in Sqoop.
*   **Data Backup:** Every database and table created in Hive has a corresponding directory in HDFS. For example, if you create a database `exp` and a table `employee`, you can find them in the HDFS Web UI (Port 50070) under the warehouse directory.

---

### **5. Comparison: Sqoop vs. Hive**

| Feature | **Sqoop** | **Hive** |
| :--- | :--- | :--- |
| **Primary Use** | **Migration:** Moving data between RDBMS and Hadoop. | **Warehousing:** Storing and analyzing data in one place. |
| **Interaction** | Terminal/Shell based. | SQL-based (HiveQL). |
| **Execution** | Triggers MapReduce for imports/exports. | Triggers MapReduce for data analysis/queries. |

---

### **6. Practical Application and Verification**
*   **Starting the Tool:** Type `hive` in the terminal to enter the Hive shell.
*   **Verification:** Create a basic database and check its existence in the shell.
*   **HDFS Validation:** Open a new terminal and run `hdfs dfs -lsr /user/hive/warehouse/` to see the physical folders created for your databases and tables.
*   **Real-world Context:** In industry, developers focus on the **SQL/HiveQL** logic (which is 90% standard SQL) rather than the installation, which is typically handled by Admins.

---

### **7. Summary Checklist for Students**
*   **Default Port:** 50070 (Hadoop Web UI for browsing files).
*   **MetaStore:** Default is Derby database.
*   **Key Skill:** Strong **SQL** knowledge is essential for Hive and other cloud tools like AWS Athena.

![Inforgraphic](inforgraphics/Session-07_Software_Setup_and_Architecture_Guide.png)