# Exercise 07: Bind Ontology Data

[← Previous Exercise: Configure Relationships](06-Configure-Relationships.md) | [Home](../README.md) | [Next Exercise: Test Ontology →](08-Test-Ontology.md)

---

## Objective

Bind each entity type and relationship in `LamnaHealthcareOntology` to the corresponding Delta Lake tables in `LamnaHealthcareLH`.

---

## Steps

### Step 1: Bind Entity Types to Lakehouse Tables

For each entity type, perform the following binding steps:

#### 1. Bind `Hospital` Entity
1. Select the `Hospital` entity on the canvas, select the ellipsis (`...`) next to its name, and select **Bind data**.
2. Select **Add data binding > Lakehouse table**.
3. Select `LamnaHealthcareLH` and select **Next**.
4. Select the `hospitals` table and select **Select**.
5. Keep **Static** binding type.
6. Verify property mappings:
   - Key: `HospitalId` → `HospitalId`
   - Properties: `HospitalName` → `HospitalName`, `City` → `City`, `State` → `State`
7. Select **Save**.

#### 2. Bind `Department`, `Room`, `Patient`, and `VitalSignEquipment`
Follow the same process for the remaining four entities:

- **`Department`**: Bind to `departments` table. Map `DepartmentId` key and properties (`DepartmentName`, `HospitalId`, `Floor`).
- **`Room`**: Bind to `rooms` table. Map `RoomId` key and properties (`RoomNumber`, `DepartmentId`, `RoomType`).
- **`Patient`**: Bind to `patients` table. Map `PatientId` key and properties (`FirstName`, `LastName`, `DateOfBirth`, `AdmissionDate`, `CurrentRoomId`).
- **`VitalSignEquipment`**: Bind to `vitalsignequipment` table. Map `EquipmentId` key and properties (`PatientId`, `EquipmentType`, `MonitoringStartDate`, `RoomId`).

---

### Step 2: Configure Relationship Key Mappings

Configure the matching key columns for each relationship line on the canvas:

| Relationship Name | Origin Entity | Target Entity | Column Mapping |
| :--- | :--- | :--- | :--- |
| `contains` | `Hospital` | `Department` | `HospitalId` = `HospitalId` |
| `has` | `Department` | `Room` | `DepartmentId` = `DepartmentId` |
| `assignedTo` | `Patient` | `Room` | `CurrentRoomId` = `RoomId` |
| `monitors` | `VitalSignEquipment` | `Patient` | `PatientId` = `PatientId` |
| `locatedIn` | `VitalSignEquipment` | `Room` | `RoomId` = `RoomId` |

1. On the canvas, select the `contains` relationship line between `Hospital` and `Department`.
2. Configure origin and target entity key mappings (`HospitalId` → `HospitalId`). Select **Save**.
3. Repeat key binding for `has`, `assignedTo`, `monitors`, and `locatedIn` relationships.

---

## Validation

1. Verify that bound status icons appear next to all 5 entities in the Explorer pane.
2. Confirm that all 5 relationship lines show configured mapping indicators.

---

## Expected Result

All entities and relationships are bound to physical Delta tables in `LamnaHealthcareLH`.

---

## Next Exercise

Proceed to [Exercise 08: Test Ontology](08-Test-Ontology.md).
