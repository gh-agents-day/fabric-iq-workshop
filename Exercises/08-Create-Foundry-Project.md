# Exercise 08: Create Foundry Project

[← Previous Exercise: Preview the Ontology & Query Builder](07-Test-Ontology.md) | [Home](../README.md) | [Next Exercise: Create Foundry IQ Knowledge Base →](09-Create-Foundry-IQ-Knowledge-Base.md)

---

## Objective

Provision a Microsoft Foundry (Azure AI Foundry) project named `LamnaHealthcareFoundryProject` and deploy a language model deployment for agent reasoning.

---

## Steps

### Step 1: Sign in to Microsoft Foundry Portal
1. Open a browser tab and navigate to [https://ai.azure.com](https://ai.azure.com).
2. Sign in using your Azure credentials.
3. Verify that your active Azure Subscription is selected.

### Step 2: Create Azure AI Foundry Project
1. On the Foundry home page, select **+ Create project**.
2. Configure project details:

| Setting | Value |
| :--- | :--- |
| **Project name** | `LamnaHealthcareFoundryProject` |
| **Subscription** | Select your active Azure Subscription |
| **Resource group** | `rg-lamna-healthcare` |
| **Region** | Select a supported region |

3. Select **Create** and wait for resource provisioning to complete.

### Step 3: Deploy Language Model (GPT-4o)
1. In the left navigation menu of `LamnaHealthcareFoundryProject`, select **Deployments**.
2. Select **+ Deploy model > Deploy base model**.
3. Select `gpt-4o` (or `gpt-4o-mini`).
4. Set deployment name to `gpt-4o`.
5. Select **Deploy**.

---

## Validation

1. Open **Deployments** in `LamnaHealthcareFoundryProject`.
2. Confirm that deployment `gpt-4o` displays status **Succeeded**.

---

## Expected Result

`LamnaHealthcareFoundryProject` is created with an active `gpt-4o` model deployment ready for AI Agent grounding.

---

## Next Exercise

Proceed to [Exercise 09: Create Foundry IQ Knowledge Base](09-Create-Foundry-IQ-Knowledge-Base.md).
