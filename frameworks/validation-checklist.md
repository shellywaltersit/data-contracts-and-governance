# ✅ Data Contract Validation Checklist

Use this checklist to manually review each contract before approval.

## 🔍 Metadata
- [ ] `id` is unique and descriptive
- [ ] `title` and `description` clearly explain the contract's purpose
- [ ] `owner` and `contact` are valid and reachable

## 🧱 Models
- [ ] Model names use only letters, numbers, underscores, or hyphens
- [ ] Each model includes `type`, `title`, `description`, and `field`
- [ ] `x-layer` is declared (bronze, silver, gold)
- [ ] Field names are clear and follow naming conventions
- [ ] `classification` uses only approved values
- [ ] `quality` rules are named consistently and reused from rule library

## 🧪 Quality & Lineage
- [ ] `quality` block includes reusable rules like `non_null`
- [ ] `lineage` includes `catalog`, `schema`, `name`, and `field`
- [ ] Transformations are described clearly and accurately

## 🔐 Access & Security
- [ ] `x-security` includes allowedGroups and piiExclusions
- [ ] Access controls match organizational policy

## 📦 Servers
- [ ] Each server includes `catalog`, `schema`, `environment`, `location`, and `format`
- [ ] Locations use parameterized paths (`{model}`)

## 📜 Terms
- [ ] `usage`, `billing`, and `limitations` use approved phrasing
- [ ] `noticePeriod` is declared
- [ ] `policies` include name, description, and URL

## 🧩 Optional Blocks
- [ ] `definitions` are used for reusable fields
- [ ] `externalDocs` link to steward-facing resources
- [ ] `x-purview` includes assetName, collection, and qualifiedName

## ✅ Final Checks
- [ ] YAML passes schema validation
- [ ] Contract renders cleanly in HTML preview
- [ ] Stakeholders have reviewed and approved
