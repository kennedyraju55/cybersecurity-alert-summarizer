<div align="center">

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![Ollama](https://img.shields.io/badge/Ollama-Local%20LLM-black?style=for-the-badge&logo=ollama&logoColor=white)](https://ollama.com)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)

**AI-Powered Threat Analysis & Triage**

[Features](#-features) • [Quick Start](#-quick-start) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Author](#author)

</div>

---

## 🎯 Overview

An AI-powered cybersecurity tool that analyzes security alerts, extracts Indicators of Compromise (IOCs), looks up CVE databases, calculates threat scores, correlates multiple alerts, and generates comprehensive threat summaries — all powered by a local LLM running through Ollama.

**Zero data leaves your network. 100% local processing.**

---

## 💡 The Problem It Solves

Security teams are overwhelmed with thousands of alerts daily. Manual triage is slow, error-prone, and leads to alert fatigue.

**Solution:** Automate alert triage with local AI — extract IOCs, score threats, correlate alerts, and generate executive summaries in seconds, with zero data leaving your network.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **🔍 IOC Extraction** | Auto-detect IPs, domains, hashes, URLs, file paths |
| **📊 Threat Scoring** | Weighted scoring with CVE, IOC density & keyword analysis |
| **🗂️ CVE Lookup** | Local CVE database with CVSS scores & vectors |
| **⚡ Alert Prioritization** | LLM-powered ranking by risk level |
| **🔗 Alert Correlation** | Cross-alert IOC and CVE correlation engine |
| **📋 Rich Reports** | Beautiful CLI output with Rich tables & panels |

---

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Ollama installed ([ollama.com](https://ollama.com/download))
- A local LLM model (e.g., `ollama pull llama3.2`)

### Installation

```bash
git clone https://github.com/kennedyraju55/cybersecurity-alert-summarizer.git
cd cybersecurity-alert-summarizer
pip install -r requirements.txt
```

### Docker Quick Start

```bash
docker-compose up
# Web UI at http://localhost:8501
```

### First Run

```bash
ollama pull llama3.2
python -m src.cyber_alert.cli --alert alerts/sample.txt
```

---

## 🏗️ Architecture

```
User Alert Input (text file)
        ↓
┌───────────────────┐
│ IOC Extraction    │ ← Regex-based pattern matching
│ (No LLM needed)   │
└────────┬──────────┘
         ↓
┌───────────────────┐
│ CVE Lookup        │ ← Query local database
│ (No LLM needed)   │
└────────┬──────────┘
         ↓
┌───────────────────┐
│ Threat Scoring    │ ← LLM-powered analysis
│ & Summarization   │
└────────┬──────────┘
         ↓
┌───────────────────┐
│ Alert Correlation │ ← Cross-alert matching
│ (No LLM needed)   │
└────────┬──────────┘
         ↓
     Rich Output
  (CLI or Web UI)
```

### How It Works

1. **IOC Extraction** — Identifies IPs, domains, hashes, URLs without needing an LLM
2. **CVE Database Lookup** — Checks extracted CVE IDs against local database
3. **Threat Scoring** — Uses LLM to analyze context and assign risk scores
4. **Alert Prioritization** — Ranks alerts by threat level
5. **Correlation Engine** — Links related alerts across multiple sources

---

## 📊 Tech Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Python 3.10+ |
| **LLM Backend** | Ollama (local inference) |
| **CLI Framework** | Click |
| **Web UI** | Streamlit |
| **REST API** | FastAPI |
| **Output Formatting** | Rich |
| **Testing** | pytest (85% coverage) |
| **Deployment** | Docker, Docker Compose |

---

## 📝 Project Structure

```
cybersecurity-alert-summarizer/
├── src/
│   └── cyber_alert/
│       ├── core.py          IOC extraction, CVE lookup, threat scoring
│       ├── cli.py           Click CLI with Rich output
│       └── config.py        YAML configuration loader
├── tests/
│   ├── test_core.py
│   └── test_cli.py
├── config.yaml
├── requirements.txt
└── docker-compose.yml
```

---

## 💻 Usage Examples

### Analyze a single alert
```bash
python -m src.cyber_alert.cli --alert alerts/sample.txt
```

### Extract IOCs only
```bash
python -m src.cyber_alert.cli --alert alerts/sample.txt --iocs
```

### Threat scoring
```bash
python -m src.cyber_alert.cli --alert alerts/sample.txt --score
```

### Prioritize multiple alerts
```bash
python -m src.cyber_alert.cli --alert alerts/multi.txt --prioritize
```

---

## 🧪 Testing

```bash
pytest tests/ -v --cov=src/cyber_alert
# Output: 85% coverage
```

---

## 🏠 Local vs ☁️ Cloud

| Feature | 🛡️ This Tool | ☁️ Cloud Alternatives |
|---------|-------------|----------------------|
| **Privacy** | ✅ 100% local | ❌ Data to servers |
| **Cost** | ✅ Free forever | ❌ Pay-per-use |
| **Speed** | ✅ No network latency | ❌ Internet dependent |
| **Offline** | ✅ Works offline | ❌ Requires internet |
| **Compliance** | ✅ Data stays on-premise | ⚠️ May violate policies |

---

## 👤 Author

**Nrk Raju Guthikonda**  
Senior Software Engineer @ Microsoft  
Copilot Search Infrastructure (Semantic Indexing, RAG)

- 🔗 GitHub: [@kennedyraju55](https://github.com/kennedyraju55)
- ✍️ Dev.to: [nrk-raju-guthikonda](https://dev.to/nrk_raju)
- 💼 LinkedIn: [nrk-raju-guthikonda](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8/)

---

## 📄 License

MIT License — See [LICENSE](LICENSE) for details.

---

<div align="center">

**Cybersecurity Alert Summarizer** — *AI-powered threat triage that respects your privacy.*

</div>
