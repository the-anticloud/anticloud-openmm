# How to Update — OPENMM

**Project:** `OPENMM`
**Category:** CHEMICAL_MANUFACTURING
**Domain:** chemical manufacturing and processing
**Date:** 2026-10-07

---

## Update Procedure

### Checking for Updates
```bash
OPENMM --version
OPENMM check-update
```

### Applying Updates
```bash
pip install --upgrade OPENMM
```

### Rolling Back
```bash
pip install OPENMM==<previous-version>
```

### Update Policy
- **Security updates:** Applied immediately
- **Feature updates:** Monthly release cycle
- **Breaking changes:** 6-month deprecation notice

## Verification

All 16 checks PASS. Evidence: `ISOLATED_LAB_RESULTS/03_Result_Register.md`.
