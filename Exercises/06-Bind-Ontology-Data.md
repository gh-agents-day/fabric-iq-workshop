# Exercise 06: Bind Entity Types to Data & Configure Relationships

[← Previous Exercise: Create Relationship Types](05-Configure-Relationships.md) | [Home](../README.md) | [Next Exercise: Preview the Ontology →](07-Test-Ontology.md)

---

## Objective

Bind entity properties to actual data sources (static Lakehouse Delta tables and time-series Eventhouse tables) and configure relationship key mappings.

---

## Steps

### Step 1: Bind Static Lakehouse Data

#### 1. Bind Hospital Entity
1. Select the **Hospital** entity type on the canvas, select the ellipsis (`...`) next to its name, and select **Bind data**.
2. Select **Add data binding > Lakehouse table**.
3. Select `LamnaHealthcareLH` (lakehouse) from your workspace and select **Next**.
4. Select the `hospitals` table and select **Select**.
5. For Binding type, keep **Static**.
6. Under Properties, ensure the automated map matches the corresponding column:
   - **Entity type key mapping**: `HospitalId` → `HospitalId`
   - **Properties**:
     - `HospitalName` → `HospitalName`
     - `City` → `City`
     - `State` → `State`
   *(The system usually auto-maps when names match).*
7. Select **Save**, confirm the entity type updated successfully, then select **Cancel** to close the configuration options.
8. Select **Home** to return to the ontology canvas.

#### 2. Bind Department, Room, and Patient Entities
Follow the same binding process for these three entities, which only require static data bindings. The system automatically maps columns to properties when names match—just verify the mappings are correct:

| Entity Type | Table Name | Source Columns |
| :--- | :--- | :--- |
| **Department** | `departments` | `DepartmentId`<br>`DepartmentName`<br>`HospitalId`<br>`Floor` |
| **Room** | `rooms` | `RoomId`<br>`RoomNumber`<br>`DepartmentId`<br>`RoomType` |
| **Patient** | `patients` | `PatientId`<br>`FirstName`<br>`LastName`<br>`DateOfBirth`<br>`AdmissionDate`<br>`CurrentRoomId` |

---

### Step 2: Bind VitalSignEquipment Static & Time-Series Data

The `VitalSignEquipment` entity requires two data bindings: one for static equipment attributes and one for time-series measurements. Time-series bindings require static bindings first. Here’s why—look at what each data source contains:

**`VitalSignEquipment.csv` (Lakehouse - Static attributes):**
```text
EquipmentId | PatientId | EquipmentType           | MonitoringStartDate
VS-1001     | 1001      | Continuous Monitoring   | 2026-02-01
VS-1002     | 1002      | Continuous Monitoring   | 2026-02-01
```

**`VitalSignsReadings.csv` (Eventhouse - Time-series measurements):**
```text
ReadingId | EquipmentId | Timestamp            | HeartRate | OxygenSaturation | RespiratoryRate
1         | VS-1001     | 2026-02-02T08:00:00Z | 78        | 98               | 16
2         | VS-1001     | 2026-02-02T08:05:00Z | 82        | 97               | 18
4         | VS-1002     | 2026-02-02T08:00:00Z | 92        | 99               | 14
```

Notice the time-series data only has measurements and `EquipmentId`—not patient or equipment type. The static binding creates the equipment entities with full context (`VS-1001` is Continuous Monitoring equipment tracking `Patient 1001`), and the time-series binding attaches streaming measurements to those entities using `EquipmentId` as the matching key.

#### 1. Bind Static Monitor Reference Data
1. Select the **VitalSignEquipment** entity type, select the ellipsis (`...`) next to its name, and select **Bind data**.
2. Select **Add data binding > Lakehouse table**.
3. Select `LamnaHealthcareLH` (lakehouse) from your workspace and select **Next**.
4. Select the `vitalsignequipment` table and select **Select**.
5. Keep **Static** binding type.
6. Map properties to columns (should auto-map):
   - `EquipmentId` → `EquipmentId`
   - `PatientId` → `PatientId`
   - `EquipmentType` → `EquipmentType`
   - `MonitoringStartDate` → `MonitoringStartDate`
