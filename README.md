# Sentiment-Analyzer-Logistic-Regression-and-TF-IDF
### Sentiment Analysis Model

This project focuses on analyzing sentiments from textual data using Logistic Regression. The model has been designed to classify text into positive or negative sentiments based on the underlying patterns in the data. Below is a detailed explanation of the steps involved, model architecture, and instructions on how to use the deployed model.

![Sentiment Analysis Cover](path_to_image) <!-- Add an illustrative image related to sentiment analysis -->

## 1. Data Preprocessing

Data preprocessing is a critical step to ensure the model receives clean, relevant, and properly formatted data. Below are the steps followed:

- **Tokenization**: The text is split into individual words or tokens.
- **Lowercasing**: All text is converted to lowercase to ensure consistency and prevent duplication of words like "The" and "the".
- **Removing Special Characters**: Non-alphanumeric characters, punctuation, and symbols are removed to clean the text.
- **Stopword Removal**: Common words such as "the", "is", "and", which do not add significant meaning to the sentiment, are removed.
- **Lemmatization**: Words are converted to their base or root form, reducing inflectional forms (e.g., "running" becomes "run").

![Data Preprocessing Steps](path_to_image) <!-- Add an image or flowchart showing the preprocessing steps -->

## 2. Model Architecture and Parameters

The model architecture comprises a **TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer** followed by a **Logistic Regression classifier**. The TF-IDF vectorizer transforms text into numerical vectors that represent the importance of words in the document, while the logistic regression classifier performs the sentiment classification.

### Model Parameters:

- **TF-IDF Vectorizer**:
  - `max_features`: 5000
  - `ngram_range`: (1, 2) (Considers unigrams and bigrams)

- **Logistic Regression**:
  - `C` (Inverse of regularization strength): 1.0
  - `Solver`: 'lbfgs'
  - `Multi_class`: 'auto'

This architecture ensures a balance between computational efficiency and performance accuracy.

![Model Architecture](path_to_image) <!-- Add a schematic diagram of the model architecture -->

## 3. Training Process

The model was trained using the following hyperparameters:

- **Batch size**: 1
- **Number of epochs**: 10

Training was conducted on a sentiment-labeled dataset, allowing the model to learn and adjust weights based on the error calculated during each epoch.

## 4. Evaluation Results and Analysis

The model's performance was evaluated using key metrics such as **precision**, **recall**, and **F1-score**, ensuring balanced performance across classes (positive/negative sentiments).

- **Precision**: Measures the accuracy of the positive predictions.
- **Recall**: Measures how well the model identifies all positive instances.
- **F1-score**: Harmonic mean of precision and recall.

Further analysis is needed for misclassified instances to identify areas for improvement in future iterations.



## 5. Instructions for Using the Deployed Model

The sentiment analysis model is deployed as a **Streamlit web application**. Users can easily interact with the model through the following steps:

1. Enter text in the input box provided on the app.
2. Click on the **"Predict"** button.
3. The model will return a sentiment prediction (positive or negative) based on the entered text.

### Running the Application:

You can access the deployed model at [Streamlit App URL](#). Alternatively, if running locally:

```bash
# Clone the repository
git clone https://github.com/AkhilKumar/Sentiment-Analysis-Model.git

# Install dependencies
pip install -r requirements.txt

# Run the Streamlit app
streamlit run app.py
