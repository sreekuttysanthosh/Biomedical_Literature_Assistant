# 🧬 AI Biomedical Literature Assistant


A **Streamlit-based AI application** that helps users explore biomedical research by searching **PubMed**, retrieving scientific publications, and using **Google Gemini** to analyze the retrieved literature.

The application provides a research-oriented summary of biomedical evidence, including key findings, common themes, research methods, limitations, potential research gaps, and future research directions.

Access to the this : https://biomedicalliteratureassistant-ck3kw2cgmrdnjxfrsoizts.streamlit.app/

## 🎯 Project Objective
Biomedical researchers often need to review a large number of scientific publications to understand a research topic.

This project provides a simple interface for:

- 🔎 Searching biomedical literature
- 📚 Retrieving relevant PubMed publications
- 🧾 Extracting publication information and abstracts
- 🤖 Analyzing retrieved literature using Google Gemini
- 💡 Identifying potential research gaps
- 📄 Exporting results as Word and PDF documents

---

---

##  Problem Statement

### Problem Statement

Biomedical researchers often need to search and analyze large amounts of scientific literature, but manually identifying relevant papers, extracting key findings, comparing studies, and identifying potential research gaps can be time-consuming. **The AI Biomedical Literature Assistant** addresses this problem by providing an AI-assisted system that retrieves relevant publications from PubMed and uses Google Gemini to summarize findings, identify common themes, analyze research methods and limitations, and suggest potential research gaps.

---
---

## 📐 Architecture

```text
          
 User
                     │
                     ▼
          ┌─────────────────────┐
          │   Research Topic    │
          │       Input         │
          └─────────────────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │   PubMed Search     │
          │     BioPython       │
          └─────────────────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Retrieve Scientific │
          │    Publications     │
          └─────────────────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Extract Evidence    │
          │ Title • Authors     │
          │ Abstract • PMID     │
          └─────────────────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │   Google Gemini     │
          │   AI Analysis       │
          └─────────────────────┘
                     │
                     ▼
       ┌─────────────────────────────┐
       │     Research Insights       │
       │                             │
       │ • Literature Summary        │
       │ • Key Findings              │
       │ • Common Themes             │
       │ • Research Methods          │
       │ • Limitations               │
       │ • Potential Research Gaps  │
       │ • Future Directions         │
       └─────────────────────────────┘
                     │
                     ▼
             PDF / Word Export
```
---
## 🚀 Features

### 🔎 PubMed Literature Search

Users can enter a biomedical research topic and retrieve relevant publications from PubMed.

The application retrieves:

- Publication title
- Authors
- Journal
- Publication year
- PMID
- Abstract
- PubMed publication link


---



---

### 🤖 AI-Powered Literature Analysis

Google Gemini analyzes the retrieved PubMed evidence and generates:

- Overall Literature Summary
- Key Findings
- Common Themes
- Research Methods
- Limitations
- Potential Research Gaps
- Future Research Directions

The AI analysis is restricted to the retrieved evidence to reduce unsupported claims.


### 📥 Export Results

Users can download the literature search and analysis as:

- 📄 Microsoft Word document
- 📕 PDF document

---
## 🧠 Application Workflow
```text
User enters biomedical topic
            │
            ▼
      PubMed Search
            │
            ▼
   Retrieve Publications
            │
            ▼
 Extract Metadata & Abstracts
            │
            ▼
      Google Gemini
            │
            ▼
    Literature Analysis
            │
            ▼
 Summary • Findings • Themes
 Limitations • Research Gaps
            │
            ▼
       PDF / Word Export
```
---
##  🛠️ Tech Stack

| Technology    | Purpose                         |
| ------------- | ------------------------------- |
| Python        | Application development         |
| Streamlit     | Web application interface       |
| BioPython     | PubMed / NCBI interaction       |
| PubMed        | Biomedical literature database  |
| Google Gemini | AI-powered literature analysis  |
| python-dotenv | Environment variable management |
| python-docx   | Word document generation        |
| ReportLab     | PDF generation                  |


---

## Project Structure

```text
Biomedical_Literature_Assistant/
│
├── app.py                  # Main Streamlit application
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
├── .gitignore              # Files excluded from Git
└── .env                    # API key configuration (not uploaded)
```
---
##  ⚙️ Setup
1. Clone the repository
```text
git clone <repository-url>
cd Biomedical_Literature_Assistant
```
2. Create a virtual environment
Creating a virtual environment is recommended.
```text
python -m venv myenv
```
Windows PowerShell
```text
myenv\Scripts\Activate.ps1
```
macOS / Linux
```text
source myenv/bin/activate
```
3. Install dependencies
```text
pip install -r requirements.txt
```
4. Configure the Gemini API key
Create a .env file in the project directory:
```text
GEMINI_API_KEY=your_gemini_api_key_here
```
Replace your_gemini_api_key_here with your own Gemini API key.

