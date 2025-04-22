# 🏥 Health Insurance Deductible Matcher

This project is a Python-based NLP pipeline that extracts deductible amounts from monthly health insurance statements and matches them with credit card transactions. It uses **spaCy** for Named Entity Recognition (NER), regex for monetary value extraction, and Pandas for data storage and financial summarization.

---

## 📌 Features

- ✅ Extracts deductible amounts and dates from insurance statement text.
- ✅ Matches deductibles with credit card transactions based on date and amount.
- ✅ Stores matched results in memory using Pandas DataFrames.
- ✅ Generates a monthly summary of deductible spending.

---

## 🧠 Technologies Used

- Python 3
- [spaCy](https://spacy.io/) (`en_core_web_sm` model)
- Regular Expressions
- Pandas
- Google Colab (for testing and development)

---

## 🔍 How It Works

### 1. Input Data
- **Insurance Statements**: Unstructured text with deductible information.
- **Credit Card Transactions**: List of transactions with dates, amounts, and descriptions.

### 2. Extraction
- **spaCy NER** is used to detect `DATE` entities.
- **Regex** identifies deductible amounts (e.g., `$250`).

### 3. Matching Logic
- Deductibles are matched to transactions using:
  - Amount similarity
  - Month of the date in the insurance statement and transaction

### 4. Output
- A table of matched deductibles and transactions.
- A monthly summary report showing total deductible payments per month.

---

## 📁 Example Output

### ✅ Extracted Deductibles
| Date       | Amount | Statement                                                   |
|------------|--------|-------------------------------------------------------------|
| March 5    | 250.0  | On March 5, your deductible of $250 was processed...         |
| March 18   | 100.0  | Your deductible of $100 was applied on March 18...           |
| April 2    | 300.0  | April 2: Deductible paid: $300 for dental procedure.         |

### 🔄 Matched Transactions
| Deductible Date | Amount | Matched Txn Date | Description                 |
|------------------|--------|------------------|-----------------------------|
| March 5          | 250.0  | 2024-03-05        | Hospital emergency service  |
| March 18         | 100.0  | 2024-03-18        | Physiotherapy               |
| April 2          | 300.0  | 2024-04-02        | Dental services             |

### 📅 Monthly Summary
| Month    | Total Deductibles |
|----------|-------------------|
| 2024-03  | 350.0             |
| 2024-04  | 300.0             |

---

## 🚀 Getting Started

### 🔧 Installation

```bash
pip install spacy pandas
python -m spacy download en_core_web_sm
