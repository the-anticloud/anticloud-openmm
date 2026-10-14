# Educators — OPENMM

**Project:** OPENMM  
**Category:** CHEMICAL_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `795d4dd660cf7e537ceb599fdb038c5388b33390`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `55446d5ad2e4009396ce36ed462417e367c4d636b8a47e76fde1634b1fca9160`  
**Date:** October 2026

## Teaching with OPENMM

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `55446d5ad2e4009396ce36ed462417e367c4d636b8a47e76fde1634b1fca9160` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
