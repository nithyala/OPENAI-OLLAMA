# Enhanced Q&A Chatbot

A simple question-and-answer chatbot built with **Streamlit** and **LangChain**, with two versions: one powered by **OpenAI** models and one powered by **open-source models via Ollama**. Both include **LangSmith** tracing for monitoring.

## 🔗 Live Demo

Try the OpenAI version here: **[Launch App](https://ai-agent-kxdsxmicbcmf7gmjr89vng.streamlit.app)**

> ⚠️ The app asks you to enter your own OpenAI API key in the sidebar — bring your own key to get a response.

## 📂 Project Files

| File | Description |
|------|-------------|
| `main.py` | Q&A chatbot using **OpenAI** models (gpt-4o, gpt-4-turbo, gpt-4). Requires an OpenAI API key. This is the version deployed in the live demo. |
| `app.py` | Q&A chatbot using **open-source models via Ollama** (e.g. Mistral). **Runs locally only** — needs Ollama installed on your machine, so it cannot be deployed to Streamlit Cloud. No API key needed. |

## ✨ Features

- Clean Streamlit web interface
- Choice of model from a sidebar dropdown
- Adjustable **temperature** and **max tokens** sliders
- LangSmith tracing for observability
- Two backends: cloud (OpenAI) and local/open-source (Ollama)

## 🛠️ Tech Stack

- [Streamlit](https://streamlit.io/) — web UI
- [LangChain](https://www.langchain.com/) — prompt templating and chaining
- [OpenAI](https://openai.com/) — LLM backend (`main.py`)
- [Ollama](https://ollama.com/) — local open-source LLMs (`app.py`)
- [LangSmith](https://smith.langchain.com/) — tracing and monitoring

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

If you don't have a `requirements.txt` yet, install the core packages:

```bash
pip install streamlit langchain langchain-openai langchain-community python-dotenv openai
```

### 3. Set up environment variables

Create a `.env` file in the project root:

```
LANGCHAIN_API_KEY=your-langchain-api-key
```

(For the OpenAI app, you enter your OpenAI API key directly in the app's sidebar — no need to put it in `.env`.)

### 4. Run an app

**OpenAI version:**

```bash
streamlit run main.py
```

**Ollama version** — runs **locally only**. Make sure [Ollama](https://ollama.com/) is installed and running, and you've pulled a model:

```bash
ollama pull mistral
streamlit run app.py
```

> ℹ️ `app.py` connects to a local Ollama server (`localhost:11434`), so it works on your own machine but **cannot run on Streamlit Cloud**, where Ollama isn't available. Only the OpenAI version (`main.py`) is deployed as the live demo — this is by design, not a bug.

## 📝 Notes

- On **Streamlit Cloud**, secrets like `LANGCHAIN_API_KEY` are stored under **Manage app → Settings → Secrets** rather than in a `.env` file.
- The Ollama version (`app.py`) runs models locally, so it works offline but needs Ollama installed on the machine running it. It is **not deployable to Streamlit Cloud** — only `main.py` (OpenAI) is hosted as the live demo.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
