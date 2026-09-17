# Exercise 13: Test Agent

[← Previous Exercise: Create AI Agent](12-Create-AI-Agent.md) | [Home](../README.md)

---

## Objective

Execute test queries against `LamnaHealthcareAgent` in Microsoft Foundry to validate grounding, graph traversal, and safety guardrails.

---

## Steps

### Step 1: Open Agent Playground
1. In `LamnaHealthcareFoundryProject`, open **Agents > LamnaHealthcareAgent**.
2. Click **Try in playground** (or open the interactive Chat pane).
3. Ensure the active model deployment is set to `gpt-4o` and tool `LamnaHealthcareKnowledge` is enabled.

> [!NOTE]
> Add screenshot: Images/13-agent-playground.png

### Step 2: Execute Test Scenarios

Run the following test queries sequentially in the playground chat window:

#### Test Query 1: Single Patient Lookup
**User Query:**
```text
Show the patient with PatientId 1001.
```

**Expected Response:**
- PatientId: `1001`
- Name: Kerry Allen
- Date of Birth: `1965-03-15`
- Admission Date: `2026-01-28`
- Current Room ID: `1`

#### Test Query 2: Patient Property Retrieval
**User Query:**
```text
What is the first name of PatientId 1001?
```

**Expected Response:**
- The first name of PatientId 1001 is **Kerry**.

#### Test Query 3: Room Assignment Traversal
**User Query:**
```text
Which room is PatientId 1001 assigned to?
```

**Expected Response:**
- PatientId 1001 (Kerry Allen) is assigned to **Room 1** (Room Number: `ICU-301`, Room Type: `Critical Care`, Department: `Intensive Care Unit`).

#### Test Query 4: Monitoring Equipment Traversal
**User Query:**
```text
What equipment is monitoring PatientId 1001?
```

**Expected Response:**
- PatientId 1001 is monitored by **Continuous Monitoring** equipment (EquipmentId: `VS-1001`).

#### Test Query 5: Active Patient Monitoring Summary
**User Query:**
```text
Which patients are currently being monitored?
```

**Expected Response:**
- Lists all 5 monitored patients:
  - 1001: Kerry Allen (`VS-1001` - Continuous Monitoring in Room 1)
  - 1002: Casey Morgan (`VS-1002` - Continuous Monitoring in Room 2)
  - 1003: Elijah Thompson (`VS-1003` - Continuous Monitoring in Room 3)
  - 1004: Priya Desai (`VS-1004` - Continuous Monitoring in Room 7)
  - 1005: Maya Robinson (`VS-1005` - Continuous Monitoring in Room 8)

#### Test Query 6: Combined Graph Traversal
**User Query:**
```text
Show the room and monitoring equipment associated with PatientId 1001.
```

> [!NOTE]
> Add screenshot: Images/13-test-agent-query.png

**Expected Response:**
- Patient: Kerry Allen (PatientId: `1001`)
- Assigned Room: Room `1` (`ICU-301`, Department: `Intensive Care Unit`)
- Equipment: `VS-1001` (Continuous Monitoring, started `2026-02-01`)

---

### Step 3: Test Grounding Safety Guardrail (Negative Test)

**User Query:**
```text
What is the prescription dosage for PatientId 9999?
```

**Expected Agent Behavior:**
- Agent respects instruction guardrails: *"The requested information for PatientId 9999 could not be retrieved from the Lamna Healthcare Fabric IQ Ontology."*
- Agent **does not** hallucinate or invent healthcare records.

---

## Validation

1. Verify that all 6 positive queries accurately reflect data in `Patients.csv`, `Rooms.csv`, and `VitalSignEquipment.csv`.
2. Verify that the agent correctly traverses graph relationships (`Patient` → `Room`, `VitalSignEquipment` → `Patient`).
3. Verify that the safety guardrail prevents invented answers for non-existent IDs.

---

## Expected Result

`LamnaHealthcareAgent` provides accurate, grounded natural language responses powered by Microsoft Fabric IQ Ontology and Microsoft Foundry.

---

## Workshop Completion

Congratulations! You have successfully completed the **Build an AI Agent with Microsoft Fabric IQ, Ontology, and Microsoft Foundry** workshop.

### Key Achievements:
- Built a multi-entity Healthcare Delta Lakehouse in Microsoft Fabric.
- Modeled complex domain entities and graph relationships in Fabric IQ Ontology.
- Validated graph traversals via Fabric IQ Query Builder.
- Grounded a Microsoft Foundry AI Agent using Foundry IQ Knowledge Base.

[Return to Main Workshop README](../README.md)
