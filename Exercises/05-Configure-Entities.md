# Exercise 05: Create Entity Types

[← Previous Exercise: Create Ontology](04-Create-Ontology.md) | [Home](../README.md) | [Next Exercise: Create Relationship Types →](06-Configure-Relationships.md)

---

## Objective

You’ll create five entity types representing the healthcare domain (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`), define their properties, and configure entity keys.

---

## Steps

### Step 1: Create Hospital Entity Type
1. In the ontology ribbon, select **Add entity type**.
2. Enter `Hospital` as the entity type name and select **Add Entity Type**.
3. The `Hospital` entity type appears on the canvas.
4. With the `Hospital` entity type selected, select **View entity type details** in the ribbon to open the entity type’s Configure page.
5. In the **Properties** section, find and expand **Manage property bindings** and select **Add properties**.
6. Add each property by entering the details below and selecting **+ Add** after each one:

| Property Name | Property Type |
| :--- | :--- |
| `HospitalId` | `Integer` |
| `HospitalName` | `String` |
| `City` | `String` |
| `State` | `String` |

7. After adding all properties, select **Save**.
8. Now define an entity key: Select **Define entity type key**, choose `HospitalId` as the key, and select **Save**.
9. Select **Home** to return to the ontology canvas.

### Step 2: Create Remaining Entity Types
Follow the same process to create these four additional entity types with their properties and keys:

| Entity Type | Property Name | Property Type | Entity Type Key |
| :--- | :--- | :--- | :--- |
| **Department** | `DepartmentId`<br>`DepartmentName`<br>`HospitalId`<br>`Floor` | `Integer`<br>`String`<br>`Integer`<br>`Integer` | `DepartmentId` |
| **Room** | `RoomId`<br>`RoomNumber`<br>`DepartmentId`<br>`RoomType` | `Integer`<br>`String`<br>`Integer`<br>`String` | `RoomId` |
| **Patient** | `PatientId`<br>`FirstName`<br>`LastName`<br>`DateOfBirth`<br>`AdmissionDate`<br>`CurrentRoomId` | `Integer`<br>`String`<br>`String`<br>`DateTime`<br>`DateTime`<br>`Integer` | `PatientId` |
| **VitalSignEquipment** | `EquipmentId`<br>`PatientId`<br>`EquipmentType`<br>`MonitoringStartDate` | `String`<br>`Integer`<br>`String`<br>`DateTime` | `EquipmentId` |

---

## Validation

You now have five entity types with properties and keys defined. Verify that the Entity Types pane shows all five entity types, and that properties and entity type key have been defined for each entity as shown in the image below:

![Entity Types Configured in Ontology Canvas](../Images/05-entity-hospital.png)

---

## Expected Result

Five entity types (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`) are configured with property types and primary keys.

---

## Next Exercise

Proceed to [Exercise 06: Create Relationship Types](06-Configure-Relationships.md).
