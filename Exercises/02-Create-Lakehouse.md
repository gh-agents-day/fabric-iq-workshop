# Exercise 02: Create Lakehouse

[← Previous Exercise: Create Fabric Workspace](01-Create-Fabric-Workspace.md) | [Home](../README.md) | [Next Exercise: Load Healthcare Data →](03-Load-Healthcare-Data.md)

---

## Objective

Provision a Microsoft Fabric Lakehouse named `LamnaHealthcareLH` inside the `LamnaHealthcareWS` workspace to store structured healthcare tables.

---

## Steps

### Step 1: Create Lakehouse Item
1. Open the `LamnaHealthcareWS` workspace in the Microsoft Fabric portal.
2. In the top action ribbon, click **+ New item**.
3. In the item gallery, locate and select **Lakehouse**.

> [!NOTE]
> Add screenshot: Images/02-new-item-lakehouse.png

### Step 2: Configure Lakehouse Properties
1. In the **New lakehouse** dialog box, enter the lakehouse name:

```text
LamnaHealthcareLH
```

2. Leave **Schemas (preview)** unchecked (or keep default schema configuration as recommended for your tenant).
3. Click **Create**.

> [!NOTE]
> Add screenshot: Images/02-create-lakehouse.png

### Step 3: Verify Lakehouse Provisioning
1. Fabric will initialize the Lakehouse editor interface.
2. Verify that the left explorer pane displays two root folders:
   - **Tables**: Stores Delta Lake tables used for Fabric IQ Ontology bindings.
   - **Files**: Stores raw unmanaged files (CSVs, JSON, Parquet).

---

## Validation

1. Navigate back to the `LamnaHealthcareWS` workspace view.
2. Confirm that the following items are created:
   - `LamnaHealthcareLH` (Lakehouse)
   - `LamnaHealthcareLH` (SQL analytics endpoint)
   - `LamnaHealthcareLH` (Semantic model)

---

## Expected Result

The `LamnaHealthcareLH` lakehouse is successfully provisioned and ready to receive healthcare datasets.

---

## Next Exercise

Proceed to [Exercise 03: Load Healthcare Data](03-Load-Healthcare-Data.md).
