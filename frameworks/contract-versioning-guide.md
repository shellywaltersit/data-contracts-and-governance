# 📦 Data Contract Versioning Guide

This guide defines how to version data contracts in a way that preserves compatibility, supports automation, and aligns with governance policies.

---

## 🔢 Semantic Versioning Format

Use `MAJOR.MINOR.PATCH` format for all contracts:

| Segment | Meaning |
|--------|---------|
| `MAJOR` | Breaking changes (e.g., field removal, type change, classification change) |
| `MINOR` | Additive changes (e.g., new fields, new models, new quality rules) |
| `PATCH` | Non-breaking fixes (e.g., typo corrections, description updates, formatting)

Example: `1.2.0` → added new model; `1.2.1` → fixed lineage typo

---

## 🧭 When to Increment

| Change Type | Version Impact | Notes |
|-------------|----------------|-------|
| Remove or rename a field | MAJOR | Breaks downstream consumers |
| Change field type or classification | MAJOR | May affect masking, access, or validation |
| Add new field or model | MINOR | Safe if optional or non-breaking |
| Update description or tags | PATCH | No impact on schema or automation |
| Add new quality rule | MINOR | Safe if rule is optional or scoped |
| Change lineage logic | MINOR or MAJOR | Depends on impact to downstream layers |
| Update terms or policies | MINOR or PATCH | Use discretion based on enforcement scope |

---

## 🧪 Validation Before Release

- [ ] Contract passes schema validation
- [ ] HTML preview is clear and steward-friendly
- [ ] Version bump follows semantic rules
- [ ] Change log is updated
- [ ] Stakeholders have reviewed and approved

---

## 📜 Change Log Format

Use `change-log-template.md` to document updates:

```markdown
## Version 1.2.0 – 2025-09-28
- Added new model `silver.dim_worker`
- Introduced `valid_student_id` quality rule
- Updated lineage for `ssn` field to exclude from silver
