# Machine Learning & Deep Learning Portfolio

A collection of small, self-contained Machine Learning and Deep Learning projects, designed to run on a personal laptop and based on public datasets.


---

## Projects

### Encoreds, Decoders, Transformers 🤖​
- **Seq2Seq Translation** — Encoder/decoder LSTM architecture with Attention, Gradient clipping, Beam search and Bleu score
- **Emotion Classifier** — Fine-tuning of pre-trained DistilBERT base uncased, Error Analysis and Visualization of Attention
- **GPT-2 Inference Lab** — BPE Tokenization, Next-token prediction, Decoding strategies (Greedy, Temperature, Top-K and Top-P)
- **Text Summarization** — Compare ROUGE-1/2/L scores between T5 vs GPT-2 (zero-shot and few-shot) vs Baseline Models
- **Tokenization & Embedding** — WordPiece, BPE and SentencePiece; Static (GloVe) vs Contextual (BERT tokenizer) Embeddings
- **Prompt Engineering** — Prompting strategies (Zero-shot, Few-shot and Chain-of-Thought) on FLAN-T5 with different tasks
- **Fine-tuning Project** — Fine tuning of distilGPT2 for sentiment analysis task, using LoRA

### Machine Learning ⚙️
- **House Prices** — Linear & Multiple Regression, Regularization (Ridge, Lasso, Elastic Net)
-  **SMS Spam Detection** — NLP pipeline with BoW, TF-IDF, Word2Vec and multiple ML models
-  **IMDB Sentiment Classification** — Word2Vec (Domain vs Pre-trained) with Classical ML
-  **Energy Efficiency Dataset** — Polynomial Regression, overfitting and Ridge regularization
-  **Telco Customer Churn** — Random Forest with Pipeline, ROC-AUC optimization and Recall-focused tuning
-  **Ames Housing Prices** — Gradient Boosting techniques: XGBoost, LightGBM, CatBoost
-  **Energy Efficiency Dataset** — Support Vector Regression with Linear, Polynomial and RBF kernels
-  **Breast Cancer Dataset** — Logistic Regression, Regularization (L1, L2)
-  **Hearth Disease Dataset** — K-NN with Cross Validation and Elbow Method, comparison with Random Forest, Decision Tree and Logistic Regression
-  **Wine Classification** — LDA for classification and dimensionality reduction, comparison with PCA and QDA, cross-validation evaluation
-  **Moons/Circles Datasets** — Linear vs RBF SVM on synthetic datasets, hyperparameter tuning ($\gamma$ and $C$)
-  **Credit Card Fraud Detection Dataset** — K-Means for Clustering using Elbow method, comparison with Isolation Forest and Local Outlier Factor
-  **Spotify Tracks Dataset** — Hierarchical Clustering for Music Personalities & Recommender System
-  **Custom and Artificial Datasets** — Probabilistic (Gaussian Mixture Models) vs Density-based (DBSCAN) Clustering, Silhouette Score
-  **Zachary Karate Club** — Community Detection on a Network using Spectral Clustering


### Neural Networks 🌐
- **Titanic** — Fully Connected Neural Network for survival prediction
- **Fake News Classification** — NLP preprocessing, One-Hot encoding, LSTM, Dropout regularization
- **Amazon Reviews Sentiment Analysis** —LSTM with trainable vs GloVe embeddings (frozen & fine-tuned)
- **Named Entity Recognition (CoNLL-2003)** — BiLSTM for sequence labeling with padding, stacked LSTMs, dropout regularization and pre-trained GloVe embeddings
- **IMDB Sentiment Classification** — GRU vs LSTM for sentiment analysis, sequence padding, packed sequences and early stopping


### Computer Vision & CNN 🖼️
- **Cats vs Dogs** — CNN on Oxford-IIIT Pet Dataset  
- **Faces (CelebA)** — Gender classification & multi-label classification with MobileNetV2  
- **Flowers** — CNN with data augmentation to reduce overfitting  
- **Object Detection** — YOLOv8 on images and videos
- **Image Segmentation** — Semantic, instance & panoptic segmentation (SegFormer, Mask R-CNN, Mask2Former)

---

## Tech Stack 🛠️
Python · NumPy · Pandas · Scikit-learn · TensorFlow/Keras · PyTorch · HuggingFace · YOLO · Gensim · NLTK · Networkx
