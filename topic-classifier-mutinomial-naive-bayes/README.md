# 20 Newsgroups Topic Classification with Naive Bayes

This project builds a **text classification model** that predicts the topic of online forum posts using the **20 Newsgroups dataset**.  
The goal is to implement a complete **Natural Language Processing (NLP) pipeline**, including data exploration, text preprocessing, TF-IDF feature extraction, model training, and evaluation.

---

## Dataset

The project uses the **20 Newsgroups dataset**, a classic benchmark for text classification.

- **11,314 documents**
- **20 topic categories**
- Posts collected from historical **Usenet discussion groups**

The dataset is relatively balanced across the different classes.

---

## Project Workflow

The notebook follows a typical NLP machine learning workflow:

1. **Data Loading**
   - Dataset loaded with `fetch_20newsgroups`
   - Headers, footers and quoted replies removed

2. **Exploratory Data Analysis**
   - Class distribution visualization
   - Document length analysis
   - Word count distribution
   - Average document length per category

3. **Text Preprocessing**
   - Lowercasing
   - Removal of emails
   - Removal of punctuation and numbers
   - Removal of extra whitespace

4. **Feature Extraction**
   - TF-IDF vectorization
   - Stopword removal
   - Unigrams and bigrams (`ngram_range=(1,2)`)
   - Rare and overly common words filtered (`min_df`, `max_df`)

5. **Model Training**
   - Multinomial Naive Bayes classifier

6. **Evaluation**
   - Accuracy
   - Classification report (precision, recall, F1-score)
   - Confusion matrix

7. **Model Improvement**
   - Hyperparameter tuning using `GridSearchCV`
   - Optimization of the smoothing parameter `alpha`
   - Additional filtering of rare words

8. **Model Interpretation**
   - Extraction of the most informative words for each category based on the learned probabilities \(P(word|class)\)

---

## Model

The classifier used is: Multinomial Naive Bayes

---

## Results

Initial model performance: accuracy 0.75%

After tuning the smoothing parameter (`alpha`) and filtering rare words: accuracy 0.77%

The improvement also increases **recall and F1-score**, particularly for categories that are semantically similar (for example religion or politics topics).

---

## Example of Informative Words

The model learns which words are most indicative for each class.  
Examples:

| Category | Example Words |
|--------|--------|
| `sci.space` | space, nasa, orbit, shuttle, launch |
| `rec.sport.hockey` | hockey, team, nhl, game |
| `talk.politics.guns` | gun, guns, firearms, weapons |
| `soc.religion.christian` | jesus, church, christ, bible |

These words correspond to those with the highest learned probability \(P(word|class)\).