The .env file is excluded from GitHub using .gitignore.

Important: Never upload your API key or .env file to GitHub.

5. Run the application
Start the Streamlit application:
```text
streamlit run app.py
```
The application will open in your browser at:
```text
http://localhost:8501
```
---



### 🖥️Usage

1. Enter a research topic
Enter a biomedical research topic into the search box
Example:
```text
Antibiotic resistance in Pseudomonas aeruginosa
```
2. Select the number of papers
Choose the number of PubMed publications to retrieve.
The application currently supports:
```text
3 – 10 publications
```
3. Search PubMed
Click:
```text
🔎 Search Literature
```
4. Review retrieved publications
For each publication, the application displays:

Publication title
Authors
Journal
Publication year
PMID
Abstract
PubMed publication link

5. Analyze the literature using Gemini

Click:
```text
🤖 Analyze Literature with Gemini
```
The retrieved publication information is provided to Gemini for AI-assisted literature analysis.

6. Explore research insights
The application generates the following sections:
```text
Overall Literature Summary

Key Findings

Common Themes

Research Methods

Limitations

Potential Research Gaps

Future Research Directions

Important Note
```
The analysis is designed to distinguish between reported evidence and suggested research directions.

7. Export the analysis
The application allows users to download the retrieved literature and analysis as:

* 📄 Microsoft Word document
* 📕 PDF document
-------
## 🔬 PubMed Integration
The application uses BioPython Entrez to communicate with the NCBI PubMed database.

The search workflow is:
```text
Research Topic
      │
      ▼
PubMed Query
      │
      ▼
PMID Retrieval
      │
      ▼
PubMed XML Records
      │
      ▼
Metadata Extraction
      │
      ├── Title
      ├── Authors
      ├── Journal
      ├── Year
      ├── PMID
      └── Abstract
```
This information is then passed to the AI analysis component.
-------

## 🤖 AI Literature Analysis

Google Gemini is used to analyze the retrieved biomedical evidence.

The AI analysis focuses on:

**Overall Literature Summary**

Provides a concise overview of the retrieved literature.

**Key Findings**

Identifies major findings supported by the retrieved publications.

**Common Themes**

Identifies recurring biological, molecular, clinical, methodological, or technological themes.

**Research Methods**

Summarizes methods, models, experiments, and analytical approaches mentioned in the retrieved papers.

**Limitations**
Reports limitations supported by the available publication information.

**Potential Research Gaps**

Highlights possible areas requiring additional investigation.

**Future Research Directions**

Suggests reasonable directions based on the retrieved evidence.

----
## 🛡️Evidence-Based Analysis
The application instructs the AI to analyze only the retrieved PubMed evidence.

The analysis prompt includes safeguards against:

Fabricating findings
Inventing experimental results
Inventing numerical results
Unsupported claims
Presenting suggestions as established findings

Potential research gaps and future research directions are explicitly presented as suggestions rather than confirmed scientific facts.


## 📊 Example Research Scenario
A researcher interested in:
```text
Antibiotic resistance in Pseudomonas aeruginosa
```
can use the application to retrieve relevant PubMed publications.

The application then provides an AI-assisted synthesis covering:

What the retrieved studies report
Major findings
Recurring research themes
Research methodologies
Reported limitations
Potential research gaps
Possible future research directions

This can help users quickly orient themselves to a biomedical research topic before reading the original publications in detail.

-----
## 🔐 Security
API credentials are stored locally using environment variables.
The project uses:
```text
.env
```
for storing the Gemini API key.

The .env file is excluded from version control through:
```text
.gitignore
```
Never commit:
```text
.env
API keys
Secret credentials
Personal access tokens
```

----
## 📄 Exported Reports
The application can generate:

**Word Document**

Contains:

* Research topic
* Retrieved publications
* Publication metadata
* Abstracts
* AI literature analysis
* Scientific disclaimer

**PDF Document**

Contains:

Research topic
Retrieved publications
Publication information
Abstracts
AI literature analysis
Scientific disclaimer

-----
## ⚠️ Important Disclaimer
This application is intended for AI-assisted biomedical literature exploration and research support.

The generated AI analysis should not be considered a replacement for reading and critically evaluating the original scientific publications.

Users should consult the original research articles before making scientific, medical, or clinical decisions.

----
## 🎓Academic Purpose
AI-generated content may contain errors or incomplete interpretations.


Always verify important information against the original scientific publications.

------
## ⚠️ Scientific Responsibility
This project demonstrates the integration of:

* Biomedical literature retrieval
* Natural language processing
* Generative AI
* API-based scientific data retrieval
* Evidence synthesis
* Web application development
* Automated report generation

The project combines biomedical research resources with AI to support literature exploration and research discovery.

-----
## Author
Sreekutty Santhosh
