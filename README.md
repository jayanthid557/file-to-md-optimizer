# 🚀 Heavy File-to-Markdown AI Optimizer

A high-efficiency Python pipeline designed to convert heavy, bloated documents (PDFs, DOCX, Images) into lightweight, structured **Markdown (.md) files**. This tool eliminates data garbage, preserves layout structure, and dramatically reduces AI API token consumption to save you credits.

---

## 🛠️ System Architecture (4-Step Pipeline)

### 1. File Input
* Accepts heavy input formats: `.pdf`, `.docx`, `.pptx`, `.png`, `.jpg`.

### 2. Security & Defusal (`python-magic` + `zipfile`)
* **Magic Bytes Verification:** Validates the underlying file signatures to block disguised extensions.
* **Zip Bomb Protection:** Analyzes compression ratios of Office files (`.docx`/`.pptx`) dynamically to kill malicious structural files before extraction.

### 3. Chunk & Parse (`pymupdf` + `pdfplumber` + `pytesseract`)
* **RAM Protection:** Slices massive documents page-by-page or paragraph-by-paragraph.
* **Layout Awareness:** Extracts columns, text flows, and complex table grids seamlessly.
* **OCR Layer:** Processes scanned pages and image text using asynchronous background workers.

### 4. Markdown Assembly & Token Cleaning (`markdownify` + `re`)
* **Token Optimizer:** Automatically strips repetitive headers, footers, page numbers, and excess white spaces.
* **Buffered Output:** Caches structural chunks in a memory buffer before writing to disk, eliminating drive latency.

---

## 💻 Tech Stack & Libraries
* **File Routing & Validation:** `python-magic`, `zipfile`
* **Text & Layout Processing:** `pymupdf` (Fitz), `python-docx`, `python-pptx`
* **Table Extraction:** `pdfplumber`
* **Optical Character Recognition (OCR):** `pytesseract` / `EasyOCR`
* **Markdown Compilation:** `markdownify`, `re` (Regex)
