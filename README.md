<!-- BlackRoad SEO Enhanced -->

# hailo vision

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad Forge](https://img.shields.io/badge/Org-BlackRoad-Forge-2979ff?style=for-the-badge)](https://github.com/BlackRoad-Forge)
[![License](https://img.shields.io/badge/License-Proprietary-f5a623?style=for-the-badge)](LICENSE)

**hailo vision** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

## About BlackRoad OS

BlackRoad OS is a sovereign computing platform that runs AI locally on your own hardware. No cloud dependencies. No API keys. No surveillance. Built by [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc), a Delaware C-Corp founded in 2025.

### Key Features
- **Local AI** — Run LLMs on Raspberry Pi, Hailo-8, and commodity hardware
- **Mesh Networking** — WireGuard VPN, NATS pub/sub, peer-to-peer communication
- **Edge Computing** — 52 TOPS of AI acceleration across a Pi fleet
- **Self-Hosted Everything** — Git, DNS, storage, CI/CD, chat — all sovereign
- **Zero Cloud Dependencies** — Your data stays on your hardware

### The BlackRoad Ecosystem
| Organization | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform and applications |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate and enterprise |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | Artificial intelligence and ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware and IoT |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity and auditing |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing research |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | Autonomous AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh and distributed networking |
| [BlackRoad Education](https://github.com/BlackRoad-Education) | Learning and tutoring platforms |
| [BlackRoad Labs](https://github.com/BlackRoad-Labs) | Research and experiments |
| [BlackRoad Cloud](https://github.com/BlackRoad-Cloud) | Self-hosted cloud infrastructure |
| [BlackRoad Forge](https://github.com/BlackRoad-Forge) | Developer tools and utilities |

### Links
- **Website**: [blackroad.io](https://blackroad.io)
- **Documentation**: [docs.blackroad.io](https://docs.blackroad.io)
- **Chat**: [chat.blackroad.io](https://chat.blackroad.io)
- **Search**: [search.blackroad.io](https://search.blackroad.io)

---


[![CI](https://github.com/blackboxprogramming/hailo-vision/actions/workflows/ci.yml/badge.svg)](https://github.com/blackboxprogramming/hailo-vision/actions/workflows/ci.yml)
[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-3776AB.svg)](https://python.org)
[![Hailo-8](https://img.shields.io/badge/Hailo--8-26_TOPS-FF6B2B.svg)](https://hailo.ai)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-detection-00D4FF.svg)](https://ultralytics.com)
[![Edge AI](https://img.shields.io/badge/edge-real_time-CC00AA.svg)](https://blackroad.io)



Computer vision inference on Hailo-8 AI accelerators (26 TOPS each). Runs YOLOv5 object detection on Raspberry Pi 5 edge hardware via the Hailo Platform SDK 4.23.0.

## Hardware

- **2x Hailo-8** accelerators (52 TOPS total)
- Octavia (Pi 5) — primary inference node
- Cecilia (Pi 5) — secondary

## API

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Upload UI |
| `/health` | GET | Hailo device status |
| `/detect` | POST | Upload image, get YOLOv5 detections (multipart/form-data) |

## Detection Response

```json
{
  "objects": [{"label": "person", "confidence": 0.95, "bbox": [0.1, 0.2, 0.8, 0.9]}],
  "inference_ms": 12,
  "total_ms": 450,
  "device": "Hailo-8 (26 TOPS)",
  "model": "yolov5s"
}
```

## Run

```bash
pip install -r requirements.txt
python server.py  # http://localhost:8200
```

## Test

```bash
pip install pytest
pytest tests/
```
