# Multi-Language Invoice Extractor using Gemini Pro

## Overview
This project is an end-to-end solution for extracting structured data from invoices in multiple languages using Google’s **Gemini Pro LLM**. The application processes invoice images, extracts key details, and organizes the extracted data into a structured format. It is designed for **businesses, finance teams, and automation workflows** that require multilingual invoice processing.

## Features
- ✅ **Multi-language support**: Extracts invoice data regardless of language.
- 🔍 **OCR Integration**: Reads text from invoice images.
- 🤖 **Gemini Pro LLM**: Uses Google’s Gemini Pro for intelligent text extraction.
- 🚀 **FastAPI Backend**: Provides efficient API endpoints for processing.
- 🎨 **Streamlit UI**: Interactive interface for uploading and analyzing invoices.
- 📊 **Structured Output**: Extracted data is presented in a clean, usable format.

## Technologies Used
- 🐍 Python 3.10
- 🧠 Google Gemini Pro LLM
- 🖼️ OCR (Tesseract or equivalent API)
- ⚡ FastAPI (Backend API)
- 🎨 Streamlit (Frontend UI)
- 📊 Pandas (Data Processing)
- 🔥 Uvicorn (Server for FastAPI)

## Installation

### Prerequisites
- Install **Python 3.10** or later
- Install `pip` if not already available
- Create and activate a virtual environment:
  ```bash
  python -m venv venv
  source venv/bin/activate  # On macOS/Linux
  venv\Scripts\activate  # On Windows
## How to Use

1. **Start the backend API**:
   - Run the following command to launch the FastAPI server:
     ```bash
     uvicorn app:app --reload
     ```
   - Open your browser and go to `http://127.0.0.1:8000/docs` to explore the API using Swagger UI.

2. **Start the frontend UI**:
   - In a new terminal window, run:
     ```bash
     streamlit run app.py
     ```
   - This will open a Streamlit web interface where you can upload invoice images.

3. **Upload and extract**:
   - Use the UI to upload a JPEG or PNG image of an invoice.
   - Click the **Extract** button.
   - The extracted invoice data will be displayed in a structured JSON format.

4. **Optional API call**:
   - If you prefer to use the backend API directly, make a `POST` request to:
     ```
     http://127.0.0.1:8000/extract-invoice
     ```
   - Include your invoice image in the request body as form-data.

## Sample Output

---

### Extracted Output
```json
{
  "invoice_number": "GST112020",
  "invoice_date": "04-Mar-2020",
  "total_amount": "1,258.00",
  "items": [
    {
      "name": "Automatic Saw",
      "quantity": 1,
      "price": 586.00
    },
    {
      "name": "Stanley Hammer",
      "quantity": 1,
      "price": 568.00
    }
  ]
}
