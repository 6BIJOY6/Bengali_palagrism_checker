# 📝 Bangla Plagiarism Checker  
*A professional plagiarism detection system for Bengali text*  

![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat&logo=fastapi)  
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)  
![Frontend](https://img.shields.io/badge/Frontend-HTML%2FCSS%2FJS-orange)  
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Overview  

The **Bangla Plagiarism Checker** is a full-stack application that detects plagiarism in **Bengali text** by combining both **lexical similarity** (TF-IDF) and **semantic similarity** (SBERT embeddings).  
It provides a **modern, responsive web interface** where users can paste text or upload documents (PDF, DOCX, TXT) and instantly receive similarity scores, confidence levels, and processed results.  

---

## ✨ Key Features  

- 🔍 **Hybrid Detection**: Combines **TF-IDF** and **SBERT** for robust similarity analysis  
- 🌐 **Full-stack App**: FastAPI backend + responsive HTML/CSS/JS frontend  
- 📑 **File Upload**: Support for PDF, DOCX, and TXT (with simulated extraction in demo)  
- 🎨 **Interactive UI**: Dark mode, progress bars, notifications, and mobile-friendly layout  
- 📊 **Detailed Results**: Overall score, TF-IDF score, SBERT score, processed text, confidence band  
- 🔒 **CORS-enabled API** for easy third-party integration  

---

## 🏗️ Architecture  

```mermaid
flowchart TD
    User[User] -->|Text / File Upload| UI[Frontend (HTML/CSS/JS)]
    UI -->|POST /api/check| API[FastAPI Backend]
    API --> Preprocess[Text Preprocessing (Regex, Tokenization, Stopwords)]
    Preprocess --> Models[TF-IDF Vectorizer & SBERT Encoder]
    Models --> Compare[Cosine Similarity vs Corpus]
    Compare --> Result[Similarity Score + Confidence]
    Result --> UI

Project Structure
.
├── main.py                  # FastAPI backend
├── templates/
│   └── index.html            # Frontend UI
├── static/                   # (optional assets, CSS/JS/images)
├── bangla_stopwords.xlsx     # Stopword list
├── tfidf_vectorizer.pkl      # Pretrained TF-IDF vectorizer
├── tfidf_matrix.npy          # Corpus TF-IDF matrix
├── sbert_embeddings.npy      # Corpus SBERT embeddings
├── requirements.txt
└── README.md