7. Select **Save**, confirm the entity type updated successfully, then select **Cancel** to close the configuration options.

#### 2. Bind Time-Series Vital Signs Data
Now you’ll add real-time vital signs readings as time-series properties.

1. With `VitalSignEquipment` still open (if not, select the ellipsis `...` next to its name and select **Bind data**).
2. Select **Add data binding > Eventhouse table**.
3. Select `LamnaHealthcareEH` (eventhouse) from your workspace and select **Next**.
4. Select the `VitalSignsReadings` table and select **Add**.
5. Under **Timeseries data**, select `Timestamp`.

> [!IMPORTANT]
> Time-series bindings require a matching key from static data. You must have the static binding configured first (which you just did).

6. Configure the time-series binding:
   - **Entity type key mapping**: Confirm `EquipmentId` is auto-selected under the Entity type key mapping section (matches the `EquipmentId` column from your static binding).
   - **Properties**: Map properties to columns (should auto-map; if not, select **Add entity type property** and select **Add all source columns as properties**):
     - `ReadingId` → `ReadingId`
     - `Timestamp` → `Timestamp`
     - `HeartRate` → `HeartRate`
     - `OxygenSaturation` → `OxygenSaturation`
     - `RespiratoryRate` → `RespiratoryRate`

![Time-Series Vital Signs Data Binding Configuration](../Images/timesseries.png)

7. Select **Save** to save the time-series binding, and confirm the entity type updated successfully.
8. Select **Home** to return to the ontology canvas.

---

### Step 3: Configure Relationships

Now you’ll configure each relationship type by specifying which table links the entity instances together. First you’ll configure one relationship using the details below, then use the reference table for the remaining four.

#### 1. Configure Hospital-Department Relationship
1. On the ontology canvas, select the **Hospital** entity, then select **contains** in the relationship line between `Hospital` and `Department`.
2. Configure the entity type mappings by selecting columns that match the key properties defined on each entity:
   - Under **Origin entity type**: Confirm `Hospital` is selected.
     - **Matched Hospital**: Select `HospitalId` (matches the `HospitalId` key defined on the `Hospital` entity).
   - Under **Target entity type**: Confirm `Department` is selected.
     - **Matched Department**: Select `DepartmentId` (matches the `DepartmentId` key defined on the `Department` entity).
3. Select **Save**, confirm that the relationship type updated successfully, then select **Cancel** to close the configuration options.
4. Select **Home** to return to the ontology canvas.

#### 2. Configure Remaining Relationships
Follow the same process for the remaining four relationships. For each: select the relationship line on the canvas, configure the mapping table and column mappings on the relationship’s configuration page, and select **Save**.

| Relationship | Source Data | Origin Entity Column | Target Entity Column |
| :--- | :--- | :--- | :--- |
| **`has`** (`Department` → `Room`) | `LamnaHealthcareLH > dbo > rooms` | Department: `DepartmentId` | Room: `RoomId` |
| **`assignedTo`** (`Patient` → `Room`) | `LamnaHealthcareLH > dbo > patients` | Patient: `PatientId` | Room: `CurrentRoomId` |
| **`monitors`** (`VitalSignEquipment` → `Patient`) | `LamnaHealthcareLH > dbo > vitalsignequipment` | VitalSignEquipment: `EquipmentId` | Patient: `PatientId` |
| **`locatedIn`** (`VitalSignEquipment` → `Room`) | `LamnaHealthcareLH > dbo > patients` | VitalSignEquipment: `PatientId` | Room: `CurrentRoomId` |

All five entity types now have data bindings connecting their properties to data sources, and all relationships have source data configured. Your ontology understands the complete healthcare data model.

---

## Validation

1. Confirm all 5 entity types display bound status icons on the canvas.
2. Confirm all 5 relationship lines display configured mapping indicators.

---

## Expected Result

All entities and relationships in `LamnaHealthcareOntology` are bound to physical data tables in Fabric Lakehouse and Eventhouse.

---

## Next Exercise

Proceed to [Exercise 07: Preview the Ontology](07-Test-Ontology.md).
