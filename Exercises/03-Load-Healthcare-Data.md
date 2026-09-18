# Exercise 03: Create an Eventhouse with Streaming Data

[← Previous Exercise: Create Lakehouse](02-Create-Lakehouse.md) | [Home](../README.md) | [Next Exercise: Create Ontology →](04-Create-Ontology.md)

---

## Objective

Create an Eventhouse named `LamnaHealthcareEH` and ingest real-time vital sign measurements from `VitalSignsReadings.csv` into a KQL database table for time-series ontology binding.

---

## Steps

### Step 1: Create Eventhouse Item
1. In your `LamnaHealthcareWS` workspace, select **+ New item > Eventhouse**.
2. Name the eventhouse `LamnaHealthcareEH` and select **Create**.
3. A default KQL database is created with the same name (`LamnaHealthcareEH`). Select the KQL database to open it.

### Step 2: Ingest Vital Signs Readings Data
1. In the KQL database, select **Get data > Local file**.
2. In the **Select or create a destination table** section, select **+ New table** and enter `VitalSignsReadings` as the table name.
3. Under **Add up to 1,000 files**, select **Browse for files** and upload the `VitalSignsReadings.csv` file.
4. Select **Next**, then continue through the ingestion wizard, keeping the default settings.
5. Select **Finish** to complete the ingestion.

---

## Validation

Verify that the `VitalSignsReadings` table appears in your KQL database as shown in the image below:

![VitalSignsReadings Table Ingested in KQL Database](../Images/timesseries.png)

---

## Expected Result

The `VitalSignsReadings` table containing 20 time-series rows is active in the `LamnaHealthcareEH` KQL database.

---

## Next Exercise

Proceed to [Exercise 04: Create Ontology](04-Create-Ontology.md).
