# Exercise 00: Prerequisites Verification

[← Back to Main README](../README.md) | [Next Exercise: Create Fabric Workspace →](01-Create-Fabric-Workspace.md)

---

## Objective

Verify that your Microsoft Fabric tenant settings, capacity licensing, Azure subscriptions, and local workshop datasets are properly configured before attempting subsequent exercises.

---

## Steps

### Step 1: Verify Microsoft Fabric Tenant Settings
1. Navigate to the [Microsoft Fabric Home Portal](https://app.fabric.microsoft.com/) in your web browser and sign in with your organizational credentials.
2. Select the **Settings** gear icon in the top right corner and choose **Admin portal**.
3. In the left navigation menu, select **Tenant settings**.
4. Scroll to the **Fabric IQ / Ontology** section:
   - Ensure **Users can create and edit Ontology items (preview)** is toggled to **Enabled** for your tenant or security group.
   - Ensure **Users can create Graph (preview)** is toggled to **Enabled**.
5. Select **Apply** if you made any changes.

> [!NOTE]
> Add screenshot: Images/00-tenant-settings.png

> [!WARNING]
> Tenant setting updates in Microsoft Fabric can take up to 15 minutes to propagate across your tenant.

### Step 2: Check Capacity Licensing Mode
1. In the **Admin portal**, select **Capacity settings**.
2. Verify that you have access to an active **Fabric Capacity** (F64 SKU or higher recommended) or an active **Fabric Trial capacity**.

> [!WARNING]
> **Trial Capacity Limitations:**
> Standard Fabric Trial capacities do not support certain advanced AI features, including Data Agent, AI Functions, AI Services, Copilot, and Trusted Workspace Access.
>
> **Paid Capacity & NL2Ontology Note:**
> Operating on a paid Fabric capacity (F-SKU) resolves compute limits but does **not** automatically fix NL2Ontology compilation or preview errors. Fabric IQ preview features depend on regional AI model deployment availability.

### Step 3: Verify Microsoft Foundry & Azure Permissions
1. Open a browser tab and navigate to the [Microsoft Foundry portal](https://ai.azure.com).
2. Sign in with your Azure credentials.
3. Verify that you have **Contributor** or **Owner** rights on an active Azure Subscription where you can create resource groups and Azure AI resources.

### Step 4: Verify Local Datasets
1. Ensure the following CSV files are downloaded locally from the repository `Data/` folder:
   - `hospitals.csv`
   - `departments.csv`
   - `rooms.csv`
   - `patients.csv`
   - `vitalsignequipment.csv`

---

## Validation

- Confirm tenant settings for Ontology (preview) and Graph (preview) are set to Enabled.
- Confirm access to Microsoft Fabric and Microsoft Foundry portals.
- Confirm local availability of all 5 CSV datasets.

---

## Expected Result

Your tenant and user identity are fully prepared with the necessary preview flags and capacity rights to build the Lamna Healthcare Ontology.

---

## Next Exercise

Proceed to [Exercise 01: Create Fabric Workspace](01-Create-Fabric-Workspace.md).
