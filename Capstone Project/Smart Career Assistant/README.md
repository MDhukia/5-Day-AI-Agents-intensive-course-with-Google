**Smart Career Assistant — RAG + Agents Project (Google ADK + Gemini)**

This project implements an AI-powered Career Assistant Agent using Google ADK, Gemini 2.5 Flash, and tool calling.
It analyzes resumes, extracts skills, retrieves real-time job market information, and generates personalized career guidance.

**🚀 Project Features**

**✅ 1. AI Career Assistant Agent**

Built using google.adk.agents.Agent.

Uses Gemini 2.5 Flash Lite model.

Provides professional answers in bullet points.

**✅ 2. Resume Analyzer**

Extracts skills using a custom Python function.

Summarizes the resume.

Suggests suitable job roles.

Provides improvement recommendations.

**✅ 3. Google Search Integration**

Uses google_search tool for:

Skills trending in 2025

Salary insights

Market demand verification

**✅ 4. Cover Letter Generator**

Generates short, professional cover letters based on extracted skills.

**✅ 5. PDF Resume Upload & Parsing**

Upload a .pdf resume through Kaggle notebook.

Extract text using pdfplumber.

Automatically feed extracted text into the Agent.

**📂 Project Structure**


├── Skill Extractor (Python Function)
├── Smart Career Agent Setup
│   ├── Gemini Model
│   ├── google_search Tool
│   ├── InMemoryRunner
├── Demo Workflows
│   ├── Career Guidance (Q&A)
│   ├── Resume Analyzer
│   ├── Salary Checker
│   ├── Cover Letter Generator
└── PDF Resume Upload Tools

**🛠️ Technologies Used**

Python

Google ADK (Agents Development Kit)

Google Gemini 2.5 Flash Lite

google_search tool

pdfplumber (PDF text extraction)

Kaggle Notebook environment

**📘 How It Works**

**Step 1 — Load API Key**

Use Kaggle Secrets:

client = UserSecretsClient()
GOOGLE_API_KEY = client.get_secret("GOOGLE_API_KEY")

**Step 2 — Create the SmartCareer Agent**

root_agent = Agent(
    name="smart_career_agent",
    model=Gemini(model="gemini-2.5-flash-lite", retry_options=retry_config),
    instruction=career_instruction,
    tools=[google_search]
)

**Step 3 — Run Queries**

Example:

response = await ask_agent("What skills do I need for a junior data scientist role?")

**Step 4 — Resume Upload Workflow**

Upload PDF to /kaggle/input/...

Extract text with pdfplumber

Process with the AI agent


**📑 Skill Extraction Logic**

The project includes a local Python tool:

SKILLS_DB = ["python", "sql", "aws", "tableau", ...]


It finds all matching skills inside the resume text.


**📈 Demo Outputs**

The notebook includes demonstrations for:

✔ Career Q&A

✔ Resume Summary

✔ Job Role Matching

✔ Skill Extraction

✔ Salary Range Finder

✔ Cover Letter Generation

**📄 PDF Resume Processing**

Upload PDF → Extract Text → Analyze with AI Agent.

resume_path = "/kaggle/input/.../resume.pdf"
resume_text = load_resume_from_pdf(resume_path)

**🔮 Future Improvements**

Add job description matching

Add streamlit web UI

Use vector database + RAG for long resumes

Build automated resume scoring system
