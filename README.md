# Multi-Agent AI Research System with LangChain

A multi-agent research workflow built with Python, LangChain, and Streamlit for automated web-based research, article scraping, report generation, and critique.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.10+" />
  <img src="https://img.shields.io/badge/LangChain-Framework-000000?style=for-the-badge" alt="LangChain" />
  <img src="https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit" />
</p>

## Overview

This project demonstrates a research pipeline where multiple specialized agents collaborate to:

- search the web for relevant sources
- identify the most useful links
- scrape deeper content from a selected URL
- write a structured research report
- critique the report for quality and improvements

The app combines:

- LangChain agents for task-based reasoning
- LangGraph-style orchestration flow
- OpenAI models for language generation
- Tavily search for web discovery
- BeautifulSoup for content extraction
- Streamlit for a polished user interface

---

## Architecture

The system is organized into a 4-step workflow:

1. Search Agent
   - Finds recent and relevant sources for the user topic.
2. Reader Agent
   - Selects the best URL and scrapes deeper content.
3. Writer Chain
   - Produces a structured research report.
4. Critic Chain
   - Reviews the quality of the report and suggests improvements.

---

## Project Structure

```text
.
├── agents.py          # Agent and writer/critic chain definitions
├── app.py             # Streamlit UI for the research workflow
├── pipeline.py        # CLI-based research pipeline runner
├── tools.py           # Search and scraping tools
├── requirements.txt   # Python dependencies
├── .env               # Local environment variables (not committed)
└── README.md          # Project documentation
```

---

## Features

- AI-powered research workflow
- Web search using Tavily
- URL scraping and content extraction
- Structured report writing
- Quality critique of generated reports
- Streamlit web interface
- CLI execution for non-UI usage

---

## Tech Stack

- Python
- LangChain
- LangChain OpenAI
- Tavily
- BeautifulSoup
- Streamlit
- python-dotenv

---

## Prerequisites

Before running the project, make sure you have:

- Python 3.10 or newer
- A valid OpenAI API key
- A Tavily API key
- Internet access for web search and scraping

---

## Setup

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd "Multi-Agent AI Research System with LangChain"
```

### 2. Create a virtual environment

Using venv:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Or using uv:

```bash
uv venv
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

Or:

```bash
uv pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root with the following values:

```env
OPENAI_API_KEY=your_openai_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

> Note: The app uses OpenAI for LLM calls and Tavily for web search. If either key is missing or invalid, the workflow will fail.

---

## Running the App

### Streamlit UI

```bash
streamlit run app.py
```

This launches the research assistant in your browser.

### Command-line runner

```bash
python pipeline.py
```

Then type a research topic when prompted, such as:

```text
what is the impact of war on stock market
```

---

## Example Workflow

User input:

```text
What is the latest research on multi-agent AI systems?
```

The system will:

- search the web for relevant sources
- select top results
- scrape the most useful URL
- summarize the findings
- generate a final report
- provide critique feedback

---

## Important Notes

### API billing

The OpenAI integration requires available credits in your OpenAI account. If your API usage is exhausted, the app will fail with a `429` quota error.

### Web scraping limitations

Some websites block automated scraping or require JavaScript to render content. In those cases, the content may be unavailable or replaced by anti-bot pages.

For best results:

- use allowlisted public sites
- prefer APIs where possible
- avoid heavily protected websites for scraping

---

## License

This project is provided for educational and research purposes.

---

## Contributing

Contributions are welcome. If you want to improve the project:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## Contact

For questions or feature ideas, open an issue or start a discussion in the repository.

---

## Summary

This project is a practical example of a multi-agent research pipeline that demonstrates how AI agents can work together to search, read, write, and review research content automatically.
