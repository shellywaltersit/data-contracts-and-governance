# 📄 Data Contract Templates – EDH_PROD Lakehouse

## 🎯 Purpose

This folder contains YAML-based data contract templates designed to formalize expectations between data producers, data stewards, and engineering teams. These contracts serve as both:

- ✅ A **governance artifact** for approval and compliance
- ✅ A **deployment blueprint** for automated pipeline configuration
- ✅ A **source of truth** for metadata synchronization with Microsoft Purview

Each contract defines the structure, quality, access, and lineage of datasets across the **bronze**, **silver**, and **gold** layers of the `EDH_PROD` lakehouse.

---

## 🏗️ Naming Convention

Contracts follow a naming convention aligned with Microsoft Fabric lakehouse standards:

| Layer   | Example Table Name               | Description                                |
|---------|----------------------------------|--------------------------------------------|
| Bronze  | `bronze.wd_worker_demographics`  | Raw ingestion, minimal transformation      |
| Silver  | `silver.dim_worker`              | Cleaned, modeled, steward-approved         |
| Gold    | `gold.people_aggregated_data`    | Curated outputs (not covered in contract)  |

> ⚠️ Gold layer products are excluded from the contract to reduce complexity. They must be derived from silver tables to ensure access control inheritance.

---

## 🔐 Access Control

Access permissions are declared per layer using the `x-security` block. For example:

```yaml
x-security:
  bronze:
    allowedGroups: ["datahub-general", "datahub-troubleshooting"]
    piiExclusions: ["SSN"]
  silver:
    allowedGroups: ["datahub-analytics", "datahub-compliance", "datahub-general", "datahub-troubleshooting"]
    inheritedFrom: bronze
