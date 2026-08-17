# Session-3: HDFS commands / Production cluster

Discusse a deep dive into practical Hadoop operations, focusing on the commands used to manage the **Hadoop Distributed File System (HDFS)** and the underlying architectural principles that govern a production cluster.

### **1. Environment Setup and Initialization**
*   **Virtual Machine Tuning:** For a smoother experience, it is recommended to increase the VM RAM from **2GB to 4GB** in the settings.
*   **Starting Hadoop:** Access the Hadoop terminal and run the command `start-all.sh` to initialize the five core services.
*   **Verification:** Use the `jps` command to ensure the following services are active:
    1.  **NameNode** (Master for metadata).
    2.  **DataNode** (Slave for actual data storage).
    3.  **Secondary NameNode** (Assists NameNode).
    4.  **ResourceManager** (YARN master).
    5.  **NodeManager** (YARN slave).

### **2. Core HDFS Commands**
HDFS and Linux are separate storage environments; Linux commands like `cd` or standard file manipulation do not work directly inside HDFS.

#### **A. Directory & File Management**
*   **Create Directory:** `bin/hdfs dfs -mkdir /dir_name`.
*   **List Files:** `bin/hdfs dfs -ls /path` (Use `-lsr` for recursive listing of all sub-directories and files).
*   **Copy (HDFS to HDFS):** `bin/hdfs dfs -cp /source /destination`.
*   **Move/Cut (HDFS to HDFS):** `bin/hdfs dfs -mv /source /destination`.
*   **Remove File:** `bin/hdfs dfs -rm /file_path`.
*   **Remove Directory:** `bin/hdfs dfs -rm -r /dir_path`.

#### **B. Data Transfer**
*   **Upload (Linux to HDFS):** `bin/hdfs dfs -put /local_source /hdfs_destination`.
*   **Download (HDFS to Linux):** `bin/hdfs dfs -get /hdfs_source /local_destination`.

#### **C. Data Inspection & Analysis**
*   **View Full Content:** `bin/hdfs dfs -cat /file_path`.
*   **View Top 10 Lines:** `cat` piped to `head` (e.g., `cat file | head -n 10`).
*   **View Bottom Lines:** `tail` command.
*   **Check Size:** `bin/hdfs dfs -du /path` (Returns size in **bytes**).
*   **Detailed Count:** `bin/hdfs dfs -count /path` (Shows number of directories, files, and total size).

### **3. Production Cluster Architecture**
In an industry setting, a separate **Hadoop Admin team** handles installation and configuration, while Data Engineers focus on running commands and processing data.

#### **A. Master-Slave Dynamics**
*   **NameNode (Master):** Stores **Metadata** in a "Register" format. This includes file names, sizes, permissions, and the specific DataNodes where blocks are stored.
*   **DataNode (Slave):** Physical servers (often in TBs) that store the actual data blocks.

#### **B. The Concept of Blocks**
*   **Definition:** HDFS splits large files into "chunks" called blocks.
*   **Default Size:** In Hadoop 2.x, the default size is **128 MB** (it was 64 MB in Hadoop 1.x).
*   **Example:** A 400 MB file will be split into **4 blocks** (3 blocks of 128 MB and 1 remainder block).

### **4. Fault Tolerance and Reliability**
Hadoop is designed to be highly available even if hardware fails.

*   **Replication:** By default, Hadoop creates **3 replicas** of every block. A 400 MB file actually consumes 1200 MB of physical space across the cluster to ensure safety.
*   **DataNode Failure:** If a DataNode crashes, the NameNode detects this and redirects "get" requests to one of the remaining replicas on other nodes.
*   **NameNode Failure:** A **Standby (Passive) NameNode** is configured to take over if the Active NameNode fails, generating its own metadata to keep the cluster running.
*   **Heartbeats:** Every **30 seconds**, DataNodes send a "Heartbeat" and a "Block Report" to the NameNode to confirm they are "alive" and to update the metadata.

### **5. Key Comparisons and Limitations**
*   **HDFS vs. Cloud (S3):** While similar in logic (Buckets/Folders/Files), HDFS is often on-premise and open-source, whereas S3 is a managed, paid cloud service.
*   **Storage vs. Processing:** HDFS is strictly for **storage**. It does not allow for editing or changing file content once saved; analytical tools like Hive or Spark are used for processing.
*   **Scalability:** You cannot store data exceeding the cluster's physical capacity (e.g., a 20 TB file cannot fit in a 10 TB architecture without adding more nodes).