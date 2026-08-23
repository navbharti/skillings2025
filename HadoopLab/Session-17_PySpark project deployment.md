# PySpark project deployment using Git/GitHub 

### **1. Introduction to Project Deployment**
Deployment is the process of moving analyzed and tested code from a local environment (like Visual Studio Code) to a centralized repository for organizational use. In PySpark, this follows the transition from code development (using RDDs in Spark Core or DataFrames in Spark SQL) to a production-ready state.

### **2. Version Control with Git and GitHub**
**GitHub** acts as a centralized cloud-based platform for storing project repositories, while **Git** is the local tool used to access and manage those repositories.

*   **GitHub Setup:** 
    *   Users must sign up or sign in to [github.com](http://github.com).
    *   **New Repository:** Created by providing a unique name (e.g., `DataEngineering_August2025`) and a project-relevant description.
    *   **Repository Link:** Every repository is identified by a unique HTTPS link used for cloning.
*   **Git Installation:** To interact with GitHub from a local machine, Git for Windows must be installed using default settings. Verification is done by typing `git` in the terminal to see "Git Bash".

#### **Core Git Commands for Deployment:**
*   **`git clone [URL]`:** Copies the cloud repository to a local folder.
*   **`git add .`:** Stages all new files or changes for a commit.
*   **`git commit -m "[message]"`:** Labels the changes with a descriptive message to identify what was modified (e.g., "New Data Frame Created").
*   **`git push origin [branch]`:** Uploads the local commits to the specified branch (e.g., `main`, `dev`, or `SIT`) on GitHub.

---

### **3. Professional Development Scenarios**
Data Engineers typically encounter two main deployment scenarios:

*   **Scenario 1: Starting from Scratch:** Creating a completely new repository for a new project, adding initial test files (e.g., `test_data.py`), and pushing them to the main branch.
*   **Scenario 2: Modifying Existing Code:** Cloning an existing organizational repository, importing the project into VS Code, making required code changes, testing them locally, and pushing them back to the repository.

---

### **4. Real-World Agile Workflow (Jira & Approvals)**
In a corporate environment, code changes are triggered by tasks assigned through tools like **Jira** or **ServiceNow**.

*   **Ticketing:** A Scrum Master assigns a **Jira ticket** (Task) or **Service Request (SR)** containing specific requirements, such as adding a new column to a DataFrame or changing a calculation.
*   **Development Practice:** It is standard practice to create a **new local folder for every Jira ticket** to keep different tasks and code versions organized and identifiable.
*   **Approval Process:** 
    *   Developers do not usually have direct access to merge code into the **Main (Production) branch**.
    *   Once a developer pushes code to a feature or testing branch (like **SIT** or **Dev**), a **two-way approval** is required from the **Architect/Lead** and the **DevOps team**.
    *   Code is only merged into the Main branch after business approval and verification of test evidence.

---

### **5. Technical Case Study: The FRS (Finance) Project**
The **Financial Regulatory System (FRS)** project is a practical application of the ETL process following **IFRS 9** templates used by investment banks (e.g., HSBC, Citi) to calculate risk.

#### **ETL Pipeline Breakdown:**
1.  **Extract:** Data is fetched from **SAP locations**. Three raw DataFrames are created: `Model_Collateral_Raw`, `Model_Auth_Raw`, and `Model_Config_Raw`.
2.  **Validate:** Standard data quality checks are applied, including **null value checks**, **duplicate removal**, and counting rows/columns.
3.  **Transform (ECL Reporting):** Generates reports based on **Expected Credit Loss (ECL)** using three stages of calculations:
    *   **Stage 1:** `EAD * PD1 * LGD`
    *   **Stage 2:** `EAD * PDLT * LGD`
    *   **Stage 3:** `EAD * LGD`
4.  **Transform (EAD Variation):** Calculates the change and percentage change in **Exposure at Default (EAD)** compared to previous records.
5.  **Load:** The final calculated reports (ECL and EAD Difference) are written to **local Excel files** for business review.

