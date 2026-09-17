# Exercise 04: Create Ontology

[← Previous Exercise: Load Healthcare Data](03-Load-Healthcare-Data.md) | [Home](../README.md) | [Next Exercise: Configure Entities →](05-Configure-Entities.md)

---

## Objective

Create an empty **Fabric IQ Ontology** item named `LamnaHealthcareOntology` within the `LamnaHealthcareWS` workspace.

---

## Steps

### Step 1: Provision Ontology Preview Item
1. Return to the `LamnaHealthcareWS` workspace view in Microsoft Fabric.
2. In the top toolbar, click **+ New item**.
3. In the new item selection modal, locate the **Fabric IQ** section and select **Ontology (preview)**.

> [!NOTE]
> Add screenshot: Images/04-new-item-ontology.png

> [!NOTE]
> If **Ontology (preview)** is not visible, verify that your Fabric administrator enabled the `Enable Ontology item (preview)` tenant setting in [Exercise 00](00-Prerequisites.md).

### Step 2: Name and Save the Ontology
1. In the **New ontology** dialog box, enter the ontology name:

```text
LamnaHealthcareOntology
```

2. Click **Create**.

> [!NOTE]
> Add screenshot: Images/04-create-ontology.png

### Step 3: Explore the Ontology Canvas
1. Once created, Fabric automatically launches the **Ontology Canvas**.
2. Note the primary layout sections:
   - **Top Ribbon**: Actions for adding entity types, relationships, data bindings, and opening the Query Builder.
   - **Canvas Center**: Visual graph editor displaying entity nodes and relationship arrows.
   - **Left Explorer Pane**: List of entity types, properties, and relationships.

---

## Validation

1. Verify that `LamnaHealthcareOntology` is listed in your workspace items.
2. Verify that the canvas loads cleanly without schema errors.

---

## Expected Result

An empty ontology item `LamnaHealthcareOntology` is provisioned and opened in canvas editing mode.

---

## Next Exercise

Proceed to [Exercise 05: Configure Entities](05-Configure-Entities.md).
