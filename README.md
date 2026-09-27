# Sentiment_Analysis
NLP-based sentiment analysis of Amazon reviews with emotion detection, rating analysis, and data visualizations using Python
# 📝 Sentiment Analysis of Amazon Reviews

## 📌 Project Overview

This project performs **Sentiment Analysis** on Amazon Fine Food Reviews using Natural Language Processing (NLP) techniques.

The main objective is to analyze customer reviews and classify them into:

* 🟢 Positive
* 🔴 Negative
* ⚪ Neutral

The project also uses a **lexicon-based approach** to identify specific emotions such as Joy, Anger, Sadness, Fear, and Surprise.

The analysis helps understand customer opinions, product satisfaction, and common patterns in Amazon reviews.

---

## 🎯 Objectives

The main objectives of this project are:

1. Analyze customer review text.
2. Clean and preprocess textual data.
3. Apply NLP techniques to determine sentiment.
4. Classify reviews as Positive, Negative, or Neutral.
5. Detect emotions using an emotion lexicon.
6. Analyze customer ratings.
7. Visualize sentiment and rating patterns.
8. Identify frequently used words.
9. Generate useful insights for marketing and product improvement.

---

## 📂 Dataset

### Amazon Fine Food Reviews

The project uses the **Amazon Fine Food Reviews** dataset.

The dataset contains customer reviews of food products purchased from Amazon.

### Dataset Size

* **Total reviews:** 568,454
* **Total columns:** 10

### Main Columns

| Column                   | Description                                  |
| ------------------------ | -------------------------------------------- |
| `Id`                     | Unique review ID                             |
| `ProductId`              | Product identifier                           |
| `UserId`                 | Customer identifier                          |
| `ProfileName`            | Customer profile name                        |
| `HelpfulnessNumerator`   | Number of users who found the review helpful |
| `HelpfulnessDenominator` | Total helpfulness votes                      |
| `Score`                  | Product rating from 1 to 5                   |
| `Time`                   | Review timestamp                             |
| `Summary`                | Short review summary                         |
| `Text`                   | Full customer review                         |

For sentiment analysis, the main columns used are:

* `Score`
* `Summary`
* `Text`

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **TextBlob**
* **WordCloud**
* **Regular Expressions (re)**

---

## 📁 Project Structure

```text
Sentiment_Analysis/
│
├── Reviews.csv
│
├── sentiment_analysis.py
│
├── requirements.txt
│
└── outputs/
    │
    ├── sentiment_results.csv
    ├── analysis_summary.csv
    ├── sentiment_distribution.png
    ├── sentiment_percentage.png
    ├── rating_distribution.png
    ├── rating_vs_sentiment.png
    ├── emotion_distribution.png
    └── wordcloud.png
```

---

## 🔄 Project Workflow

```text
Amazon Reviews
       ↓
Load Dataset
       ↓
Understand Dataset
       ↓
Handle Missing Values
       ↓
Remove Duplicate Reviews
       ↓
Text Cleaning
       ↓
Sentiment Analysis
       ↓
Positive / Negative / Neutral
       ↓
Emotion Detection
       ↓
Rating Analysis
       ↓
Data Visualization
       ↓
Business Insights
```

---

## 🧹 Data Preprocessing

The review text is cleaned before performing sentiment analysis.

The following preprocessing steps are performed:

1. Convert text to lowercase.
2. Remove URLs.
3. Remove HTML tags.
4. Remove numbers and special characters.
5. Remove extra spaces.
6. Remove duplicate reviews.
7. Remove rows with missing review text.

After preprocessing, the cleaned text is stored in:

```text
clean_text
```

---

## 💭 Sentiment Analysis

The project uses **TextBlob** to calculate sentiment polarity.

TextBlob produces a polarity score between:

```text
-1  → Very Negative
 0  → Neutral
+1  → Very Positive
```

The following classification is used:

```text
Polarity > 0.05
→ Positive

Polarity < -0.05
→ Negative

-0.05 to +0.05
→ Neutral
```

Each review receives a sentiment label:

```text
Positive
Negative
Neutral
```

---

## 😊 Emotion Detection

A simple **emotion lexicon** is used to identify specific emotions from the review text.

The project detects:

* 😊 Joy
* 😡 Anger
* 😢 Sadness
* 😨 Fear
* 😲 Surprise

If no emotion keywords are found, the review is classified as:

