# Exercise 06: Configure Relationships

[← Previous Exercise: Configure Entities](05-Configure-Entities.md) | [Home](../README.md) | [Next Exercise: Bind Ontology Data →](07-Bind-Ontology-Data.md)

---

## Objective

Model graph relationships between domain entities in `LamnaHealthcareOntology` to establish domain context and traversal capabilities.

---

## Steps

### Step 1: Create `contains` Relationship (Hospital → Department)
1. In the ribbon, select **Add relationship**.
2. Configure the relationship dialog:
   - **Relationship type name**: `contains`
   - **Origin entity type**: `Hospital`
   - **Target entity type**: `Department`
3. Select **Create**. The `contains` relationship line connects `Hospital` to `Department`.

### Step 2: Create Remaining Relationships
Follow the same process to create these four additional relationships:

| Relationship Name | Origin Entity Type | Target Entity Type | Description |
| :--- | :--- | :--- | :--- |
| `has` | `Department` | `Room` | Department contains rooms |
| `assignedTo` | `Patient` | `Room` | Patient is assigned to a room |
| `monitors` | `VitalSignEquipment` | `Patient` | Equipment monitors patient |
| `locatedIn` | `VitalSignEquipment` | `Room` | Equipment is located in a room |

---

## Validation

Review the Ontology Canvas relationship graph. Verify that all 5 relationships are visually rendered connecting the entities:

```text
[Hospital] ───(contains)───► [Department] ───(has)───► [Room]
                                                         ▲         ▲
                                                         │         │
[Patient] ──────────────────(assignedTo)─────────────────┘         │
    ▲                                                              │
    │                                                              │
    └───────────────────────(monitors)─────────────────────────────┼── [VitalSignEquipment]
                                                                   │
                                                                   └───(locatedIn)
```

---

## Expected Result

The 5 semantic relationships are created, connecting entity types into an interconnected domain graph.

---

## Next Exercise

Proceed to [Exercise 07: Bind Ontology Data](07-Bind-Ontology-Data.md).
