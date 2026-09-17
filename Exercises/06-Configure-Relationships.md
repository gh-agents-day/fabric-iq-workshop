# Exercise 06: Configure Relationships

[← Previous Exercise: Configure Entities](05-Configure-Entities.md) | [Home](../README.md) | [Next Exercise: Bind Ontology Data →](07-Bind-Ontology-Data.md)

---

## Objective

Model graph relationships between domain entities in `LamnaHealthcareOntology` to establish domain context and traversal capabilities.

---

## Steps

### Step 1: Create `contains` Relationship (Hospital → Department)
1. In the Ontology ribbon, click **Add relationship**.
2. Configure the relationship dialog:

| Setting | Value |
| :--- | :--- |
| **Relationship type name** | `contains` |
| **Origin entity type** | `Hospital` |
| **Target entity type** | `Department` |

3. Click **Create**. A connecting arrow labeled `contains` appears on the canvas.

> [!NOTE]
> Add screenshot: Images/06-relationship-contains.png

### Step 2: Create `has` Relationship (Department → Room)
1. Click **Add relationship** in the ribbon.
2. Configure settings:

| Setting | Value |
| :--- | :--- |
| **Relationship type name** | `has` |
| **Origin entity type** | `Department` |
| **Target entity type** | `Room` |

3. Click **Create**.

### Step 3: Create `assignedTo` Relationship (Patient → Room)
1. Click **Add relationship** in the ribbon.
2. Configure settings:

| Setting | Value |
| :--- | :--- |
| **Relationship type name** | `assignedTo` |
| **Origin entity type** | `Patient` |
| **Target entity type** | `Room` |

3. Click **Create**.

### Step 4: Create `monitors` Relationship (VitalSignEquipment → Patient)
1. Click **Add relationship** in the ribbon.
2. Configure settings:

| Setting | Value |
| :--- | :--- |
| **Relationship type name** | `monitors` |
| **Origin entity type** | `VitalSignEquipment` |
| **Target entity type** | `Patient` |

3. Click **Create**.

### Step 5: Create `locatedIn` Relationship (VitalSignEquipment → Room)
1. Click **Add relationship** in the ribbon.
2. Configure settings:

| Setting | Value |
| :--- | :--- |
| **Relationship type name** | `locatedIn` |
| **Origin entity type** | `VitalSignEquipment` |
| **Target entity type** | `Room` |

3. Click **Create**.

---

## Validation

Review the Ontology Canvas relationship graph. Verify that all 5 relationships are visually rendered:

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

> [!NOTE]
> Add screenshot: Images/06-relationship-graph.png

---

## Expected Result

The 5 semantic relationships are created, linking entity types into an interconnected domain graph.

---

## Next Exercise

Proceed to [Exercise 07: Bind Ontology Data](07-Bind-Ontology-Data.md).
