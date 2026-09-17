# Workshop Prerequisites & System Setup

Before starting the **Build an AI Agent with Microsoft Fabric IQ, Ontology, and Microsoft Foundry** workshop, verify that all subscription, tenant, and licensing requirements are met.

---

## 1. Microsoft Fabric Capacity & Tenant Settings

### Required Licensing
- Access to a **Microsoft Fabric Capacity** (F64 or higher recommended for full AI features, or an active **Fabric Trial** capacity).
- **Fabric Administrator** or **Workspace Admin** permissions.

> [!WARNING]
> **Trial Capacity Limitations:**
> Microsoft Fabric Trial capacity has specific platform restrictions. Certain advanced AI features — including Data Agent, AI Functions, AI Services, Copilot, and Trusted Workspace Access — are restricted or unavailable on standard Fabric Trial capacities.
>
> **Important Note on Capacity & NL2Ontology:**
> Upgrading to a paid Fabric capacity (F-SKU) resolves capacity throttling and unlocks enterprise features, but **does NOT automatically guarantee resolution of NL2Ontology or preview model compilation errors**. Fabric IQ preview capabilities depend on backend regional feature availability and tenant-level preview configurations.

### Required Tenant Settings
A Fabric Administrator must enable the following settings in the **Fabric Admin Portal** (`Settings > Admin portal > Tenant settings`):

1. **Ontology (preview)**: Enable `Users can create and edit Ontology items (preview)`.
2. **Graph (preview)**: Enable `Users can create Graph (preview)`.
3. **Data Agent & AI Features**: Enable AI and Copilot experiences if available in your region.

---

## 2. Microsoft Foundry (Azure AI Foundry) Setup

### Access Requirements
- An active **Azure Subscription** with permissions to create resource groups and Azure AI resources (Contributor or Owner role).
- Access to the **Microsoft Foundry portal** (`https://ai.azure.com` / `https://foundry.microsoft.com`).
- Permission to deploy foundation models (e.g., GPT-4o or GPT-4o-mini) within your Azure AI Foundry project.

---

## 3. Client Environment & Browser Requirements

- **Browser**: Modern web browser (Microsoft Edge or Google Chrome recommended).
- **Local File System Access**: Capability to download CSV datasets from this repository (`Data/` folder) and upload them to Microsoft Fabric.

---

## 4. Workshop Assets Verification

Ensure you have cloned or downloaded this repository to access the following datasets:
- [`Data/hospitals.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/hospitals.csv)
- [`Data/departments.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/departments.csv)
- [`Data/rooms.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/rooms.csv)
- [`Data/patients.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/patients.csv)
- [`Data/vitalsignequipment.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/vitalsignequipment.csv)
- [`Data/vitalsignsreadings.csv`](file:///c:/Users/Praveenr/Desktop/demo/fabricIQ%20workshop/Data/vitalsignsreadings.csv) (Time-series data for Real-Time Eventhouse streaming)

---

## Quick Navigation

[← Back to README](README.md) | [Start Exercise 00: Prerequisites Verification →](Exercises/00-Prerequisites.md)
