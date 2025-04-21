# 🚀 Falcon 9 Booster Scraper: Project Summary

This project scrapes and analyzes data from the [Wikipedia Falcon 9 Booster List](https://en.wikipedia.org/wiki/List_of_Falcon_9_first-stage_boosters), focusing on booster blocks: **v1.0**, **1.1**, **Block 4**, and **Block 5**. The final results are exported as `.csv` and `.txt` files for summary reporting in a zip folder.

---

## 🧰 Scraper Tools Used

### 1. `BeautifulSoup`

BeautifulSoup was chosen for direct HTML scraping and precise table handling:

- It gave me full control over tag structure and filtering.
- Allowed me row-wise parsing of each `<table class="wikitable">`.
- Easily integrated with `requests` for page fetching.

> ⏱️ Time to implement: ~8 hours (including debugging and cleaning HTML structures)

### 2. `ScrapeGraphAI`

ScrapeGraphAI was used as an AI-assisted alternative for structured data extraction

> ⏱️ Time to implement: ~10–15 minutes (after model setup and prompt testing)

---

## 🧠 Prompt Design for ScrapeGraphAI

The following prompt was used to instruct the LLM:


"Extract data about Falcon 9 boosters that are of types: v1.0, v1.1, Block 4, and Block 5.
For each booster, extract the following fields:
Engine Number, Block Type, Flight Number, Flight Type (F9 or FH), Launch Date (YYYY-MM-DD), 
Mission, Launch Pad, Landing, Turnaround (days), and Status."
Return the result as a structured list of entries.

This prompt was plugged into the `SmartScraperGraph` configuration and yielded a clean, structured JSON result.

---

## ⚙️ Scraping Strategy

- **BeautifulSoup Prompting**:  
  Parsed multiple tables, filtered only rows related to selected block types, and normalized messy data like launch dates and landing info.

- **ScrapeGraphAI Prompting**:  
  Used the prompt above to extract the same set of fields and compare with manual results. Served as a useful validation mechanism.

---

## 🛠️ Python Development Tools

- `Python 3.12`
- `BeautifulSoup4` – for HTML parsing
- `requests` – for fetching the Wikipedia page
- `pandas` – to clean and export `.csv` and `.txt` files
- `ScrapeGraphAI` – for AI-assisted prompt scraping
- `VSCode` – development environment

---

## 🧪 Function Design & Challenges

### Development Plan

- Write modular functions to:
  - Filter boosters by block type
  - Extract and normalize key fields
  - Export `.txt` summaries and `.csv` reports
- Automate generation of assignment-based queries (e.g. `b4only`, `mostLaunches`)

### Key Challenges

- HTML inconsistencies in Wikipedia tables.
- Blocks have incomplete data
- Headers are nested which gives null value
- Handling landing info nested within links and footnotes.
- ScrapeGraphAI initially hallucinated some field names — required prompt refinement.
- Unicode issues during `.csv` writing (fixed via `utf-8` encoding).

---

## 📁 Output Files

- ✅ `Blocks_combined_all_final_latest.csv` – full scraped dataset
- ✅ `.txt` files (e.g., `f9only.txt`, `longestTurnaround.txt`, `mostLaunches.txt`)
- ✅ Python scripts for filtering, scraping, and generating reports

---

## 📎 References

- 🌐 [Wikipedia Falcon 9 Boosters](https://en.wikipedia.org/wiki/List_of_Falcon_9_first-stage_boosters)
- 🛠️ [BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- 🤖 [ScrapeGraphAI GitHub](https://github.com/IsaacScript/scrapegraphai)
- 📄 [GitHub Markdown Writing Guide](https://docs.github.com/en/get-started/writing-on-github)

