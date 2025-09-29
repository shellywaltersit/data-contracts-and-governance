# 📜 Data Contract Change Log Template

Use this template to document changes across versions of a data contract. Each entry should clearly describe what changed, why, and whether it impacts consumers.

---

## Version 1.2.0 – 2025-09-28
**Change Type**: MINOR  
**Summary**:
- Added new model `silver.dim_worker`
- Introduced `valid_student_id` quality rule
- Updated lineage for `ssn` field to exclude from silver

**Impact**:
- No breaking changes
- Consumers of `silver.dim_worker` must validate new field formats

**Approvals**:
- ✅ Product Owner: Enterprise Data Hub Team
- ✅ Data Steward: Worker Data Steward Group
- ✅ Data Executive: HCM Data Executive

---

## Version 1.1.0 – 2025-08-15
**Change Type**: MINOR  
**Summary**:
- Added `budget` subdomain to finance
- Introduced `valid_zip_code` rule

**Impact**:
- No breaking changes
- `budget` consumers must review masking logic

**Approvals**:
- ✅ Product Owner: Enterprise Data Hub Team
- ✅ Data Steward: Budget Data Steward Group
- ✅ Data Executive: Finance Data Executive
