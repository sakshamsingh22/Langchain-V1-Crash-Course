# LLM Gateway Tutorial with LiteLLM and LangChain

A hands-on Jupyter notebook exploring how an LLM gateway can provide one interface across model providers and how that gateway can fit into LangChain-based applications.

> **Learning material attribution:** The notebook credits Krish Naik / KRISHAI Technologies. This repository is a learning implementation, not an independently authored production gateway.

## What the notebook covers

- Why applications use an LLM gateway between the app and model providers
- A unified completion interface with LiteLLM
- Loading provider credentials from environment variables with `python-dotenv`
- Calling models from different providers through a common interface
- Gateway patterns such as routing, fallbacks, caching, rate limiting, cost tracking, and observability
- Connecting gateway calls to LangChain workflows

The notebook is the primary learning artifact: [`llm_gateway_tutorial.ipynb`](./llm_gateway_tutorial.ipynb).

## Requirements

- Python **3.13 or newer** (as declared in `pyproject.toml`)
- Jupyter Notebook or JupyterLab
- API credentials for whichever hosted model providers you choose to call

## Setup

### Option A: pip

```bash
git clone https://github.com/sakshamsingh22/Langchain-V1-Crash-Course.git
cd Langchain-V1-Crash-Course

python -m venv .venv
source .venv/bin/activate
# Windows PowerShell: .venv\\Scripts\\Activate.ps1

python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

### Option B: uv

```bash
uv sync
uv run jupyter notebook
```

## Configure API keys

Create a local `.env` file in the repository root:

```dotenv
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
GROQ_API_KEY=your_groq_key
```

Only configure keys for providers you intend to use. Never commit `.env` or paste credentials into notebook cells. The notebook uses environment variables and `python-dotenv` for local configuration.

## Run the tutorial

1. Start Jupyter from the repository root.
2. Open `llm_gateway_tutorial.ipynb`.
3. Read the markdown explanations and execute cells in order.
4. Skip provider examples for which you have not configured credentials.
5. Monitor provider usage and costs when running live model calls.

## Important notes

- Model names and provider availability can change. Check the relevant provider and LiteLLM documentation if a call stops working.
- Hosted model calls may incur charges and are subject to provider rate limits.
- The notebook is educational material. It does **not** by itself provide a deployed gateway service, production authentication, tenant isolation, or operational monitoring.
- Do not commit API keys, generated secrets, or private datasets.

## Project structure

```text
.
├── llm_gateway_tutorial.ipynb
├── pyproject.toml
├── requirements.txt
└── README.md
```

## License and attribution

See [`LICENSE`](./LICENSE) for this repository's license. The tutorial notebook credits its original instructional source; retain that attribution when adapting the learning material.
