# Session-2: Hadoop / HDFS Introduction

### **1. Introduction to Big Data and Hadoop**
Hadoop is a framework designed to handle **Big Data**, which includes structured, semi-structured, and unstructured data.
*   **Comparison with Traditional Databases:** Traditional databases like MySQL and Oracle primarily process structured data, whereas Hadoop supports all three data formats.
*   **Key Features of Hadoop:**
    *   **Distributed Storage and Processing:** Unlike traditional systems that store data serially, Hadoop distributes data across multiple nodes for storage and processing, significantly reducing processing time.
    *   **Scalability and Cost-Effectiveness:** It is highly scalable and open-source, making it a cost-effective solution for large-scale data.
    *   **Fault Tolerance and High Availability:** Hadoop ensures data reliability through **replication**. If a data node fails, the system can recover data from its replica on another node.

### **2. Hadoop Ecosystem and Architecture**
Hadoop follows a **Master-Slave architecture** consisting of three primary technologies:

*   **HDFS (Hadoop Distributed File System):** The storage layer used to store large volumes of data.
*   **YARN (Yet Another Resource Negotiator):** Used for job scheduling and resource management across the cluster.
*   **MapReduce:** A programming model and backend framework used for parallel data analysis.

#### **Verification of Hadoop Services**
After installation, running the `jps` command should confirm the following five essential services are active:
1.  **NameNode** (HDFS Service)
2.  **DataNode** (HDFS Service)
3.  **Secondary NameNode** (HDFS Service)
4.  **Resource Manager** (MapReduce/YARN Service)
5.  **Node Manager** (MapReduce/YARN Service)

### **3. HDFS Architecture and Components**
HDFS splits large files into **blocks** (typically 128 MB) and replicates them across multiple data nodes.
*   **NameNode (Master):** Maintains **metadata**, including file names, permissions, and the physical locations of data blocks.
*   **DataNode (Slave):** Stores the actual data within the data blocks.
*   **Secondary NameNode:** Assists the NameNode by maintaining checkpoints; it is important to note that this is **not a backup** for the NameNode.

### **4. YARN Components**
YARN manages resources globally and at the individual node level:
*   **Resource Manager:** Manages cluster resources (NameNodes and DataNodes) globally.
*   **Node Manager:** Manages resources on individual server nodes.
*   **Application Master:** Manages the execution of specific applications or codes.
*   **Containers:** Represent the allocated resources, such as CPU and memory, required to run a job.

### **5. MapReduce Framework**
MapReduce processes data in two main phases:
*   **Map Phase:** Processes the input data.
*   **Reduce Phase:** Aggregates the output received from the Map phase.
While MapReduce was the original processing engine, it has largely been replaced in modern workflows by **PySpark**.

### **6. HDFS Operations and Commands**
HDFS operates on a directory-based file system (Directory > Sub-directory > File > Data). It is a separate storage area from the host Linux operating system.

| Task | HDFS Command |
| :--- | :--- |
| **Create Directory** | `bin/hdfs dfs -mkdir /directory_name` |
| **List Files/Dirs** | `bin/hdfs dfs -ls /` (use `-lsr` for recursive list) |
| **Upload from Linux** | `bin/hdfs dfs -put /local_source /hdfs_destination` |
| **Download to Linux** | `bin/hdfs dfs -get /hdfs_source /local_destination` |
| **View File Content** | `bin/hdfs dfs -cat /file_path` |
| **Remove File** | `bin/hdfs dfs -rm /file_path` |
| **Remove Directory** | `bin/hdfs dfs -rm -r /directory_path` |
| **Copy (HDFS to HDFS)** | `bin/hdfs dfs -cp /source /destination` |
| **Move (HDFS to HDFS)** | `bin/hdfs dfs -mv /source /destination` |
| **Check Size** | `bin/hdfs dfs -du /directory_path` |
| **Check Drive Space** | `bin/hdfs dfs -df` |
| **Change Permissions** | `bin/hdfs dfs -chmod 755 /path` |

### **7. Learning Roadmap and Prerequisites**
Hadoop serves as the foundational prerequisite for many modern Big Data tools:
*   **Sequence:** Hadoop > Hive/Sqoop > PySpark > Cloud Services (AWS Glue, Azure Data Factory).
*   Understanding HDFS is essential for working with cloud storage like **AWS S3**, as the logical operations are similar.