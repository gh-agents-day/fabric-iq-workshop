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
1. Select the `Hospital` node on the canvas, click the ellipsis (`...`), and select **Bind data**.
2. Click **Add data binding > Lakehouse table**.
3. Select `LamnaHealthcareLH` and click **Next**.
4. Select the `hospitals` table and click **Select**.
5. Set Binding type to **Static**.
6. Verify auto-mapped properties:
   - Key: `HospitalId` → `HospitalId`
   - Properties: `HospitalName` → `HospitalName`, `City` → `City`, `State` → `State`
7. Click **Save**.

> [!NOTE]
> Add screenshot: Images/07-bind-hospital.png

#### 2. Bind `Department` Entity
1. Select `Department` node > **Bind data > Add data binding > Lakehouse table**.
2. Select `LamnaHealthcareLH` > `departments` table.
3. Verify mappings:
   - Key: `DepartmentId` → `DepartmentId`
   - Properties: `DepartmentName` → `DepartmentName`, `HospitalId` → `HospitalId`, `Floor` → `Floor`
4. Click **Save**.

#### 3. Bind `Room` Entity
1. Select `Room` node > **Bind data > Add data binding > Lakehouse table**.
2. Select `LamnaHealthcareLH` > `rooms` table.
3. Verify mappings:
   - Key: `RoomId` → `RoomId`
   - Properties: `RoomNumber` → `RoomNumber`, `DepartmentId` → `DepartmentId`, `RoomType` → `RoomType`
4. Click **Save**.

#### 4. Bind `Patient` Entity
1. Select `Patient` node > **Bind data > Add data binding > Lakehouse table**.
2. Select `LamnaHealthcareLH` > `patients` table.
3. Verify mappings:
   - Key: `PatientId` → `PatientId`
   - Properties: `FirstName` → `FirstName`, `LastName` → `LastName`, `DateOfBirth` → `DateOfBirth`, `AdmissionDate` → `AdmissionDate`, `CurrentRoomId` → `CurrentRoomId`
4. Click **Save**.

> [!NOTE]
> Add screenshot: Images/07-bind-patient.png

#### 5. Bind `VitalSignEquipment` Entity
1. Select `VitalSignEquipment` node > **Bind data > Add data binding > Lakehouse table**.
2. Select `LamnaHealthcareLH` > `vitalsignequipment` table.
3. Verify mappings:
   - Key: `EquipmentId` → `EquipmentId`
   - Properties: `PatientId` → `PatientId`, `EquipmentType` → `EquipmentType`, `MonitoringStartDate` → `MonitoringStartDate`, `RoomId` → `RoomId`
4. Click **Save**.

---

### Step 2: Configure Relationship Key Mappings

Configure the matching keys for each relationship line:

| Relationship Name | Origin Entity | Target Entity | Foreign Key Column Mapping |
| :--- | :--- | :--- | :--- |
| `contains` | `Hospital` | `Department` | `Hospital.HospitalId` = `Department.HospitalId` |
| `has` | `Department` | `Room` | `Department.DepartmentId` = `Room.DepartmentId` |
| `assignedTo` | `Patient` | `Room` | `Patient.CurrentRoomId` = `Room.RoomId` |
| `monitors` | `VitalSignEquipment` | `Patient` | `VitalSignEquipment.PatientId` = `Patient.PatientId` |
| `locatedIn` | `VitalSignEquipment` | `Room` | `VitalSignEquipment.RoomId` = `Room.RoomId` |

1. On the canvas, click the `contains` relationship line.
2. Set Origin key `HospitalId` to match Target foreign key `HospitalId`. Click **Save**.
3. Repeat key binding for `has`, `assignedTo`, `monitors`, and `locatedIn` relationships.

---

## Validation

1. Verify that a green checkmark or "Bound" status appears next to all 5 entities in the Explorer pane.
2. Confirm that all 5 relationship lines show configured mapping indicators without missing key warnings.

---

## Expected Result

All entities and relationships are bound to physical Delta tables in `LamnaHealthcareLH`.

---

## Next Exercise

Proceed to [Exercise 08: Test Ontology](08-Test-Ontology.md).
