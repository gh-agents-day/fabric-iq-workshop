# Exercise 08: Create AI Agent with Fabric IQ Ontology

[← Previous Exercise: Preview the Ontology & Query Builder](07-Test-Ontology.md) | [Home](../README.md) | [Next Exercise: Test AI Agent →](09-Test-Agent.md)

---

## Objective

Provision a project in Microsoft Foundry, create an AI Agent named `LamnaHealthcareAgent`, configure system instructions, and attach your `LamnaHealthcareOntology` item directly via the **Fabric IQ (OneLake Catalog)** tool.

---

## Steps

### Step 1: Create or Open Foundry Project
1. Open a web browser and navigate to [Microsoft Foundry](https://ai.azure.com).
2. Sign in with your Azure credentials.
3. On the Foundry home page, select **+ Create project** (or open your existing project `LamnaHealthcareFoundryProject`).
4. Select your Azure Subscription and Resource Group (`rg-lamna-healthcare`), then select **Create**.

---

### Step 2: Create AI Agent & Configure System Instructions
1. In the left navigation menu under **Build**, select **Agents**.
2. Select **+ Create agent**.
3. Configure agent settings:
   - **Agent Name**: `LamnaHealthcareAgent`
   - **Model Deployment**: Select `gpt-4o` (or `gpt-4o-mini`).
4. In the **Instructions** text box, enter the system prompt:

```text
You are a Lamna Healthcare AI Assistant.

Use the connected Fabric IQ Ontology to retrieve and answer questions about:
- Patients
- Rooms
- Hospitals
- Departments
- Vital sign equipment
- Patient-to-room assignments
- Patient monitoring relationships

Use the ontology relationships to retrieve related information.

Behavior:
- Always use Fabric IQ data for healthcare questions.
- Give accurate, concise, and grounded answers.
- Do not invent or assume data.
- If information is unavailable, clearly say so.
- Present results in a simple table or bullet points when useful.
```

---

### Step 3: Attach Fabric IQ Ontology Tool
1. In the agent configuration pane, locate **Tools** and select **+ Add tool** (or **Connect a tool**).
2. In the **Select a tool** modal, select **Fabric IQ (OneLake Catalog)**.
3. In the **OneLake Catalog** modal, select your ontology item: `LamnaHealthcareOntology`.
4. Select **Add tool** (or **Connect**).
5. Select **Save** to save the agent configuration.

---

## Validation

1. Verify that `LamnaHealthcareAgent` appears in your project agents list.
2. Confirm `LamnaHealthcareOntology` (Fabric IQ) is listed under active Agent Tools.

---

## Expected Result

`LamnaHealthcareAgent` is created in Microsoft Foundry, configured with system instructions, and grounded directly with your Fabric IQ `LamnaHealthcareOntology`.

---

## Next Exercise

Proceed to [Exercise 09: Test AI Agent](09-Test-Agent.md).
