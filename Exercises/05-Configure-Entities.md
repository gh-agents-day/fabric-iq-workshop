# Exercise 05: Configure Entities

[← Previous Exercise: Create Ontology](04-Create-Ontology.md) | [Home](../README.md) | [Next Exercise: Configure Relationships →](06-Configure-Relationships.md)

---

## Objective

Define the 5 domain entity types (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`), add properties to each entity, and set entity keys in `LamnaHealthcareOntology`.

---

## Steps

### Step 1: Create `Hospital` Entity Type
1. In the `LamnaHealthcareOntology` ribbon, click **Add entity type**.
2. Enter `Hospital` as the entity type name and click **Add Entity Type**.
3. Select the `Hospital` node on the canvas, then click **View entity type details** (or edit properties).
4. Under **Properties**, click **Add properties** and create the following fields:

| Property Name | Property Type |
| :--- | :--- |
| `HospitalId` | String |
| `HospitalName` | String |
| `City` | String |
| `State` | String |

5. Click **Define entity type key**, select `HospitalId`, and click **Save**.

> [!NOTE]
> Add screenshot: Images/05-entity-hospital.png

### Step 2: Create `Department` Entity Type
1. Click **Add entity type** in the ribbon. Name: `Department`.
2. Open properties for `Department` and add the following fields:

| Property Name | Property Type |
| :--- | :--- |
| `DepartmentId` | String |
| `DepartmentName` | String |
| `HospitalId` | String |
| `Floor` | Integer |

3. Click **Define entity type key**, select `DepartmentId`, and click **Save**.

### Step 3: Create `Room` Entity Type
1. Click **Add entity type** in the ribbon. Name: `Room`.
2. Open properties for `Room` and add the following fields:

| Property Name | Property Type |
| :--- | :--- |
| `RoomId` | String |
| `RoomNumber` | String |
| `DepartmentId` | String |
| `RoomType` | String |

3. Click **Define entity type key**, select `RoomId`, and click **Save**.

### Step 4: Create `Patient` Entity Type
1. Click **Add entity type** in the ribbon. Name: `Patient`.
2. Open properties for `Patient` and add the following fields:

| Property Name | Property Type |
| :--- | :--- |
| `PatientId` | Integer |
| `FirstName` | String |
| `LastName` | String |
| `DateOfBirth` | Date |
| `AdmissionDate` | Date |
| `CurrentRoomId` | String |

3. Click **Define entity type key**, select `PatientId`, and click **Save**.

> [!NOTE]
> Add screenshot: Images/05-entity-patient.png

### Step 5: Create `VitalSignEquipment` Entity Type
1. Click **Add entity type** in the ribbon. Name: `VitalSignEquipment`.
2. Open properties for `VitalSignEquipment` and add the following fields:

| Property Name | Property Type |
| :--- | :--- |
| `EquipmentId` | String |
| `PatientId` | Integer |
| `EquipmentType` | String |
| `MonitoringStartDate` | DateTime |
| `RoomId` | String |

3. Click **Define entity type key**, select `EquipmentId`, and click **Save**.

---

## Validation

1. Inspect the left **Entity Types** pane in the Ontology canvas.
2. Confirm that all 5 entity types are listed:
   - `Hospital` (Key: `HospitalId`)
   - `Department` (Key: `DepartmentId`)
   - `Room` (Key: `RoomId`)
   - `Patient` (Key: `PatientId`)
   - `VitalSignEquipment` (Key: `EquipmentId`)

---

## Expected Result

All 5 entity types are defined on the canvas with appropriate property schemas and primary keys.

---

## Next Exercise

Proceed to [Exercise 06: Configure Relationships](06-Configure-Relationships.md).
