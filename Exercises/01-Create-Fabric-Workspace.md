# Exercise 01: Create Fabric Workspace

[← Previous Exercise: Prerequisites Verification](00-Prerequisites.md) | [Home](../README.md) | [Next Exercise: Create Lakehouse →](02-Create-Lakehouse.md)

---

## Objective

Create a dedicated Microsoft Fabric workspace named `LamnaHealthcareWS` configured with Fabric capacity licensing to host the healthcare data lakehouse and ontology artifacts.

---

## Steps

### Step 1: Access Microsoft Fabric Portal
1. Open your web browser and navigate to [https://app.fabric.microsoft.com/](https://app.fabric.microsoft.com/).
2. Sign in with your Fabric credentials.
3. In the left navigation menu, click on the **Workspaces** icon (represented by the folder/workspace icon).

> [!NOTE]
> Add screenshot: Images/01-fabric-navigation.png

### Step 2: Provision a New Workspace
1. In the Workspaces pane, click **+ New workspace**.
2. In the **Create a workspace** side pane, configure the following settings:

| Setting | Value |
| :--- | :--- |
| **Workspace Name** | `LamnaHealthcareWS` |
| **Description** | Workspace for Lamna Healthcare Fabric IQ Ontology and Foundry AI Agent workshop. |

3. Expand the **Advanced** section at the bottom of the pane.
4. Under **License mode**, select one of the following valid capacity options:
   - **Fabric capacity**: Assign to your organization's F-SKU capacity.
   - **Trial**: Select if using a Fabric Trial capacity.
   - **Premium capacity**: Select if using Power BI Premium P-SKU.

> [!TIP]
> Ensure the capacity region matches your Azure region for Microsoft Foundry to reduce cross-region latency.

5. Click **Apply** to provision the workspace.

> [!NOTE]
> Add screenshot: Images/01-create-workspace.png

---

## Validation

1. Verify that the browser redirects to the newly created `LamnaHealthcareWS` workspace.
2. Confirm that the workspace license indicator (diamond or trial badge) appears near the top workspace header.

---

## Expected Result

An empty Fabric workspace titled `LamnaHealthcareWS` is provisioned and bound to a valid Fabric capacity.

---

## Next Exercise

Proceed to [Exercise 02: Create Lakehouse](02-Create-Lakehouse.md).
