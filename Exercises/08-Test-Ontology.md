# Exercise 08: Test Ontology

[← Previous Exercise: Bind Ontology Data](07-Bind-Ontology-Data.md) | [Home](../README.md) | [Next Exercise: Create Foundry Project →](09-Create-Foundry-Project.md)

---

## Objective

Validate `LamnaHealthcareOntology` schemas, inspect graph connections via the Relationship Graph, and run graph queries using the Fabric IQ Query Builder focused on `PatientId 1001`.

---

## Steps

### Step 1: Save and Preview Ontology
1. In the `LamnaHealthcareOntology` ribbon, select **Save**.
2. Select **Room** (or **Patient**) from the Entity Types list.
3. In the ontology ribbon, select **Entity type overview**.
4. After background processing completes, refresh the browser page to display the entity overview.
5. Review the overview sections:
   - **Relationship graph**: Visual representation connecting `Patient`, `Room`, `Department`, and `VitalSignEquipment`.
   - **Property charts**: Value distributions for entity properties.
   - **Entity instances table**: List of individual records.

### Step 2: Test Entity Graph Traversal
1. Select instance `PatientId 1001` (`Kerry Allen`).
2. Observe the interactive **Relationship Graph** view for Patient 1001:
   - Traverses to `Room 1` (`ICU-301`) via `assignedTo`.
   - Traverses to `VitalSignEquipment VS-1001` via `monitors`.

### Step 3: Run Traversal Queries in Query Builder
1. Select **Query Builder** in the ribbon.
2. Construct a graph traversal query for `PatientId 1001`:

```text
FIND Patient WHERE PatientId = 1001
  MATCH (Patient)-[assignedTo]->(Room)
  MATCH (VitalSignEquipment)-[monitors]->(Patient)
  MATCH (Department)-[has]->(Room)
```

3. Select **Run Query**.

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
