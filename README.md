# 🏛️ Legal Document Classification and Summarization

This project focuses on automating the **classification** and **summarization** of legal documents. The system supports three primary document categories:

- 🧾 Contract
- 🏡 Land
- ⚖️ Judgment

## 🔍 Project Overview

Legal documents are often long and complex. This project aims to:
1. **Classify** legal texts into predefined categories using **Legal BERT**.
2. **Summarize** the content using **BART**, providing a concise overview for quick understanding.

---

## 📂 Dataset

- **Types**: Judgment, Contract, Land
- **Format**: Plain text documents (.txt or .csv)
- **Length**: Varies between 5–15 pages

---

## 🧠 Models Used

### 1. Legal BERT (Classification)
- Fine-tuned on the labeled legal dataset
- Input: Full document text
- Output: Predicted label (Judgment, Contract, Land)

### 2. BART (Summarization)
- Pretrained BART model (optionally fine-tuned on legal texts)
- Input: Full document text or paragraphs
- Output: Abstractive summary (~3-5 sentences)

---

## 🔧 Pipeline

```text
            ┌─────────────────────┐
            │  Raw Legal Document │
            └────────┬────────────┘
                     ↓
            ┌─────────────────────┐
            │  Preprocessing      │
            │ - Clean text        │
            │ - Remove headers    │
            └────────┬────────────┘
                     ↓
      ┌──────────────┴──────────────┐
      ↓                             ↓
┌──────────────┐            ┌────────────────┐
│ Classification│           │ Summarization  │
│  (Legal BERT) │           │    (BART)      │
└──────┬────────┘            └──────┬─────────┘
       ↓                            ↓
  Predicted Label            Summary Output

