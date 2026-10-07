# Build and Test

**Project:** `OPENMM`
**Upstream:** https://github.com/SimTk/openmm
**License:** MIT

## Quick Start

```bash
git clone https://github.com/SimTk/openmm
cd openmm
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local process monitoring and yield optimization
2. AIOSS tamper-evident batch record chain (GMP/FDA aligned)
3. AES-256 encryption for all formulation and production data
4. Single-binary MES replacement for GMP-compliant isolated networks
5. Zero-cloud: all AI analytics and control run locally
6. GPU/CPU equalizer: spectroscopy AI on GPU, PLC control on CPU
7. Open OPC-UA/Modbus integration replacing proprietary DCS
8. Offline regulatory submission generator for FDA/EMA eCTD format

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
