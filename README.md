# SMS Spam Detection

## Project Overview

This project aims to build a machine learning model capable of classifying SMS messages as either "ham" (legitimate) or "spam". The goal is to develop an effective and interpretable solution for identifying unwanted messages.

## Dataset

The dataset used in this project is `smsspamcollection.csv`, which contains a collection of SMS messages along with their respective labels (ham or spam).

## Project Structure

The project is implemented as a Jupyter Notebook (`sms-spam-detection.ipynb`) and follows a standard machine learning workflow:

1.  **Data Cleaning**: Initial inspection and cleaning of the raw dataset, including handling missing values, renaming columns, and removing duplicate entries.
2.  **Exploratory Data Analysis (EDA)**: Analyzing the dataset's characteristics, such as the distribution of ham and spam messages, and extracting new features like message length (characters, words, sentences) to gain insights into the data.
3.  **Text Preprocessing**: Transforming the raw text data into a suitable format for machine learning models. This involves:
    * Lowercasing
    * Tokenization
    * Removing special characters
    * Removing stop words and punctuation
    * Stemming
4.  **Model Building**: Training various machine learning classification models on the preprocessed text data.
5.  **Evaluation**: Assessing the performance of the trained models using metrics like accuracy and precision.
6.  **Model Improvement (Ensemble Methods)**: Exploring advanced techniques like Voting Classifier and Stacking Classifier to potentially enhance model performance.
7.  **Interpretability (LIME)**: Using LIME (Local Interpretable Model-agnostic Explanations) to understand why the model makes specific predictions for individual SMS messages.
8.  **Deployment**: Saving the trained model and vectorizer for future use in a production environment.

## Technologies Used

* **Python**: Programming language
* **Pandas**: Data manipulation and analysis
* **NumPy**: Numerical operations
* **NLTK**: Natural Language Toolkit for text preprocessing
* **Scikit-learn**: Machine learning models and utilities
* **Matplotlib & Seaborn**: Data visualization
* **WordCloud**: For generating word clouds
* **XGBoost**: Gradient Boosting library
* **LIME**: For model interpretability

## How to Run the Notebook

1.  **Clone the repository (if applicable)**:
    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```
    (If this is a standalone file, simply ensure `smsspamcollection.csv` is in the same directory as the notebook.)

2.  **Install necessary libraries**:
    ```bash
    pip install pandas numpy scikit-learn nltk matplotlib seaborn wordcloud xgboost lime
    ```

3.  **Download NLTK data**:
    Open a Python interpreter or a notebook cell and run:
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    nltk.download('PorterStemmer') # Note: This might already be included in 'nltk.download('stemmers')' or 'all'
    ```

4.  **Run the Jupyter Notebook**:
    ```bash
    jupyter notebook sms-spam-detection.ipynb
    ```
    Execute all cells in the notebook.

## Model Persistence

The trained TF-IDF vectorizer and the best-performing Multinomial Naive Bayes model are saved as `vectorizer.pkl` and `model.pkl` respectively, using Python's `pickle` module. These files can be loaded to make predictions on new SMS messages without retraining the model.

## LIME Interpretability

The notebook includes a section demonstrating the use of LIME to explain individual predictions. This helps in understanding which words in an SMS message contribute most to its classification as "ham" or "spam." This is particularly useful for debugging the model and gaining trust in its decisions.

---