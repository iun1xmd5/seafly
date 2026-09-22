# SEAFly: A Secure ....

[![Paper](https://img.shields.io/badge/paper-Smart%20Agricultural%20Technology-blue)](https://doi.org/XXXX)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)

Official implementation of the SEAFly framework, presented in:

> **SEAFly: ....**
> Authors


---

## Overview

SEAFly is a four-layer edge AIoT framework that co-designs:
1. **Edge AI inference** — quantised MobileNetV2 (INT8) for fruit fly detection
2. **In-line security** — device authentication, AES-128-CTR encryption, HMAC-SHA-256 integrity, replay protection
3. **Resilient communication** — MQTT publish/subscribe with store-and-forward buffering
4. **Resource efficiency** — duty-cycled sensing on Raspberry Pi hardware

The framework is evaluated on a two-tier prototype: a Raspberry Pi Zero W sensing node and a Raspberry Pi 4 edge gateway.

---

## Key Results

| Metric | Value |
|--------|-------|
| Detection accuracy | 95.00% |
| Recall | 96.91% |
| Macro-F1 | 91.57% |
| Mean inference latency | 233.86 ms |
| Peak memory | 178.0 MB |
| Energy per cycle | 3.245 J |
| Attack detection rate | 98.33% |
| Attack rejection rate | 96.33% |
| False-alarm rate | 2.00% |
| End-to-end latency overhead | +18.2% |
| Energy per cycle overhead | +23.9% |

---

## Repository Structure

- `seafly/` — core Python package (AI, security, communication, node, gateway)
- `configs/` — YAML configuration files for each experimental setup
- `experiments/` — scripts that reproduce every figure and table in the paper
- `scripts/` — hardware setup, key provisioning, deployment, benchmarking
- `data/` — dataset download and split scripts
- `figures/` — regenerated figures (matches paper graphicspath)
- `tests/` — unit tests for cryptographic primitives and metrics
- `docs/` — extended documentation
- `paper/` — LaTeX source for the manuscript

---

## Hardware Requirements

| Component | Specification |
|-----------|---------------|
| Sensing node | Raspberry Pi Zero W (512 MB RAM) |
| Camera | Pi Camera v2 (8 MP) |
| Environmental sensor | DHT22 temperature/humidity |
| Gateway | Raspberry Pi 4 Model B (4 GB RAM) |
| Power monitoring | INA219 (I²C) |
| Network | Wi-Fi 802.11 b/g/n (LoRa optional) |

A **mock mode** is provided (`--simulate`) for users without hardware, which reproduces the experiments using recorded telemetry.

---

## Installation

### Software dependencies

```bash
git clone https://github.com/iun1xmd5/BeyDet.git
cd BeyDet
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
pip install -e .
