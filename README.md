# FixFox-A-Dataset-on-Mozilla-Firefox-Vulnerabilities-and-Fixes

The **FixFox dataset** is provided as a `.bacpac` file for portability and compatibility across different SQL Server versions and environments. This repository includes instructions for importing and verifying the dataset for research and development purposes.

---

## Dataset Details

| **Property**                 | **Value**                           |
| ---------------------------- | ----------------------------------- |
| **Database Name**            | `FixFox`                            |
| **File Provided**            | `FixFox.bacpac`                     |
| **SQL Server Compatibility** | Level 160                           |
| **Collation**                | `SQL_Latin1_General_CP1_CI_AS`      |
| **Database Size**            | 144.00 MB (Data) + 47.59 MB (Index) |
| **SQL Server Version**       | Microsoft SQL Server 2022 (RTM)     |

---

### Key Points:

- **SQL Server Version**: The dataset is compatible with **SQL Server 2022** (RTM).
- **Compatibility Level**: Set to **160**, ensuring compatibility with SQL Server 2022.
- **Collation**: Uses **SQL_Latin1_General_CP1_CI_AS**, which is the default collation for SQL Server.
- **Database Size**: The dataset has a size of **144.00 MB** for data and **47.59 MB** for index space.

---

## Dataset Schema

![FixFox_Diagram](https://github.com/user-attachments/assets/dfa21d28-4f3e-4802-b527-08048bd1ae99)

---

## Tools Required

To access the FixFox dataset, the following tools are recommended:

### 1. Microsoft SQL Server Management Studio (SSMS)

- **Purpose**: Import `.bacpac` file and query the dataset.
- **Download**: [SSMS Download Page](https://learn.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)
- **Guide**: Refer to the "Importing the Dataset" section below.

### 2. SQL Server Developer Edition

- **Purpose**: Host the database locally if you don't have an existing SQL Server instance.
- **Download**: [SQL Server Developer Edition](https://www.microsoft.com/sql-server/sql-server-downloads)

### 3. Python Libraries

To run the example notebooks, ensure you have the required Python libraries installed. The dependencies are listed in the `requirements.txt` file. Install them using the following command:

```bash
pip install -r Usage\ Examples/requirements.txt
```

---

## Import Instructions

Follow these steps to import the `FixFox.bacpac` file:

### 1. Launch SSMS

- Open SQL Server Management Studio (SSMS) and connect to your SQL Server instance.

### 2. Start the Import Process

- Right-click on the **Databases** folder in the Object Explorer pane.
- Select **Import Data-tier Application**.

### 3. Select the .bacpac File

- In the Import Wizard:
  - Click **Next**.
  - Select **Import from local disk** and locate the provided `FixFox.bacpac` file.
  - Click **Next**.

### 4. Configure Import Settings

- Specify the database name as `FixFox` (or use your preferred name).
- Adjust server-specific configurations if needed (e.g., storage location).

### 5. Begin Import

- Click **Finish** to start the import process.
- Once completed, a success message will appear.

---

## Post-Import Verification

Run the following queries in SSMS to verify the database configuration and dataset size:

### Verify Database Properties

```sql
USE FixFox; -- Replace if a different name was used
SELECT compatibility_level FROM sys.databases WHERE name = 'FixFox';
SELECT collation_name FROM sys.databases WHERE name = 'FixFox';
```
