# 🧠 Knowledge Graph Generator

This is a Flask-based web application that allows users to generate interactive knowledge graphs from:

- Raw text input  
- Uploaded `.txt` files  
- URLs (webpages)

It uses **LLM (OpenRouter + Qwen2.5)** to extract **entities and relations**, and renders them as interactive visualizations using **PyVis** and **NetworkX**.

---

## 🚀 Features

- 🔍 Extracts **entities and relations** from text using an LLM (Qwen2.5 via OpenRouter)
- 🌐 Supports input via:
  - Direct text input
  - URLs (scrapes and extracts content)
  - `.txt` file uploads
- 🌈 Generates **interactive knowledge graphs**
- 📊 View entity and relation counts
- 📁 Browse, view, and download past graphs in **JSON** or **CSV**
- 🧼 Automatically cleans and limits input text for efficiency
- 🎨 Custom graph styling with physics-based layout

---

## 🖥️ Demo

![text1](https://github.com/user-attachments/assets/53c6e05e-a425-4d55-b847-e0aa28bbf71e)

![text](https://github.com/user-attachments/assets/90334e17-cb62-4fb6-8a3c-ebfad85e5b2e)


---

## 📦 Installation

```bash
git clone https://github.com/Jaikumar96/knowledge-graph-generator.git
cd knowledge-graph-generator
pip install -r requirements.txt
```

## 🔑 OpenRouter API Key
Go to https://openrouter.ai

### Sign in and get your API key

Replace the placeholder key in app.py:
```bash
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="your-api-key-here"
)
```
## 🏃 Running the App
```bash
python app.py
```
Then open http://localhost:5000 in your browser.

## 📁 Project Structure
```bash
.
├── app.py                  # Main Flask app
├── templates/              # HTML templates
├── static/
│   └── graphs/             # Saved graph HTML and JSON files
├── uploads/                # Uploaded text files
└── requirements.txt        # Python dependencies
```
## 📤 Input Types
Text: Direct text input field

URL: Extracts content from the webpage using BeautifulSoup

File: Upload .txt files (UTF-8 encoded)

## 📈 Output Formats
```bash
.html: Interactive graph (rendered in browser)

.json: Raw data (entities and relations)

.csv: Tabular format (for entities and relations)
```

## 📄 Example Output
```bash
{
  "entities": ["Python", "Flask", "PyVis"],
  "relations": [
    ["Python", "uses", "Flask"],
    ["Flask", "visualizes", "PyVis"]
  ]
}
```
## 🛠️ Technologies Used
Flask – Web framework

NetworkX & PyVis – Graph generation and visualization

OpenRouter (Qwen2.5) – LLM for extracting relationships

BeautifulSoup – Web scraping for URL input

Matplotlib & Pandas – Optional (for advanced export)

## 📌 To Do / Improvements
 Add PNG/SVG export support

 Limit API calls for free usage tiers

 Support multilingual inputs

 Add dark mode and responsive design

## 📃 License
This project is open-source and available under the MIT License.
