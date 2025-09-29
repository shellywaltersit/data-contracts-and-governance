# 🛡️ Sensitivity & Regulation Guide

This guide defines sensitivity classifications and maps them to relevant regulations, policies, and handling strategies.

---

## 🔐 Security Classifications

| Classification       | Description |
|----------------------|-------------|
| `restricted`         | Most sensitive (e.g., SSN, PHI, student ID) |
| `highly_sensitive`   | Sensitive but not regulated (e.g., internal salary bands) |
| `sensitive_internal` | Internal use only (e.g., job titles, org charts) |
| `public`             | Safe for external sharing (e.g., department names)

---

## 📜 Regulatory Mapping

| Regulation | Applies To | Notes |
|-----------|------------|-------|
| **GLBA**  | Financial data | Applies to student financial aid, banking info |
| **GDPR**  | Personal data of EU residents | Requires consent, right to erasure |
| **COPPA** | Children under 13 | Applies to student living and records |
| **FERPA** | Student education records | Applies to studentadministration and studentservices domains |
| **HIPAA** | Health data | Applies to health domain and PHI fields |

---

## 🧩 Handling Strategy Mapping

| Regulation | Recommended Strategy |
|------------|----------------------|
| GLBA       | `exclude` or `mask` |
| GDPR       | `mask` or `nullify` |
| COPPA      | `exclude` |
| FERPA      | `exclude` or `mask` |
| HIPAA      | `exclude` or `mask`

---

## ✅ Authoring Tips

- Declare sensitive fields using `classification:` and `tags:`
- Use `handling:` strategies in `x-security` blocks
- Reference applicable regulations in `terms.policies`
- Validate contracts against this guide before approval
