# 🕵️‍♂️ Agentic Web Search Chatbot

An interactive AI chatbot that uses a **ReAct agent** to decide which tool to use, then searches the web, Wikipedia, or arXiv to answer your questions. The agent's thoughts and tool calls are displayed live in the UI.

## Features
- **Agentic reasoning**: a Zero-Shot ReAct agent chooses the best tool for each query
- **Three knowledge sources**: DuckDuckGo (live web), Wikipedia (general knowledge), arXiv (research papers)
- **Fast LLM inference**: Groq API with the `openai/gpt-oss-120b` model
- **Transparent thinking**: real-time display of agent steps via `StreamlitCallbackHandler`
- **Chat history** kept for the duration of the session
- **Secure key entry**: password-masked API key input in the sidebar
- **Error recovery** from malformed LLM output with `handle_parsing_errors`

## Tech Stack
Python · LangChain · Groq · Streamlit · DuckDuckGo Search · Wikipedia API · arXiv API

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/agentic-web-search-chatbot.git
cd agentic-web-search-chatbot
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the app
```bash
streamlit run app.py
```

### 4. Add your Groq API key
Enter your key in the sidebar. You can get one for free at [console.groq.com](https://console.groq.com).

## Example Queries
- "What is machine learning?"
- "Summarize the paper *Attention Is All You Need*"
- "What are the latest developments in quantum computing?"

## How It Works
1. The user submits a question.
2. The ReAct agent reasons about which tool fits best.
3. The tool (web, Wikipedia, or arXiv) returns a short result.
4. The agent uses that observation to produce the final answer.

## Project Structure
```
├── app.py
├── requirements.txt
└── README.md
```

## Requirements
```
streamlit
langchain
langchain-classic
langchain-community
langchain-groq
python-dotenv
wikipedia
arxiv
duckduckgo-search
```

## Future Improvements
- Add persistent memory across sessions
- Add source citations to answers
- Deploy on Streamlit Community Cloud

## License
MIT
