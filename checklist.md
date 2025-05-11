# Sitemap Crawler Web App Checklist

## 1. Environment & Dependencies
- [x] Set up Python virtual environment
- [x] Identify and list required libraries: streamlit, requests, beautifulsoup4, lxml, python-docx, fpdf, langchain, crawl4ai (if available)
- [x] Install required libraries
- [ ] Document all dependencies in `requirements.txt`
- [ ] Use pip for all Python package management

## 2. UI/UX Design
- [x] Design a simple, RTL-friendly Streamlit page
- [x] Centered input for sitemap URL with submit button
- [x] Display results under the input after crawling (scrollable, small height)
- [ ] Add a secondary input for user questions (RAG/QA) between the sitemap input and the results
- [ ] Add a submit button for the question input to allow users to ask questions
- [ ] Show crawl status for each URL (success/error, checkmark or error icon)
- [ ] Ensure Bootstrap or custom CSS for RTL and responsive design
- [ ] Document styling approach
- [x] Add sidebar archive for previously crawled sitemaps

## 3. Sitemap Crawling & Parsing
- [x] Fetch and parse the sitemap XML from user input URL
- [x] Extract URLs, lastmod, priority, etc.
- [x] Crawl the listed pages (with crawl4ai), track status for each (success/error)
- [x] Store crawled content for further processing
- [x] Handle errors and invalid URLs gracefully

## 4. Content Analysis & Knowledge Base
- [x] Limit the total crawled content sent to the LLM to avoid context length errors (truncate to 40,000 characters or less)
- [ ] Automatically generate and display a detailed explanation after crawling, including:
    - Website description (what the website is)
    - Products
    - Services
    - Expertise
    - Additional details
    - Keywords for products, services, and potential customers
    - Suggested email for potential customers
- [ ] Store results as a knowledge base (in-memory or persistent)
- [ ] Document analysis and extraction logic

## 5. RAG/QA System
- [ ] Implement a Retrieval-Augmented Generation (RAG) system using the knowledge base
- [ ] Allow user to ask questions about the company (input between sitemap and results, with submit button)
- [ ] Return answers based on the crawled knowledge base
- [ ] Support Persian language and RTL display

## 6. Export Features
- [ ] Generate and provide download links for:
    - Word document (docx) of the response
    - PDF of the response
- [ ] Ensure correct formatting and RTL support in exports

## 7. Testing
- [ ] Unit tests for sitemap parsing, crawling, and content extraction
- [ ] Integration tests for end-to-end workflow
- [ ] Test with Persian and English sitemaps
- [ ] Test export features (Word, PDF)
- [ ] Document test procedures

## 8. Security & Error Handling
- [ ] Use environment variables for sensitive configs
- [ ] Validate and sanitize all user inputs
- [ ] Implement proper error handling and logging
- [ ] Document error patterns and recovery procedures

## 9. Documentation
- [ ] Update `README.md` with setup, usage, and features
- [ ] Document major decisions and architecture
- [ ] Maintain API and code documentation
- [ ] Update docs as changes occur

## 10. Final Review
- [ ] Review code for simplicity, maintainability, and security
- [ ] Ensure all project rules are followed
- [ ] Finalize and document deployment steps 