# Exercise 02: Create Lakehouse

[← Previous Exercise: Create Fabric Workspace](01-Create-Fabric-Workspace.md) | [Home](../README.md) | [Next Exercise: Load Healthcare Data →](03-Load-Healthcare-Data.md)

---

## Objective

Provision a Microsoft Fabric Lakehouse named `LamnaHealthcareLH` inside the `LamnaHealthcareWS` workspace to store structured healthcare tables.

---

## Steps

### Step 1: Create Lakehouse Item
1. Open the `LamnaHealthcareWS` workspace in the Microsoft Fabric portal.
2. Select **+ New item**.
3. In the item list, select **Lakehouse**.

### Step 2: Configure Lakehouse Properties
1. In the **New lakehouse** dialog box, enter the lakehouse name:

```text
LamnaHealthcareLH
```

2. Select **Create**.

### Step 3: Verify Lakehouse Provisioning
1. Fabric will open the Lakehouse editor interface.
2. Verify that the Explorer pane displays two main folders:
   - **Tables**: Stores Delta Lake tables used for Fabric IQ Ontology bindings.
   - **Files**: Stores raw unmanaged files (CSVs).

---

## Validation

1. Navigate back to the `LamnaHealthcareWS` workspace view.
2. Confirm that the `LamnaHealthcareLH` lakehouse item is listed.

---

## Expected Result

The `LamnaHealthcareLH` lakehouse is successfully provisioned and ready to receive healthcare datasets.

---

## Next Exercise

Proceed to [Exercise 03: Load Healthcare Data](03-Load-Healthcare-Data.md).
