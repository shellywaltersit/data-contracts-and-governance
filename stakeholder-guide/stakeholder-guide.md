# 📘 Stakeholder Guide for Data Contracts

## 🎯 Purpose

This guide helps product owners, data stewards, and reviewers collaborate on data contracts in a consistent, compliant, and steward-friendly way. It complements the YAML template and HTML generator by providing standardized phrasing, examples, and decision support.

---

## 🧭 Roles & Responsibilities

| Role              | Responsibility |
|-------------------|----------------|
| **Product Owner** | Leads contract authoring, gathers stakeholder input |
| **Data Steward**  | Validates field definitions, classifications, and usage |
| **Data Owner**    | Approves contract terms and access controls |
| **Data Engineer** | Implements pipelines based on contract config |
| **Reviewer**      | Ensures spec compliance and clarity for non-technical users |

---

## 🧱 Required Blocks in Every Contract

| Block             | Description |
|------------------|-------------|
| `info`            | Title, version, owner, contact |
| `servers`         | Physical storage details (catalog, schema, format) |
| `models`          | Logical datasets and field definitions |
| `field`           | Field-level metadata, quality, classification |
| `lineage`         | Field transformations across layers |
| `quality`         | Reusable rule definitions |
| `terms`           | Usage, billing, limitations, policies |

---

## 🧩 Standardized Phrasing Library

### ✅ Usage Examples
- “Data may be used for internal analytics, reporting, and machine learning.”
- “Not suitable for external sharing or real-time use cases.”

### ✅ Billing Examples
- “Covered under enterprise data agreement.”
- “Consumption is tracked but not billed to individual teams.”

### ✅ Limitations Examples
- “SSN and other highly sensitive fields are excluded from silver layer.”
- “Gold products must derive from silver to preserve access control.”

### ✅ Policy Block Example
```yaml
policies:
  - name: "HIPAA Compliance"
    description: "Ensure no PHI is exposed beyond silver layer"
    url: "https://yourdomain.com/policies/hipaa"
