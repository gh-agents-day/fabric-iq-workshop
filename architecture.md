# Architecture & Data Flow Overview

This document describes the architectural flow and domain model for the **Lamna Healthcare** workshop solution, integrating **Microsoft Fabric IQ**, **Fabric Lakehouse**, **Ontology**, and **Microsoft Foundry Agent Service**.

---

## 1. End-to-End System Architecture

The workshop builds an end-to-end knowledge and agentic intelligence pipeline that connects raw operational healthcare tables to natural language conversational agents.

```mermaid
flowchart LR
    subgraph Data Layer["1. Data Ingestion & Storage"]
        CSV["Healthcare CSV Files<br/>(Hospitals, Departments, Rooms,<br/>Patients, VitalSignEquipment)"]
        LH["Microsoft Fabric Lakehouse<br/>(LamnaHealthcareLH Delta Tables)"]
        CSV -->|Upload & Load to Tables| LH
    end

    subgraph Fabric IQ Layer["2. Semantic & Knowledge Layer"]
        ONT["Fabric IQ Ontology<br/>(LamnaHealthcareOntology)"]
        ENT["Entity Types & Keys<br/>(Hospital, Department, Room,<br/>Patient, VitalSignEquipment)"]
        REL["Relationships<br/>(contains, has, assignedTo,<br/>monitors, locatedIn)"]
        
        LH -->|Data Binding| ONT
        ONT --- ENT
        ONT --- REL
    end

    subgraph Foundry Integration Layer["3. Foundry Intelligence Layer"]
        FKS["Foundry IQ Knowledge Source<br/>(Fabric IQ Connector)"]
        FKB["Foundry IQ Knowledge Base<br/>(LamnaHealthcareKnowledge)"]
        FAGT["Microsoft Foundry AI Agent<br/>(LamnaHealthcareAgent)"]

        ONT -->|Knowledge Export/Sync| FKS
        FKS -->|Index & Ground| FKB
        FKB -->|Grounding Tool| FAGT
    end

    subgraph User Experience Layer["4. User Interaction"]
        USER["Healthcare Practitioner / Analyst"]
        USER <-->|Natural Language Queries| FAGT
    end
```

---

## 2. Lamna Healthcare Ontology Domain Model

The **Lamna Healthcare** domain model formalizes operational entities and their relationships, enabling graph traversal and context-aware reasoning for the AI Agent.

```mermaid
erDiagram
    Hospital ||--o{ Department : "contains"
    Department ||--o{ Room : "has"
    Patient }|--|| Room : "assignedTo"
    VitalSignEquipment }|--|| Patient : "monitors"
    VitalSignEquipment }|--|| Room : "locatedIn"

    Hospital {
        string HospitalId PK
        string HospitalName
        string City
        string State
    }

    Department {
        string DepartmentId PK
        string DepartmentName
        string HospitalId FK
        int Floor
    }

    Room {
        string RoomId PK
        string RoomNumber
        string DepartmentId FK
        string RoomType
    }

    Patient {
        string PatientId PK
        string FirstName
        string LastName
        string DateOfBirth
        string AdmissionDate
        string CurrentRoomId FK
    }

    VitalSignEquipment {
        string EquipmentId PK
        string PatientId FK
        string EquipmentType
        string MonitoringStartDate
        string RoomId FK
    }
```

---

## 3. Key Components & Responsibilities

| Component | Technology | Primary Function |
| :--- | :--- | :--- |
| **Data Lakehouse** | Microsoft Fabric Lakehouse | Stores raw CSV data as Delta Lake tables (`hospitals`, `departments`, `rooms`, `patients`, `vitalsignequipment`). |
| **Semantic Data Layer** | Fabric IQ Ontology | Maps tabular Delta tables into domain entities, properties, keys, and graph relationships. |
| **Graph Query Engine** | Fabric IQ Query Builder | Validates ontology traversal (e.g. `PatientId 1001` → `Room` → `Equipment`). |
| **Knowledge Grounding** | Foundry IQ Knowledge Base | Connects Fabric IQ Ontology entities into Microsoft Foundry for enterprise RAG and reasoning. |
| **AI Agent** | Microsoft Foundry Agent | Uses system instructions and grounding tools to execute reasoning queries over healthcare data. |

---

## Quick Navigation

[← Back to README](README.md) | [View Prerequisites](prerequisites.md) | [Start Exercise 00 →](Exercises/00-Prerequisites.md)
