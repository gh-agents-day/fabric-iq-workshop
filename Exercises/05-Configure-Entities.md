# Exercise 05: Configure Entities

[← Previous Exercise: Create Ontology](04-Create-Ontology.md) | [Home](../README.md) | [Next Exercise: Configure Relationships →](06-Configure-Relationships.md)

---

## Objective

Define the 5 domain entity types (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`), add properties to each entity, and set entity keys in `LamnaHealthcareOntology`.

---

## Steps

### Step 1: Create `Hospital` Entity Type
1. In the ontology ribbon, select **Add entity type**.
2. Enter `Hospital` as the entity type name and select **Add Entity Type**.
3. Select the `Hospital` entity type on the canvas, then select **View entity type details** in the ribbon.
4. In the **Properties** section, select **Manage property bindings > Add properties**.
5. Add each property by entering details and selecting **+ Add**:
   - `HospitalId` (Integer)
   - `HospitalName` (String)
   - `City` (String)
   - `State` (String)
6. Select **Save**.
7. Select **Define entity type key**, choose `HospitalId` as the key, and select **Save**.
8. Select **Home** to return to the ontology canvas.

![Hospital Entity Configuration](../Images/05-entity-hospital.png)

### Step 2: Create Remaining Entity Types
Follow the same process to create the remaining four entity types with their properties and keys:

#### `Department`
- **Name**: `Department`
- **Properties**: `DepartmentId` (Integer), `DepartmentName` (String), `HospitalId` (Integer), `Floor` (Integer)
- **Entity Key**: `DepartmentId`

#### `Room`
- **Name**: `Room`
- **Properties**: `RoomId` (Integer), `RoomNumber` (String), `DepartmentId` (Integer), `RoomType` (String)
- **Entity Key**: `RoomId`

#### `Patient`
- **Name**: `Patient`
- **Properties**: `PatientId` (Integer), `FirstName` (String), `LastName` (String), `DateOfBirth` (String), `AdmissionDate` (String), `CurrentRoomId` (Integer)
- **Entity Key**: `PatientId`

#### `VitalSignEquipment`
- **Name**: `VitalSignEquipment`
- **Properties**: `EquipmentId` (String), `PatientId` (Integer), `EquipmentType` (String), `MonitoringStartDate` (String), `RoomId` (Integer)
- **Entity Key**: `EquipmentId`

---

## Validation

1. Verify that the **Entity Types** pane displays all 5 entity types:
   - `Hospital` (Key: `HospitalId`)
   - `Department` (Key: `DepartmentId`)
   - `Room` (Key: `RoomId`)
   - `Patient` (Key: `PatientId`)
   - `VitalSignEquipment` (Key: `EquipmentId`)
2. Confirm properties and entity type keys are defined for each entity.

---

## Expected Result

All 5 entity types are created on the canvas with appropriate property schemas and primary keys.

---

## Next Exercise

Proceed to [Exercise 06: Configure Relationships](06-Configure-Relationships.md).
