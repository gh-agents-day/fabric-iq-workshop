# Exercise 10: Create Foundry IQ Knowledge Base

[← Previous Exercise: Create Foundry Project](09-Create-Foundry-Project.md) | [Home](../README.md) | [Next Exercise: Connect Ontology to Foundry →](11-Connect-Ontology-to-Foundry.md)

---

## Objective

Create a Foundry IQ Knowledge Base named `LamnaHealthcareKnowledge` inside `LamnaHealthcareFoundryProject` to index and ground Fabric IQ Ontologies for AI Agent reasoning.

---

## Steps

### Step 1: Navigate to Knowledge Bases in Foundry
1. In `LamnaHealthcareFoundryProject`, locate the left navigation menu.
2. Under **Knowledge** (or **Data & Indexes**), click **Knowledge bases** (or **Foundry IQ**).
3. Click **+ Create knowledge base**.

> [!NOTE]
> Add screenshot: Images/10-knowledge-base-menu.png

### Step 2: Configure Knowledge Base Details
1. In the Knowledge Base creation wizard, enter:

| Setting | Value |
| :--- | :--- |
| **Knowledge Base Name** | `LamnaHealthcareKnowledge` |
| **Description** | Grounded healthcare knowledge base backed by Fabric IQ Ontology. |
| **Indexing Mode** | Semantic & Graph Indexing |

2. Click **Next**.

> [!NOTE]
> Add screenshot: Images/10-foundry-iq-knowledge-base.png

### Step 3: Select Fabric IQ Knowledge Source Type
1. Under **Select data source type**, choose **Microsoft Fabric IQ / Fabric Ontology (preview)**.
2. Select **Microsoft Fabric Connection**.

---

## Validation

1. Verify that `LamnaHealthcareKnowledge` appears in the list of Knowledge Bases.
2. Confirm status is set to **Draft / Awaiting Source Configuration**.

---

## Expected Result

The `LamnaHealthcareKnowledge` Knowledge Base shell is provisioned in Microsoft Foundry.

---

## Next Exercise

Proceed to [Exercise 11: Connect Ontology to Foundry](11-Connect-Ontology-to-Foundry.md).
