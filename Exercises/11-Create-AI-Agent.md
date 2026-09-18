# Exercise 11: Create AI Agent

[← Previous Exercise: Connect Ontology to Foundry](10-Connect-Ontology-to-Foundry.md) | [Home](../README.md) | [Next Exercise: Test Agent →](12-Test-Agent.md)

---

## Objective

Build and configure a grounded Microsoft Foundry AI Agent named `LamnaHealthcareAgent` connected to `LamnaHealthcareKnowledge`.

---

## Steps

### Step 1: Provision AI Agent in Foundry
1. In `LamnaHealthcareFoundryProject`, select **Agents** from the left navigation menu.
2. Select **+ Create agent**.
3. Set agent name to `LamnaHealthcareAgent`.
4. Select model deployment: `gpt-4o`.

### Step 2: Configure System Instructions
In the **Instructions** text box, enter the following system prompt:

```text
You are a healthcare data assistant.

Answer healthcare questions using the knowledge base grounded in the Lamna Healthcare Fabric IQ ontology.

Use ontology entities, properties, keys, and relationships when answering questions.

Use PatientId to identify patients.

Do not invent healthcare data. If information cannot be retrieved from the ontology, clearly state that the information could not be retrieved.
```

### Step 3: Attach Foundry IQ Knowledge Base Tool
1. Under **Tools**, select **+ Add tool > Knowledge Base**.
2. Select `LamnaHealthcareKnowledge`.
3. Select **Save agent**.

---

## Validation

1. Verify that `LamnaHealthcareAgent` appears in your project agents list.
2. Confirm `LamnaHealthcareKnowledge` is listed under active Agent Tools.

---

## Expected Result

`LamnaHealthcareAgent` is fully configured with healthcare grounding instructions and connected to the Fabric IQ Knowledge Base.

---

## Next Exercise

Proceed to [Exercise 12: Test Agent](12-Test-Agent.md).
