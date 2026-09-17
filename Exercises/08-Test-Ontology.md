# Exercise 08: Test Ontology

[← Previous Exercise: Bind Ontology Data](07-Bind-Ontology-Data.md) | [Home](../README.md) | [Next Exercise: Create Foundry Project →](09-Create-Foundry-Project.md)

---

## Objective

Validate `LamnaHealthcareOntology` schemas, inspect graph connections via the Relationship Graph, and run graph queries using the Fabric IQ Query Builder focused on `PatientId 1001`.

---

## Steps

### Step 1: Save and Validate Ontology Schema
1. In the `LamnaHealthcareOntology` top ribbon, click **Save**.
2. Click **Validate** to trigger schema integrity checks.
3. Verify that zero compilation warnings or unmapped property errors are returned.

> [!NOTE]
> Add screenshot: Images/08-validate-ontology.png

### Step 2: Test Entity Graph Traversal (Relationship Graph)
1. Select the `Patient` entity node on the canvas.
2. Click **Entity type overview** (or **Preview data**).
3. Wait 1-2 minutes for background indexing to complete if prompted.
4. Select instance `PatientId 1001` (`Kerry Allen`).
5. Observe the interactive **Relationship Graph** view for Patient 1001:
   - Traverses to `Room 1` (`ICU-301`) via `assignedTo`.
   - Traverses to `VitalSignEquipment VS-1001` via `monitors`.

> [!NOTE]
> Add screenshot: Images/08-relationship-graph-1001.png

### Step 3: Run Traversal Queries in Query Builder
1. Click **Query Builder** in the top ribbon.
2. Construct a graph traversal query for `PatientId 1001`:

```text
FIND Patient WHERE PatientId = 1001
  MATCH (Patient)-[assignedTo]->(Room)
  MATCH (VitalSignEquipment)-[monitors]->(Patient)
  MATCH (Department)-[has]->(Room)
```

3. Click **Run Query**.

> [!NOTE]
> Add screenshot: Images/08-query-builder-patient1001.png

---

## Validation

Review the Query Builder output table for `PatientId 1001`:

| Field | Returned Value |
| :--- | :--- |
| **PatientId** | `1001` |
| **Patient Name** | Kerry Allen |
| **Assigned Room** | `1` (RoomNumber: `ICU-301`, Type: `Critical Care`) |
| **Department** | `1` (Intensive Care Unit, Floor 3) |
| **Monitoring Equipment** | `VS-1001` (Continuous Monitoring) |

---

## Expected Result

`PatientId 1001` correctly resolves across all graph relationship hops (`Patient` → `Room` → `Equipment` → `Department`).

---

## Next Exercise

Proceed to [Exercise 09: Create Foundry Project](09-Create-Foundry-Project.md).
