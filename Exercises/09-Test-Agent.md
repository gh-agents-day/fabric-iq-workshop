# Exercise 09: Test AI Agent

[← Previous Exercise: Create AI Agent with Fabric IQ Ontology](08-Create-AI-Agent.md) | [Home](../README.md) | [Next Exercise: Clean Up Resources →](10-Clean-Up-Resources.md)

---

## Objective

Interact with `LamnaHealthcareAgent` in the Microsoft Foundry playground using natural language test queries to validate ontology grounding, graph traversal, and response accuracy.

---

## Steps

### Step 1: Open Agent Playground
1. In Microsoft Foundry, select **Build > Agents > LamnaHealthcareAgent**.
2. Select **Try in playground** (or open the Chat pane).
3. Confirm that the active model deployment is `gpt-5` (or `gpt-5-mini`) and `Fabric IQ (LamnaHealthcareOntology)` tool is active.

---

### Step 2: Execute Test Queries

Run the following test queries sequentially in the chat window:

#### Query 1: Single Patient Lookup
**User Query:**
```text
Show details for PatientId 1001.
```

**Expected Agent Response:**
- **Patient**: Kerry Allen (`PatientId: 1001`)
- **Date of Birth**: `1965-03-15`
- **Admission Date**: `2026-01-28`
- **Current Room ID**: `1`

---

#### Query 2: Room & Monitoring Equipment Traversal
**User Query:**
```text
Show the room and monitoring equipment associated with PatientId 1001.
```

**Expected Agent Response:**
- **Patient**: Kerry Allen (`PatientId: 1001`)
- **Assigned Room**: Room `1` (`ICU-301`, Department: `Intensive Care Unit`)
- **Monitoring Equipment**: `VS-1001` (Continuous Monitoring, started `2026-02-01`)

---

#### Query 3: Safety Guardrail (Non-Existent Patient)
**User Query:**
```text
What is the prescription dosage for PatientId 9999?
```

**Expected Agent Response:**
- The agent respects safety instructions: *"Information for PatientId 9999 could not be retrieved from the Lamna Healthcare Fabric IQ Ontology."*
- The agent does **not** hallucinate or invent records.

---

## Validation

1. Verify that queries 1 and 2 return accurate patient, room, and equipment data matching `patients.csv`, `rooms.csv`, and `vitalsignequipment.csv`.
2. Verify that the agent correctly traverses graph relationships (`Patient` → `Room`, `VitalSignEquipment` → `Patient`).
3. Verify that the safety guardrail prevents invented answers for non-existent IDs.

---

## Expected Result

`LamnaHealthcareAgent` accurately answers clinical context questions grounded directly in your Microsoft Fabric IQ Ontology.

---

## Next Exercise

Proceed to [Exercise 10: Clean Up Resources (Optional)](10-Clean-Up-Resources.md).
