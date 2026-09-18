# Exercise 10: Connect Ontology to Foundry

[← Previous Exercise: Create Foundry IQ Knowledge Base](09-Create-Foundry-IQ-Knowledge-Base.md) | [Home](../README.md) | [Next Exercise: Create AI Agent →](11-Create-AI-Agent.md)

---

## Objective

Establish a live Knowledge Source connection between `LamnaHealthcareOntology` in Microsoft Fabric and `LamnaHealthcareKnowledge` in Microsoft Foundry.

---

## Steps

### Step 1: Configure Fabric Connection in Foundry
1. Open `LamnaHealthcareKnowledge` in the Microsoft Foundry portal.
2. Select **+ Add Data Source > Fabric IQ Connector**.
3. Select workspace: `LamnaHealthcareWS`.
4. Under **Select Fabric Item**, choose: `LamnaHealthcareOntology`.

### Step 2: Select Entities and Relationships
1. Select all entity types:
   - `Hospital`
   - `Department`
   - `Room`
   - `Patient`
   - `VitalSignEquipment`
2. Enable relationship traversal:
   - `contains`
   - `has`
   - `assignedTo`
   - `monitors`
   - `locatedIn`

### Step 3: Trigger Knowledge Indexing
1. Select **Save and Sync**.
2. Foundry IQ will initiate an automated indexing job extracting ontology entities, key properties, and relationships from Fabric IQ.
3. Wait for indexing status to update to **Active / Synchronized**.

---

## Validation

1. Select the **Entities** tab inside `LamnaHealthcareKnowledge`.
2. Confirm that 5 entities (`Hospital`, `Department`, `Room`, `Patient`, `VitalSignEquipment`) show status **Indexed**.
3. Verify that `PatientId 1001` is indexed with active graph edges.

---

## Expected Result

`LamnaHealthcareOntology` is synchronized with `LamnaHealthcareKnowledge` in Microsoft Foundry.

---

## Next Exercise

Proceed to [Exercise 11: Create AI Agent](11-Create-AI-Agent.md).
