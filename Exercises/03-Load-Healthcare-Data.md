# Exercise 03: Load Healthcare Data

[← Previous Exercise: Create Lakehouse](02-Create-Lakehouse.md) | [Home](../README.md) | [Next Exercise: Create Ontology →](04-Create-Ontology.md)

---

## Objective

Upload the 5 sample healthcare CSV datasets into the `LamnaHealthcareLH` lakehouse and convert them into Delta Lake tables for ontology binding.

---

## Steps

### Step 1: Upload CSV Files to Lakehouse
1. Open the `LamnaHealthcareLH` lakehouse in the Fabric portal.
2. In the left **Explorer** pane, hover over or click the ellipsis (`...`) next to the **Files** folder and select **Upload > Upload files**.
3. In the **Upload files** pane, click the folder icon to browse your local file system.
4. Select the 5 static reference CSV files from your local workshop `Data/` directory:
   - `hospitals.csv`
   - `departments.csv`
   - `rooms.csv`
   - `patients.csv`
   - `vitalsignequipment.csv`

> [!NOTE]
> **Why are there 6 CSV files in `sample-data.zip` / `Data/` directory?**
> - **5 Static Data Files** (`hospitals.csv`, `departments.csv`, `rooms.csv`, `patients.csv`, `vitalsignequipment.csv`): These store relational master data uploaded into the **Fabric Lakehouse** to construct the static entity nodes and graph relationships in the ontology.
> - **1 Time-Series Data File** (`vitalsignsreadings.csv`): Stores real-time telemetry streaming readings (heart rate, $\text{SpO}_2$, respiratory rate). In advanced ontology scenarios, time-series data is ingested into an **Eventhouse / KQL database** for real-time vital sign tracking rather than static lakehouse tables.

5. Click **Open** and then click **Upload**.
6. Wait for the upload to complete into the `Files` directory.

> [!NOTE]
> Add screenshot: Images/03-upload-csv.png

### Step 2: Convert CSV Files to Delta Tables
Convert each uploaded CSV file into a Lakehouse Delta table using the following configuration:

1. In the Explorer pane under **Files**, locate `hospitals.csv`.
2. Click the ellipsis (`...`) next to `hospitals.csv` and select **Load to Tables > New table**.
3. Configure the table load dialog:

| Setting | Value |
| :--- | :--- |
| **Table name** | `hospitals` |
| **Column header** | Check **Use header for column names** |
| **Separator** | Comma (`,`) |

4. Click **Load** and wait for table generation.

> [!NOTE]
> Add screenshot: Images/03-load-table-hospitals.png

5. Repeat the exact load process for the remaining 4 files:

| File Name | Target Table Name | Column Header | Separator |
| :--- | :--- | :--- | :--- |
| `departments.csv` | `departments` | Checked | Comma (`,`) |
| `rooms.csv` | `rooms` | Checked | Comma (`,`) |
| `patients.csv` | `patients` | Checked | Comma (`,`) |
| `vitalsignequipment.csv` | `vitalsignequipment` | Checked | Comma (`,`) |

---

## Validation

1. Expand the **Tables** folder in the Explorer pane.
2. Verify that all 5 tables appear in lowercase:
   - `hospitals`
   - `departments`
   - `rooms`
   - `patients`
   - `vitalsignequipment`
3. Click on the `patients` table to preview data rows. Verify that patient record `1001` (`Kerry Allen`) is displayed correctly.

> [!NOTE]
> Add screenshot: Images/03-tables-validation.png

---

## Expected Result

All 5 CSV datasets are converted into Delta Lake tables residing in `LamnaHealthcareLH`.

---

## Next Exercise

Proceed to [Exercise 04: Create Ontology](04-Create-Ontology.md).
