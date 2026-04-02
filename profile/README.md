<div align="center">

# 🕉️ vedicreader

**Python-first developer tools for cloud, DevOps, and AI agents**

[![Website](https://img.shields.io/badge/🌐_Website-vedicreader.com-blue?style=for-the-badge)](https://vedicreader.com)
[![PyPI](https://img.shields.io/badge/PyPI-packages-orange?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/user/vedicreader/)
[![GitHub followers](https://img.shields.io/github/followers/vedicreader?style=for-the-badge&logo=github)](https://github.com/vedicreader)

</div>

---

## 🚀 What We Build

We craft **minimal, composable Python libraries** that automate the repetitive parts of cloud infrastructure, DevOps workflows, and AI agent development — so you can focus on what matters.

---

## 🛠️ Projects

### ⚡ Infrastructure & DevOps

| Package | Description | Install |
|---------|-------------|---------|
| [**fastops**](https://github.com/vedicreader/fastops) | End-to-end DevOps toolkit: Docker, VPS, DNS, Caddy, and CI/CD — all from Python | `pip install fastops` |
| [**vpseasy**](https://github.com/vedicreader/vpseasy) | Provision, configure, and deploy to cloud VPS (Hetzner + Multipass) | `pip install vpseasy` |
| [**dockeasy**](https://github.com/vedicreader/dockeasy) | Docker made easy — fluent Python API for images, containers, and Compose | `pip install dockeasy` |
| [**cfeasy**](https://github.com/vedicreader/cfeasy) | Cloudflare DNS and tunnel management from Python | `pip install cfeasy` |
| [**awseasy**](https://github.com/vedicreader/awseasy) | AWS resources made easy | `pip install awseasy` |
| [**gcpeasy**](https://github.com/vedicreader/gcpeasy) | GCP resources made easy | `pip install gcpeasy` |
| [**azeasy**](https://github.com/vedicreader/azeasy) | Azure resources made easy | `pip install azeasy` |

### 🤖 AI & Agent Tooling

| Package | Description | Install |
|---------|-------------|---------|
| [**karma**](https://github.com/vedicreader/karma) | Repo memory for AI agents — FTS5+vector code index, episodic decisions, and practice patterns | `pip install karma` |
| [**claude-plugins**](https://github.com/vedicreader/claude-plugins) | One-command Claude Code setup: hooks, MCP servers, and skills for the AnswerDotAI ecosystem | `pip install claude-plugins` |
| [**onneta**](https://github.com/vedicreader/onneta) | Stateful helpers for `onnxruntime-genai` | `pip install onneta` |

### 🧰 Developer Experience

| Package | Description | Install |
|---------|-------------|---------|
| [**shipit**](https://github.com/vedicreader/shipit) | Python project setup made easy | `pip install shipit` |
| [**gheasy**](https://github.com/vedicreader/gheasy) | GitHub made easy — automate repos, PRs, and workflows from Python | `pip install gheasy` |

---

## 💡 Philosophy

> **Small libraries, big leverage.**

Each package does one thing well and composes with the others. Whether you're deploying a Python webapp behind Caddy with a Cloudflare tunnel, or giving your AI agent a persistent memory of past decisions — you're never more than a `pip install` away.

```python
# From zero to a deployed app in minutes
from fastops import appfile, Compose, caddy, cloudflared_svc
from fastops import vps_init, create, deploy, dns_record

# Build configs
df = appfile(port=8080)
dc = (Compose()
    .svc('app', build='.', networks=['web'])
    .svc('caddy', **caddy('myapp.example.com', port=8080, cloudflared=True))
    .svc('cloudflared', **cloudflared_svc(), networks=['web'])
    .network('web'))

# Provision, deploy, point DNS
ip = create('prod-01', server_type='cx22', location='nbg1',
            cloud_init=vps_init('prod-01', pub_keys='...'))
deploy(dc, ip, key='~/.ssh/id_ed25519')
dns_record('example.com', 'myapp', ip, proxied=True)
```

---

## 🧠 AI-Native Development

We build tools that treat **AI coding agents as first-class users**. `karma` gives any agent (Claude, Copilot, GPT-4o, …) a persistent, searchable memory of your repo:

```python
from karma import index_repo, arun, build_dev_context

index_repo('.')  # index once, reuse forever
ctx = arun(build_dev_context('how to extend a class', repo_root='.'))
# → surfaces existing code, past decisions, and practices before writing a line
```

`claude-plugins` wires up hooks, MCP servers, and skills in a single command:

```bash
pip install claude-plugins
claude-plugins setup   # hooks + MCP + skills — live in Claude Code immediately
```

---

## 🔧 Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![FastHTML](https://img.shields.io/badge/FastHTML-000000?style=flat-square)
![nbdev](https://img.shields.io/badge/nbdev-Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![Hetzner](https://img.shields.io/badge/Hetzner-D50C2D?style=flat-square&logo=hetzner&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

---

<div align="center">

**[🌐 vedicreader.com](https://vedicreader.com)** · **[📦 PyPI](https://pypi.org/user/vedicreader/)** · **[🐙 GitHub](https://github.com/vedicreader)**

</div>
