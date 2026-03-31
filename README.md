# 🤖 Cyber Security LLM Agents

A collection of AI agents that use Large Language Models (LLMs) to perform 
automated tasks in cyber security operations — from EDR detection to threat 
analysis and report generation.

Built on top of [AutoGen](https://microsoft.github.io/autogen/) by Microsoft.

---

## 🧠 Project Goal

To demonstrate how LLM-powered autonomous agents can automate complex, 
repetitive cyber security workflows — reducing manual effort and enabling 
always-on security operations.

---

## 🏗️ Technical Architecture

The system follows a **multi-agent orchestration pattern**:
```
User Input
    ↓
AutoGen Orchestrator  ←→  LLM Core (GPT-4 / OpenAI API)
    ↓
┌─────────────────────────────────────────┐
│          Specialized Agents             │
│  EDR Detection | Threat Analysis        │
│  Code Execution | Report Generation     │
└─────────────────────────────────────────┘
    ↓
Tools & Integrations
│  Caldera | HTTP/FTP Server              │
│  Jupyter Notebooks | OpenAI .env        │
    ↓
Security Report / Findings
```

---

## 🔄 Agent Workflow

1. **Task Input** — Operator defines a security scenario
2. **Orchestration** — AutoGen routes the task to appropriate agents
3. **LLM Reasoning** — GPT-4 generates plans, code, and analysis
4. **Agent Execution** — Specialized agents run assigned sub-tasks
5. **Tool Usage** — Agents interact with Caldera, servers, scripts
6. **Report Output** — Findings compiled into structured security report

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Orchestration | Microsoft AutoGen | Multi-agent coordination |
| LLM | OpenAI GPT-4 | Reasoning and code generation |
| Language | Python 3.10+ | Core implementation |
| Notebooks | Jupyter | Demo and testing |
| Attack Emulation | Caldera | Adversary simulation |
| Servers | Python HTTP/FTP | Payload hosting for demos |
| Config | .env / dotenv | API keys and parameters |

---

## 📁 Project Structure
```
cyber-security-llm-agents/
│
├── agents/          # Individual LLM agent definitions
├── actions/         # Scenario and task configurations
│   └── agent_actions.py   # All scenarios defined here
├── tools/           # Supporting tools for agents
├── notebooks/       # Jupyter notebooks for demos
├── utils/           # Utility/helper functions
├── documentation/   # Videos and screenshots
├── run_agents.py    # Main entry point
├── run_servers.py   # HTTP/FTP server launcher
├── run_notebooks.sh # Notebook launcher script
├── requirements.txt # Python dependencies
└── .env_template    # API config template
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- OpenAI API key
- Virtual environment (recommended)

### Step 1 — Clone and install
```bash
git clone https://github.com/Shubhamharanale7/cyber-security-llm-agents.git
cd cyber-security-llm-agents
pip install -r requirements.txt
```

### Step 2 — Configure API keys
```bash
cp .env_template .env
```
Edit `.env` and add your OpenAI API key and other parameters.

### Step 3 — Test setup
```bash
python run_agents.py HELLO_AGENTS
```

### Step 4 — (Optional) Start HTTP/FTP servers
Only needed for demos involving payload hosting or exfiltration simulation:
```bash
python run_servers.py
```

---

## 🧩 Available Scenarios

All scenarios are defined in `actions/agent_actions.py`.

| Scenario | Description |
|----------|-------------|
| `HELLO_AGENTS` | Basic test — confirms setup is working |
| `DETECT_EDR` | Identifies EDR tools running on a Windows system |
| Custom | Add your own scenarios to `agent_actions.py` |

Run any scenario with:
```bash
python run_agents.py 
```

---

## 🔑 Key Concepts

### Multi-Agent Design
Multiple specialized agents collaborate on a task. Each agent has a defined 
role — coordinator, analyst, code executor — and communicates via AutoGen's 
message-passing framework.

### LLM-Driven Automation
Agents use GPT-4 to reason about security tasks, generate Python scripts, 
interpret tool outputs, and produce human-readable findings — all without 
manual intervention.

### Modular & Extensible
New agents, tools, and scenarios can be plugged in without changing the 
core framework. The design supports scaling from simple demos to full 
CI/CD security pipelines.

---

## ⚠️ Disclaimer

Running LLM-generated source code and commands poses a **security risk** 
to your host environment. Only run this project in a **virtual machine 
or isolated test environment**. Never run on production systems.

---

## 📜 License

Released under the **GNU General Public License v3 (GPL-3)**.

---

## 🙌 Feedback Welcome

Thank you for exploring my Cyber Security LLM Agents project!  
I'm always open to suggestions, improvements, or collaboration ideas.

📩 Connect with me on [LinkedIn](https://www.linkedin.com/in/shubhamharanale7)  
📧 Email: **shubhaminfosoft7@gmail.com**

Your feedback helps me grow. Let's connect and build something great!
