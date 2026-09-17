# Exercise 11: Connect Ontology to Foundry

[← Previous Exercise: Create Foundry IQ Knowledge Base](10-Create-Foundry-IQ-Knowledge-Base.md) | [Home](../README.md) | [Next Exercise: Create AI Agent →](12-Create-AI-Agent.md)

---

## Objective

Establish a live Knowledge Source connection between `LamnaHealthcareOntology` in Microsoft Fabric and `LamnaHealthcareKnowledge` in Microsoft Foundry.

---

## Steps

### Step 1: Configure Fabric Connection in Foundry
1. Open `LamnaHealthcareKnowledge` in the Microsoft Foundry portal.
2. Click **+ Add Data Source > Fabric IQ Connector**.
3. Select your Fabric tenant identity and select workspace:

```text
LamnaHealthcareWS
```

4. Under **Select Fabric Item**, choose:

```text
LamnaHealthcareOntology
```

> [!NOTE]
> Add screenshot: Images/11-connect-ontology.png

### Step 2: Select Entities and Graph Traversal Depth
1. In the schema selection pane, check **Select all entity types**:
   - `Hospital`
   - `Department`
   - `Room`
   - `Patient`
   - `VitalSignEquipment`
2. Enable **Traverse Relationships**:
   - `contains`
   - `has`
   - `assignedTo`
   - `monitors`
   - `locatedIn`

### Step 3: Trigger Knowledge Indexing
1. Click **Save and Sync**.
2. Foundry IQ will initiate an automated indexing job extracting ontology entities, key properties, and relationships from Fabric IQ.
3. Wait 2-3 minutes until indexing status updates to **Active / Synchronized**.

---

## Validation

1. Click on the **Entities** tab inside `LamnaHealthcareKnowledge`.
2. Confirm that 5 entities (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`) show status **Indexed**.
3. Verify that `PatientId 1001` is indexed with active graph edges.

---

## Expected Result

`LamnaHealthcareOntology` is synchronized with `LamnaHealthcareKnowledge` in Microsoft Foundry.

---

## Next Exercise

Proceed to [Exercise 12: Create AI Agent](12-Create-AI-Agent.md).
