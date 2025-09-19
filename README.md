🚀 Jira Supervisor Agent

An intelligent automation that fetches, summarizes, and emails Jira defect reports using multi-agent architecture (LangChain + LangGraph).
Built with Python 3.13 • Designed & coded by Thumma Sai Kumar

🌟 Why This Project Stands Out

Real-world impact: Solves a common problem for QA & PM teams — getting quick, daily summaries of open defects.

Modern stack:

🐍 Python 3.13

🤖 LangChain & LangGraph (multi-agent orchestration)

📬 Mailtrap SMTP for notifications

☁️ Google Vertex AI for LLM summarization

Clean DevOps workflow: versioned with Git, environment-isolated, and CI-ready.

🧭 How It Works
graph TD
    A[Supervisor Agent] -->|Requests defects| B[Jira Agent]
    B -->|JSON data| A
    A -->|Pass data| C[Summarize Agent]
    C -->|Generate email| D[SMTP Tool]


Supervisor → manages workflow.

Jira Agent → collects all open defects from the LMS Jira project.

Summarize Agent → condenses defects into a neat report.

Email Tool → delivers the summary to all@qt.com.

🛠️ Tech Highlights

Python packaging: pyproject.toml with proper dependencies.

Config management: .env for credentials and API keys.

Secure by design: secrets kept out of source control.

Extensible: easy to plug in other models or notification channels.

⚙️ Quick Start
1️⃣ Clone & Install
git clone https://github.com/Sai2932000/jira-supervisor-agent.git
cd jira-supervisor-agent
python -m venv venv
source venv/bin/activate  # (Windows: venv\Scripts\activate)
pip install -e .

2️⃣ Configure

Create a .env file (see .env.example):

JIRA_API_TOKEN=your_token
JIRA_USERNAME=you@company.com
JIRA_INSTANCE_URL=https://yourcompany.atlassian.net
SMTP_HOST=sandbox.smtp.mailtrap.io
SMTP_PORT=2525
SMTP_USERNAME=...
SMTP_PASSWORD=...
FROM_EMAIL=yourcompany@mail.com
MODEL_ID=gemini-2.5-flash
MODEL_PROVIDER=google_vertexai


Never commit .env or application_default_credentials.json.

3️⃣ Run
python -m jira_agent.supervisor


You’ll receive an email titled “Summary of Defects” 🎉

💼 Skills Demonstrated

Building multi-agent systems (LangChain / LangGraph).

Integrating third-party APIs (Jira REST, Mailtrap).

Designing clean project structure & packaging (PEP-621).

Secure environment management.

Writing clear documentation and Git history.

📌 This project is a showcase of how I design production-ready Python tools that solve business problems.

🛣️ Future Enhancements

Slack / MS Teams notifications.

Support for multiple Jira projects.

Automated daily scheduling (GitHub Actions / cron).

Retry logic & monitoring dashboards.
