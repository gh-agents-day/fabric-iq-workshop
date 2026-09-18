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
3. In the left navigation menu, select **Workspaces**.

### Step 2: Provision a New Workspace
1. In the Workspaces pane, select **+ New workspace**.
2. In the **Create a workspace** pane, configure the following settings:

| Setting | Value |
| :--- | :--- |
| **Workspace Name** | `LamnaHealthcareWS` |
| **Description** | Workspace for Lamna Healthcare Fabric IQ Ontology and Foundry AI Agent workshop. |

3. Expand the **Advanced** section.
4. Under **License mode**, select a valid capacity option (Fabric capacity, Trial, or Premium capacity).
5. Select **Apply** to provision the workspace.

---

## Validation

1. Verify that the browser redirects to the newly created `LamnaHealthcareWS` workspace.
2. Confirm that the workspace license indicator appears near the top workspace header.

---

## Expected Result

An empty Fabric workspace titled `LamnaHealthcareWS` is provisioned and ready for use.

---

## Next Exercise

Proceed to [Exercise 02: Create Lakehouse](02-Create-Lakehouse.md).