```text
No Specific Emotion
```

This is a **keyword-based lexicon approach**, rather than a trained machine learning emotion classifier.

---

## 📊 Data Visualization

The project generates several visualizations.

### 1. Sentiment Distribution

Shows the number of:

* Positive reviews
* Negative reviews
* Neutral reviews

### 2. Sentiment Percentage

Shows the percentage distribution of each sentiment category.

### 3. Rating Distribution

Shows the number of reviews for ratings from:

```text
1 ⭐ to 5 ⭐
```

### 4. Rating vs Sentiment

Compares customer ratings with sentiment classifications.

### 5. Emotion Distribution

Shows the frequency of detected emotions.

### 6. Word Cloud

Displays frequently occurring words from customer reviews.

---

## 📈 Output Files

After running the program, the following files are generated inside the `outputs` folder:

| File                         | Purpose                              |
| ---------------------------- | ------------------------------------ |
| `sentiment_results.csv`      | Complete processed sentiment results |
| `analysis_summary.csv`       | Summary of major results             |
| `sentiment_distribution.png` | Sentiment count visualization        |
| `sentiment_percentage.png`   | Sentiment percentage chart           |
| `rating_distribution.png`    | Rating distribution chart            |
| `rating_vs_sentiment.png`    | Rating and sentiment comparison      |
| `emotion_distribution.png`   | Emotion frequency chart              |
| `wordcloud.png`              | Frequently used words                |

---

## 💻 Installation

### Step 1: Install Python

Make sure Python is installed on your system.

Check using:

```bash
python --version
```

### Step 2: Install required libraries

```bash
pip install pandas numpy matplotlib seaborn textblob wordcloud
```

### Step 3: Download TextBlob resources

```bash
python -m textblob.download_corpora
```

---

## ▶️ How to Run

Place `Reviews.csv` in the project folder.

Then run:

```bash
python sentiment_analysis.py
```

The program will:

1. Load the dataset.
2. Display dataset information.
3. Clean the review text.
4. Calculate sentiment polarity.
5. Classify sentiments.
6. Detect emotions.
7. Generate visualizations.
8. Save processed results.

---

## 🔍 Example Output

A processed review may look like:

| Score | Review                       |       Polarity | Sentiment |
| ----: | ---------------------------- | -------------: | --------- |
|     5 | Great product and delicious! | Positive value | Positive  |
|     1 | Very bad product.            | Negative value | Negative  |
|     3 | The product is okay.         |         Near 0 | Neutral   |

---

## 💡 Business Insights

Sentiment analysis can help businesses understand customer opinions.

### Marketing

Positive reviews can be used to identify products that customers appreciate.

### Product Development

Negative reviews can reveal:

* Product quality problems
* Packaging issues
* Taste complaints
* Customer dissatisfaction

### Customer Experience

Companies can identify common complaints and improve their products and services.

### Product Strategy

Frequently mentioned positive and negative words can help businesses understand customer preferences.

---

## ⚠️ Limitations

This project has some limitations:

1. TextBlob may not correctly understand sarcasm.
2. Some reviews may contain mixed positive and negative opinions.
3. Keyword-based emotion detection may miss emotions expressed using different words.
4. Sentiment accuracy depends on the quality of the text.
5. The emotion detection system is a simple lexicon-based approach.
6. The project does not use a trained deep learning sentiment model.

---

## 🚀 Future Improvements

The project can be improved by:

* Using machine learning models such as Logistic Regression or SVM.
* Using TF-IDF features.
* Using transformer models such as BERT.
* Improving emotion detection with a larger emotion lexicon.
* Performing aspect-based sentiment analysis.
* Building an interactive dashboard using Power BI or Streamlit.
* Analyzing sentiment trends over time.
* Identifying sentiment for individual products.

---

## 🏁 Conclusion

This project demonstrates how **Natural Language Processing** can be used to analyze customer reviews.

By classifying reviews into Positive, Negative, and Neutral sentiments and detecting specific emotions, businesses can better understand customer opinions and identify areas for product and service improvement.

The project provides a practical application of NLP for **customer feedback analysis, marketing insights, and product development**.

---

## 👩‍💻 Project

**Project:** Sentiment Analysis
**Dataset:** Amazon Fine Food Reviews
**Domain:** Natural Language Processing / Data Analytics
**Language:** Python
**Type:** NLP and Sentiment Analysis
