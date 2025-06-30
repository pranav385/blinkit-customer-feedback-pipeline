# 🛒 Blinkit Customer Complaint Analysis (LinkedIn + Twitter + LLMs)

> **End-to-end data pipeline** to scrape, extract, clean, and analyze Blinkit customer complaints using LinkedIn, Twitter, and LLaMA 3 via Ollama. Includes automated social media login, complaint detection, LLM-based field extraction, and actionable data visualizations.

---

## 📌 Overview

This project investigates real-world customer grievances related to **Blinkit**, a quick-commerce delivery platform, by:

- Scraping posts from **LinkedIn** and **Twitter** using **Selenium** and **BeautifulSoup**
- Extracting key complaint details using **LLaMA 3 via Ollama**
- Standardizing noisy, user-generated data into clean, structured form
- Performing **data visualization** to uncover insights about issues, urgency, and sentiment

---

## 🧭 Project Workflow

```
[Selenium Scraper]
        ↓
[LinkedIn Posts] + [Tweets]
        ↓
[Preprocessing + Filtering Complaints]
        ↓
[LLM Extraction → Issue / Product / Resolution]
        ↓
[LLM Standardization → Generic Clean Fields]
        ↓
[Data Visualization + Insight]
```

---

## 🗂️ Notebooks Overview

| Notebook | Description |
|----------|-------------|
| **1. `Linkedin Blinkit.ipynb`** | Logs into LinkedIn and searches for complaint posts. Scrapes name, date, text, and engagement stats. |
| **2. `Twitter Blinkit.ipynb`** | Automates login and searches for complaint tweets. Extracts post metadata, engagement, and content. |
| **3. `Blinkit with llama.ipynb`** | Merges and cleans all data. Uses **LLaMA 3 (via Ollama)** to extract: `Issue`, `Product`, `Resolution Requested`. Then, prompts LLaMA 3 again for consistent standardization. |
| **4. `Final.ipynb`** | Generates **11+ visualizations** to reveal patterns in complaints, sentiment, urgency, and resolutions across time. |

---

## 🛠 Tech Stack

- **Python**: Data processing & analysis  
- **Selenium + BeautifulSoup**: Automated social media scraping (LinkedIn & Twitter)  
- **LLMs via Ollama (LLaMA 3)**: Extract + standardize complaint fields  
- **Pandas, Matplotlib, Seaborn**: Data wrangling and visualization  
- **Jupyter Notebooks**: Exploratory development  

---

## 📊 Key Visualizations

> Found in `Final.ipynb`

- ✅ **Top 10 Reported Issues**  
- ✅ **Top 10 Resolution Requests**  
- ✅ **Complaints Over Time**  
- ✅ **Issue vs Resolution Heatmap**  
- ✅ **Sentiment & Urgency Distribution**  
- ✅ **Issue vs Sentiment Heatmap**  
- ✅ **Issue vs Urgency Heatmap**  
- ✅ **Resolution Trends Over Time**  
- ✅ **Top Issues Over Time**  
- ✅ **Engagement vs Sentiment**  
- ✅ **Negative Sentiment Complaints**  

---

## 💡 Example Insights

| Observation | Insight |
|-------------|---------|
| 🚨 Most common complaints | Scam, delayed orders, refund issues |
| 😠 Sentiment skew | Majority of complaints carry **negative tone** |
| ⏳ Urgency levels | High urgency linked to refund-related issues |
| 📅 Time trends | Complaint surges on specific days may link to app/server issues |
| 🎯 Resolution ask | Refunds, customer care contact, and replacements are top demands |

---

## 🧠 LLM Use Cases

### 1. **Extraction**
Took noisy user-generated posts and converted them into structured JSON fields:
```json
{
  "Issue": ["spoiled item", "no refund"],
  "Product": ["fruits", "groceries"],
  "Resolution_Requested": ["refund", "replacement"]
}
```

### 2. **Standardization**
Unified different phrasings (e.g., "money not received", "didn't get refund") into clean, analyzable categories like `"refund"`.

---

## 📁 Sample Extracted Data

| Post Text | Issue | Product | Resolution Requested |
|-----------|-------|---------|----------------------|
| "Blinkit delivered rotten fruits again!" | spoiled item | fruits | refund |
| "Still no refund for a failed order. It’s been a week!" | no refund | groceries | refund |

---

## 🧪 How to Run

1. **Start Ollama with LLaMA 3:**
```bash
ollama run llama3
```

2. **Run notebooks in order:**
   - `Linkedin Blinkit.ipynb`
   - `Twitter Blinkit.ipynb`
   - `Blinkit with LLM.ipynb`
   - `Final.ipynb`

⚠️ **Note:** This project scrapes private platforms. Use responsibly and only for learning/demo purposes.

---

## 🚀 Possible Extensions

- Classify complaint types using ML models  
- Track complaint-to-resolution time lag  
- Deploy interactive dashboard using **Streamlit**  
- Apply **NER** to extract brands/products directly  

---

## 🤖 LLM Model Flexibility

This pipeline uses **LLaMA 3 via Ollama** for cost-effective and local LLM inference. However, output quality can improve significantly by:

- Switching to **more advanced models** (e.g., GPT-4, Claude 3)
- Fine-tuning on Blinkit-specific complaint data

The pipeline is modular — so model swapping is simple and encourages experimentation.

---

## 👨‍💻 Author

**Pranav Kumar**  
Data Analyst  
📧 pranavkumarpk385@gmail.com  
🌐 [LinkedIn](https://www.linkedin.com/in/pranavkumarpk/)

---

## 📃 License

This project is for educational and demonstration purposes only. **Commercial use of scraped data is not advised.**
