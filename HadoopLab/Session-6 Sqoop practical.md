# Session-6 **Sqoop installation and practical operations** 

### **1. MySQL Installation & Configuration**
Before installing Sqoop, a source database like MySQL must be set up.
*   **Installation:** The process involves running specific commands to download the **318 MB MySQL server package**.
*   **Security:** Users must set a root password (e.g., "admin") during the process.
*   **Initial Testing:** To verify the database is functional, perform standard SQL operations:
    *   `CREATE DATABASE` (e.g., a database named `exp`).
    *   `CREATE TABLE` (e.g., `employee` with columns for ID and Name).
    *   `INSERT INTO` and `SELECT * FROM` to confirm data persistence.

### **2. Sqoop Installation Steps**
The installation requires manual extraction and configuration of the tool.
*   **Prerequisites:** **Hadoop must be started** (`start-all.sh`) before running Sqoop commands.
*   **Software Components:** You need the `sqoop-1.4.7.tar.gz` file and the **MySQL connector jar file**.
*   **Extraction:** Extract the tarball into the Home directory and rename the folder to simply `sqoop`.
*   **Jar Configuration:** Copy the MySQL connector jar file into the `lib` folder inside the Sqoop directory.
*   **Environment Configuration (`sqoop-env.sh`):**
    *   Navigate to the `conf` folder.
    *   Copy `sqoop-env-template.sh` and rename it to `sqoop-env.sh`.
    *   Edit lines 23 and 26 to remove the comment symbol (`#`) and provide the correct **Hadoop path**.

### **3. Setting Environment Paths**
To run Sqoop from any terminal window, the path must be added to the system's configuration.
*   **Edit `.bashrc`:** Open the file using `sudo gedit ~/.bashrc` and add the paths for `SQOOP_HOME` and update the system `PATH`.
*   **Refresh:** Run `source ~/.bashrc` to apply the changes.
*   **Verification:** Execute `sqoop version` to ensure the tool is correctly installed.

### **4. Practical Commands and Operations**
Sqoop allows for direct interaction with the database and data migration.
*   **Discovery Commands:** Use `list-databases` and `list-tables` to view existing metadata in the MySQL environment.
*   **The `eval` Command:** This allows running any SQL query (DML or DDL) directly from the Sqoop terminal. For example, you can create new tables or insert records without logging into MySQL.
*   **Importing Data (SQL to HDFS):**
    *   **Single Table Import:** Migrates one table. It triggers a **MapReduce job** in the background.
    *   **All-Tables Import:** Migrates every table in a database to HDFS.
    *   **Verification:** Data can be verified via the terminal using `hdfs dfs -ls` or through the **Hadoop Web UI at Port 50070**.
    *   **Structure:** HDFS creates a directory named after the table containing a `part-m-00000` file (the data) and a success message.

### **5. Advanced Import & Export Logic**
*   **Conditional Import:** Uses the `--where` clause to filter data (e.g., `id = 3`) and requires a `--target-dir` to avoid overwriting existing data.
*   **Incremental Import:** Uses `--incremental append` to add newly added records (e.g., IDs 4, 5, 6) based on a `--check-column` and the `--last-value` of the previous import.
*   **Data Export (HDFS to SQL):** Copies a text file from HDFS into a pre-created MySQL table. **Crucial Requirement:** The number of columns in the MySQL table must exactly match the data in the HDFS file to avoid errors.

### **6. Automation with Sqoop Jobs**
To simplify repetitive tasks, Sqoop allows the creation of "Jobs."
*   **Creation:** Use `sqoop job --create [job_name] -- [command]`.
*   **Execution:** Run the job using `sqoop job --exec [job_name]`.
*   **Troubleshooting:** Running jobs may require an additional **Java JSON jar file** in the Sqoop `lib` folder to handle security and connectivity issues during execution.

### **7. Production Tips**
*   **Monitoring Jobs:** Every import/export creates a **Job ID**. If a migration is taking hours (long-running), Data Engineers should provide this Job ID to the Admin team for investigation or optimization.
*   **Terminal Usage:** While a Web UI exists, Data Engineers primarily use the **Terminal/Shell** for verifying file systems and running operations.