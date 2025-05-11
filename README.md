# RTL Sitemap Crawler with crawl4ai

A simple, RTL-friendly web app for crawling website sitemaps, extracting and summarizing content, and building a knowledge base for question answering (RAG). Built with Python and Streamlit.

## Features
- Enter a sitemap URL and crawl all listed pages using [crawl4ai](https://github.com/unclecode/crawl4ai)
- Persian (Farsi) and RTL UI support
- Summarizes website, products, services, expertise, and more
- Extracts keywords for products, services, and potential customers
- Suggests an email template for potential customers
- Knowledge base for Retrieval-Augmented Generation (RAG) Q&A
- Export results as Word and PDF
- Clean, simple, and responsive UI

## Requirements
- Python 3.8+
- [Firefox browser](https://www.mozilla.org/firefox/) (for crawl4ai, or configure for Chromium)
- Internet connection (for crawling and fetching sitemaps)

## Installation
1. **Clone the repository** (if using version control):
   ```sh
   git clone <your-repo-url>
   cd <project-folder>
   ```
2. **Create and activate a virtual environment:**
   ```sh
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # macOS/Linux:
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```sh
   pip install streamlit requests beautifulsoup4 lxml python-docx fpdf langchain crawl4ai nest_asyncio
   ```
   - If you see errors for `crawl4ai`, check its [installation guide](https://github.com/unclecode/crawl4ai#installation).
   - Make sure Firefox or Chromium is installed for browser-based crawling.

## Usage
1. **Run the app:**
   ```sh
   streamlit run app.py
   ```
2. **In your browser:**
   - Enter a sitemap URL (e.g., `https://www.xml-sitemaps.com/download/novincarbon.com-8e74355b2/sitemap.xml?view=1`)
   - Click "بررسی سایت‌مپ" to parse the sitemap
   - Click "شروع خزیدن" to crawl all pages
   - Wait for crawling to finish; a summary and knowledge base will be generated
   - Ask questions about the company or export the results as Word/PDF

## Project Structure
```
project/
├── app.py           # Main Streamlit app
├── checklist.md     # Development checklist
├── README.md        # This file
├── requirements.txt # Python dependencies
└── ...
```

## Troubleshooting
- **Import errors:**
  - Ensure your virtual environment is activated
  - Install all dependencies as above
  - Select the correct Python interpreter in VSCode if using it
- **Browser errors:**
  - Make sure Firefox or Chromium is installed and accessible
- **Async errors:**
  - `nest_asyncio` is used to allow async crawling in Streamlit
- **crawl4ai errors:**
  - Check [crawl4ai documentation](https://github.com/unclecode/crawl4ai) for advanced setup

## Notes
- The app is designed for RTL/Persian websites but works for any sitemap
- All crawling is performed client-side; ensure your machine/network allows browser automation
- For large sitemaps, crawling may take several minutes
- The knowledge base and RAG/QA features are extensible for further NLP/AI integration

## License
MIT (or your chosen license) 