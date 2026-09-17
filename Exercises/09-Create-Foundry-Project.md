# Exercise 09: Create Foundry Project

[← Previous Exercise: Test Ontology](08-Test-Ontology.md) | [Home](../README.md) | [Next Exercise: Create Foundry IQ Knowledge Base →](10-Create-Foundry-IQ-Knowledge-Base.md)

---

## Objective

Provision a Microsoft Foundry (Azure AI Foundry) project named `LamnaHealthcareFoundryProject` and deploy an LLM model deployment for agent reasoning.

---

## Steps

### Step 1: Sign in to Microsoft Foundry Portal
1. Open a browser tab and navigate to [https://ai.azure.com](https://ai.azure.com) (or [https://foundry.microsoft.com](https://foundry.microsoft.com)).
2. Sign in using your Azure credentials.
3. Verify that your active Azure Subscription is selected.

> [!NOTE]
> Add screenshot: Images/09-foundry-home.png

> [!NOTE]
> UI Notice: Microsoft Foundry branding and menu layout may differ slightly due to ongoing portal updates.

### Step 2: Create Azure AI Foundry Project
1. On the Foundry home page, click **+ Create project** (or **+ New project**).
2. Configure project details:

| Setting | Value |
| :--- | :--- |
| **Project name** | `LamnaHealthcareFoundryProject` |
| **Azure AI Hub / Resource** | Select existing Hub or create new `LamnaHealthcareHub` |
| **Subscription** | Select your active Azure Subscription |
| **Resource group** | `rg-lamna-healthcare` |
| **Region** | Select region matching your Fabric capacity (e.g., `East US 2` or `Sweden Central`) |

3. Click **Create** and wait for resource deployment to finish.

> [!NOTE]
> Add screenshot: Images/09-create-foundry-project.png

### Step 3: Deploy Language Model (GPT-4o)
1. In the left navigation menu of `LamnaHealthcareFoundryProject`, select **Deployments** under **My assets** (or **Models + endpoints**).
2. Click **+ Deploy model > Deploy base model**.
3. Select `gpt-4o` (or `gpt-4o-mini`).
4. Configure deployment:
   - **Deployment name**: `gpt-4o`
   - **Deployment type**: Standard / Global Standard
5. Click **Deploy**.

---

## Validation

1. Open **Deployments** in `LamnaHealthcareFoundryProject`.
2. Confirm that deployment `gpt-4o` shows status **Succeeded** and **Succeeded (Active)**.

---

## Expected Result

`LamnaHealthcareFoundryProject` is created with an active `gpt-4o` model deployment ready for AI Agent grounding.

---

## Next Exercise

Proceed to [Exercise 10: Create Foundry IQ Knowledge Base](10-Create-Foundry-IQ-Knowledge-Base.md).
