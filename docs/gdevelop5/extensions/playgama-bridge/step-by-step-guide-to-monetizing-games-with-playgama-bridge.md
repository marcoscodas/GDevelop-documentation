
# 🔍 Webscraper Overview

## Summary

This tool is a web scraper that extracts metadata, download links, and PDF content from a specified site. The code includes functionality for site crawling, HTML parsing, downloading files, and extracting PDF text.

---

## 📂 File Breakdown

### `main.py`

Main script that starts the scraping process.

- Initializes URLs and config.
- Calls crawler and parsing functions.

### `crawler.py`

Handles URL discovery and filtering.

- Crawls target site starting from base URL.
- Collects URLs that match allowed patterns.
- Filters out unwanted links.

### `downloader.py`

Responsible for saving HTML pages and files (like PDFs).

- Downloads files found in `crawler.py`.
- Supports PDF and HTML saving with directory structure.

### `pdf_extractor.py`

Extracts text from downloaded PDF files.

- Converts PDF files into text using PyMuPDF (`fitz`).
- Saves text to `.txt` files.

### `parser.py`

Parses saved HTML files to extract metadata and useful content.

- Extracts:
  - Titles
  - Meta descriptions
  - Custom tags (based on config)
- Stores data in JSONL format.

---

## 🧰 Tools & Libraries

- `requests`, `BeautifulSoup`: HTML crawling & parsing
- `fitz` (PyMuPDF): PDF parsing
- `os`, `pathlib`: File handling
- `re`: URL filtering
- `jsonlines`: Output format for structured data

---

## 🖼️ Visual Overview

### Architecture Diagram

![Webscraper Architecture](https://raw.githubusercontent.com/yourusername/yourrepo/main/assets/architecture.png)

### Example Output

![JSONL Output Example](https://raw.githubusercontent.com/yourusername/yourrepo/main/assets/output-sample.png)

---

## 🚀 Usage

1. Set the base URL in `main.py`.
2. Run:

```bash
python main.py
```

3. Output:
   - Downloaded HTML/PDF files
   - Extracted PDF text files
   - JSONL file with metadata

---

## 📝 Notes

- Avoids blacklisted patterns via regex.
- Designed to scale to multiple domains.
- Modular code: swap out components easily (e.g. PDF parser).
