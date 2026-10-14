# Ethics — OPENMM

**Project:** OPENMM  
**Category:** CHEMICAL_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `795d4dd660cf7e537ceb599fdb038c5388b33390`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `55446d5ad2e4009396ce36ed462417e367c4d636b8a47e76fde1634b1fca9160`  
**Date:** October 2026

## Position

OPENMM is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
