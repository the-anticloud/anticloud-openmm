# Students — OPENMM

**Project:** OPENMM  
**Category:** CHEMICAL_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `795d4dd660cf7e537ceb599fdb038c5388b33390`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `55446d5ad2e4009396ce36ed462417e367c4d636b8a47e76fde1634b1fca9160`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `795d4dd660cf7e537ceb599fdb038c5388b33390`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `55446d5ad2e4009396ce36ed462417e367c4d636b8a47e76fde1634b1fca9160`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
