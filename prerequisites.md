# Workshop Prerequisites & System Setup

Before starting the **Build an AI Agent with Microsoft Fabric IQ, Ontology, and Microsoft Foundry** workshop, verify that all subscription, tenant, and licensing requirements are met.

---

## 1. Microsoft Fabric Capacity & Tenant Settings

### Required Licensing
- Access to a **Microsoft Fabric Capacity** (Fabric Trial or paid Fabric Capacity).
- **Fabric Administrator** or **Workspace Admin** permissions.

> [!IMPORTANT]
> Ontology features in Microsoft Fabric are currently in preview. To complete this lab, you need access to a Fabric paid or trial capacity, and tenant settings for Ontology and Graph items must be enabled by a Fabric Administrator.

### Required Tenant Settings
A Fabric Administrator must enable the following settings in the **Fabric Admin Portal** (`Settings > Admin portal > Tenant settings`):

1. **Ontology (preview)**: Enable `Users can create and edit Ontology items (preview)`.
2. **Graph (preview)**: Enable `Users can create Graph (preview)`.

---

## 2. Microsoft Foundry Setup

### Access Requirements
- An active **Azure Subscription** with permissions to create resource groups and Azure AI resources (Contributor or Owner role).
- Access to the **Microsoft Foundry portal** (`https://ai.azure.com`).
- Permission to deploy foundation models (such as GPT-4o or GPT-4o-mini) within your project.

---

## 3. Client Environment & Browser Requirements

- **Browser**: Modern web browser (Microsoft Edge or Google Chrome recommended).
- **Local File System Access**: Ability to access CSV datasets from this repository (`Data/` folder) and upload them to Microsoft Fabric.

---

## 4. Workshop Assets Verification

Ensure you have cloned or downloaded this repository to access the following datasets:
- [`Data/hospitals.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/hospitals.csv)
- [`Data/departments.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/departments.csv)
- [`Data/rooms.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/rooms.csv)
- [`Data/patients.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/patients.csv)
- [`Data/vitalsignequipment.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/vitalsignequipment.csv)
- [`Data/vitalsignsreadings.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/vitalsignsreadings.csv)

---

## Quick Navigation

[← Back to README](README.md) | [Start Exercise 00: Prerequisites Verification →](Exercises/00-Prerequisites.md)
