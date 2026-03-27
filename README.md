# 💹 Financial News Sentiment Analysis

Fine-tuned DistilBERT model that classifies financial news into
Bearish 🐻, Bullish 🐂, or Neutral 😐 sentiment.


## 📊 Dataset
- **Source:** zeroshot/twitter-financial-news-sentiment
- **Size:** ~11,000 labelled financial news sentences
- **Labels:** Bearish (0) · Bullish (1) · Neutral (2)

## 🧠 Model Details
- **Base model:** distilbert-base-uncased (67M parameters)
- **Fine-tuned for:** 2 epochs
- **Training:** fp16 on Google Colab T4 GPU
- **Accuracy:** ~88% on validation set

## 🚀 How to run
1. Open `financial_sentiment.ipynb` in Google Colab
2. Go to **Runtime → Change runtime type → T4 GPU**
3. Run all cells from top to bottom (~10 min)

## 💻 Try the model directly
```python
from transformers import pipeline

classifier = pipeline(
    "text-classification",
    model="addyrall/financial-sentiment-distilbert"
)

result = classifier("Company profits hit record high this quarter.")
print(result)
# → Bullish 📈
```

## 🛠️ Tech Stack
- Python 3.12
- HuggingFace Transformers
- HuggingFace Datasets
- PyTorch
- Google Colab (free tier)
