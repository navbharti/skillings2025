# Session-4: Mapreduce Architecture

### **1. Overview of MapReduce**
*   **Definition:** MapReduce is a processing technique used primarily for **data analysis**.
*   **Role in Hadoop Ecosystem:** It serves as the backend engine for various tools. For example, when using **Sqoop**, MapReduce processes Linux commands in the background. In **Hive**, SQL-like queries (HiveQL) are converted into MapReduce jobs for execution.
*   **Purpose:** While HDFS is responsible for data storage, MapReduce is the component that performs the analysis and logic on that stored data.

---

### **2. The MapReduce Architecture: Two Primary Phases**
The MapReduce process is internally divided into two main stages: the **Mapping Phase** and the **Reducing Phase**.

#### **A. The Mapping Phase**
This phase prepares the data for analysis by breaking it down into manageable chunks.
1.  **Input Split:** When a query is run against a large file (e.g., 400 MB), the file is already split into chunks across different DataNodes in HDFS. These are called **Input Splits**.
2.  **Record Reader:** Every input split has a corresponding Record Reader. Its job is to read the data from the split and convert it into a format consisting of a **Byte Offset (Address)** and the **Entire Line (Record)**.
3.  **Map Block:** The output from the Record Reader goes to a Map Block. The Map Block assigns a **Key-Value pair** to the data. Typically, the entire record/line is treated as the "Key," and a static "Value" of **1** is assigned to each.
    *   *Scale Rule:* The number of Input Splits = Number of Record Readers = Number of Map Blocks.

#### **B. The Reducing Phase**
This phase aggregates the results generated during mapping.
1.  **Combiner:** Each Map Block has a corresponding Combiner. It performs local aggregation to reduce the amount of data sent over the network. If a record appears multiple times in a single map block, the Combiner sums those values (e.g., changing two entries of `(Name, 1)` into one entry of `(Name, 2)`).
2.  **Reducer:** There is only **one Reducer** per process. It collects the outputs from all combiners across the cluster and performs the final global aggregation to provide the ultimate count or result.
3.  **Output:** The Reducer generates two items:
    *   **Part File:** A text file containing the final analyzed results.
    *   **Success Message:** A notification indicating the process completed successfully.

---

### **3. Production Cluster Architecture**
In a production environment, MapReduce operates through two specialized services that manage resources and tasks.

*   **ResourceManager (Master):** The central authority that receives job requests. It communicates with the **NameNode** to find out which DataNodes contain the required data.
*   **NodeManager (Slave):** Every DataNode has its own NodeManager. It receives specific tasks from the ResourceManager and executes them on the local data.

#### **The Execution Workflow:**
1.  The user runs a query (e.g., a SQL `GROUP BY` or `COUNT`).
2.  The **ResourceManager** identifies the data locations via the **NameNode**.
3.  **NodeManagers** on those specific nodes apply the task to the local data.
4.  Each node provides a solution (Solution 1, Solution 2, etc.) back to the **ResourceManager**.
5.  The **Reducer** (located within the ResourceManager's scope) combines these solutions into the final **Part File**.

---

### **4. Key Logic Summary for Interviews**
*   **HDFS vs. MapReduce:** HDFS is for storage; MapReduce is for analysis.
*   **Quantity Ratios:** Number of Input Splits = Number of Mappers = Number of Record Readers = Number of Combiners. However, there is **only one Reducer**.
*   **Fault Tolerance:** The process is designed to be successful and provides a "Success Message" only when all mapping and reducing steps are completed across the multi-node cluster.