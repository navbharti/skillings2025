# Hadoop 2.7.3 Installation on an **Ubuntu** operating system within a virtualized environment


### **1. Hardware and Software Prerequisites**
*   **System Requirements:** A minimum of **8GB RAM** is required for the laptop to prevent hanging; 4GB is insufficient.
*   **Virtualization Software:** Either **VMware Workstation** (Version 15 is used in the session) or Oracle VirtualBox is required to run Linux on Windows.
*   **Operating System:** **Ubuntu** is the only supported Linux distribution for this setup (a 5.9GB ISO file).
*   **Hadoop Version:** **Hadoop 2.7.3** (approximately 204 MB).
*   **Disk Space:** At least **20GB** should be allocated from the hard drive for the Ubuntu installation.

### **2. Environment Setup (VMware & Ubuntu)**
*   **Installation:** Standard software installation process for VMware; no special configurations are needed during the initial wizard.
*   **Creating the Virtual Machine (VM):**
    *   Browse and select the Ubuntu ISO path.
    *   **Naming Convention:** Use lowercase letters for the username (e.g., "swipe") and a simple password like "**admin**".
    *   **Import Process:** The initial OS import and installation can take between **45 minutes to over an hour**.
*   **Basics of Linux Usage:** Nearly all operations are performed via the **Terminal** (right-click -> Open in Terminal).

### **3. Java Installation (Prerequisite)**
Hadoop requires Java to function. The session utilizes **Java 8 (OpenJDK 8)**.
*   **Verification:** Check if Java is present using `java -version`. If not found, proceed to installation.
*   **Installation Commands:**
    *   `sudo apt-get update`
    *   `sudo apt-get install openjdk-8-jdk`.
*   **Location:** Once installed, Java files are typically found in `/usr/lib/jvm/java-8-openjdk-amd64`.

### **4. Hadoop Installation and Environment Configuration**
*   **Preparation:** Download and extract the `hadoop-2.7.3.tar.gz` file to the Home directory.
*   **Setting Paths (.bashrc):**
    *   Paths for both `JAVA_HOME` and `HADOOP_HOME` must be added to the `.bashrc` file (accessed via `sudo gedit ~/.bashrc`).
    *   Use the `source ~/.bashrc` command to refresh the configuration after saving.
*   **SSH Setup:** Secure Shell (SSH) must be configured for the local host to allow Hadoop services to communicate.

### **5. Configuration of Hadoop Files**
Specific changes are required in five key configuration files located in the `etc/hadoop` folder:
1.  **hadoop-env.sh:** Manually set the `JAVA_HOME` path on line 25.
2.  **core-site.xml:** Define the default file system property.
3.  **hdfs-site.xml:** Configure HDFS replication properties.
4.  **mapred-site.xml:** (Renamed from the template file) Set the framework name to `yarn`.
5.  **yarn-site.xml:** Configure auxiliary services.

### **6. Starting and Verifying Hadoop**
*   **Formatting the NameNode:** Before starting Hadoop for the first time, the NameNode must be formatted using `bin/hadoop namenode -format`.
*   **Starting Services:** Use the command `sbin/start-all.sh` to launch all Hadoop daemons.
*   **Verification (JPS Command):** Running the `jps` command should show **five essential services**:
    1.  NameNode
    2.  DataNode
    3.  SecondaryNameNode
    4.  ResourceManager
    5.  NodeManager

### **7. System Maintenance**
*   **Graceful Shutdown:** Always use "**Shut Down Guest**" in VMware rather than just closing the window to avoid corruption.
*   **Performance Optimization:** Unnecessary software should be uninstalled from the host Windows machine to free up resources for the VM.
*   **Resource Adjustment:** If the VM is slow, RAM can be increased up to 4GB in the "Edit Virtual Machine Settings" menu.