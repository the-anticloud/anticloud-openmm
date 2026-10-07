# Technical Architecture — OPENMM

**Upstream:** [https://github.com/SimTk/openmm](https://github.com/SimTk/openmm)
**License:** MIT
**Category:** CHEMICAL_MANUFACTURING
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Molecular simulation for chemical processes

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local process monitoring and yield optimization
2. AIOSS tamper-evident batch record chain (GMP/FDA aligned)
3. AES-256 encryption for all formulation and production data
4. Single-binary MES replacement for GMP-compliant isolated networks
5. Zero-cloud: all AI analytics and control run locally
6. GPU/CPU equalizer: spectroscopy AI on GPU, PLC control on CPU
7. Open OPC-UA/Modbus integration replacing proprietary DCS
8. Offline regulatory submission generator for FDA/EMA eCTD format

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_openmm.spec` or `go build -o openmm`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |