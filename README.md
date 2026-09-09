# Sentiment Analysis using Hugging Face and Streamlit

A simple and interactive web-based **Sentiment Analysis application** built using Python, Hugging Face Transformers, and Streamlit.

The application analyzes user-provided text and predicts whether the given sentence expresses a **Positive** or **Negative** sentiment. It also displays the confidence score of the prediction.

## Project Overview

This project demonstrates how **Natural Language Processing (NLP)** and **Transformer-based AI models** can be integrated into a simple web application.

The user enters a sentence through the Streamlit interface. The input text is processed by a pre-trained Hugging Face Transformer model, which analyzes the sentence and generates a sentiment prediction.

### The application provides:

* Sentiment label – Positive or Negative
* Confidence score of the prediction
* Interactive web-based interface
* Real-time prediction

## Key Features

* AI-powered sentiment analysis
* Interactive Streamlit web interface
* Pre-trained Hugging Face Transformer model
* Positive and Negative sentiment classification
* Confidence score display
* Fast model inference
* Empty input validation
* Model caching for better performance
* No model training required
* Simple NLP application suitable for beginners

## Technologies and Tools

| Technology / Tool         | Purpose                                 |
| ------------------------- | --------------------------------------- |
| Python                    | Core programming language               |
| Streamlit                 | Creates the interactive web application |
| Hugging Face Transformers | Provides the pre-trained NLP model      |
| DistilBERT                | Performs sentiment classification       |
| PyTorch                   | Backend for Transformer model           |
| VS Code                   | Development environment                 |
| Git                       | Version control                         |
| GitHub                    | Project hosting                         |

## AI Model

This project uses the following pre-trained Hugging Face model:

**Model:** `distilbert-base-uncased-finetuned-sst-2-english`

The model is a fine-tuned version of DistilBERT designed for English sentiment classification.

The model predicts two sentiment classes:

* `POSITIVE`
* `NEGATIVE`

Along with the predicted sentiment, the model provides a confidence score indicating how confident it is about the prediction.

## How the Application Works

The application follows a simple NLP workflow:

```text
User enters text
       |
       v
Streamlit Interface
       |
       v
Input Validation
       |
       v
Hugging Face Pipeline
       |
       v
DistilBERT Model
       |
       v
Sentiment Prediction
       |
       v
Positive / Negative
       |
       v
Confidence Score
       |
       v
Result displayed
```

## Workflow Explanation

### 1. User Input

The user enters a sentence into the text area provided by the Streamlit application.

### 2. Input Validation

The application checks whether the user has entered valid text.

If the input field is empty, a warning message is displayed.

### 3. Model Processing

The entered text is passed to the Hugging Face sentiment-analysis pipeline.

### 4. Sentiment Classification

The pre-trained DistilBERT model analyzes the input sentence and predicts whether the sentiment is Positive or Negative.

### 5. Confidence Score

The model generates a confidence score for the predicted sentiment.

### 6. Result Display

The prediction and confidence percentage are displayed on the Streamlit web interface.

## Important Functions Used

### `st.set_page_config()`

Configures the Streamlit application's page settings such as:

* Page title
* Page icon
* Layout

Example:

```python
st.set_page_config(
    page_title="Sentiment Analysis",
    page_icon="🤖"
)
```

### `st.title()`

Displays the main title of the application.

### `st.text_area()`

Provides a text box where users can enter sentences.

### `st.button()`

Creates a button that starts the sentiment analysis process.

### `st.cache_resource`

Caches the AI model so that it does not need to be loaded repeatedly.

This improves application performance.

### `pipeline()`

The Hugging Face `pipeline()` function provides a simple way to perform sentiment analysis using a pre-trained Transformer model.

Example:

```python
pipeline(
    "sentiment-analysis",
    model="distilbert-base-uncased-finetuned-sst-2-english"
)
```

### `st.success()` and `st.error()`

These functions display appropriate messages based on the prediction or application status.

## Project Structure

```text
sentiment-analysis/
│
├── app.py
├── huggingfaceapp.py
├── requirements.txt
├── .env
├── .gitignore
└── README.md
```

### Files

**`app.py`**

Contains the Streamlit user interface, input handling, prediction trigger, and result display.

**`huggingfaceapp.py`**

Contains the Hugging Face model integration and sentiment prediction function.

**`requirements.txt`**

Contains all Python libraries required to run the project.

**`.env`**

Stores environment variables and secret configuration when required.

**`.gitignore`**

Prevents unnecessary or sensitive files from being uploaded to GitHub.

**`README.md`**

Contains the documentation, installation steps, workflow, features, and project information.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/sentiment-analysis.git
```

### 2. Open the Project Folder

```bash
cd sentiment-analysis
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Virtual Environment

For Windows:

```bash
venv\Scripts\activate
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the Application

```bash
streamlit run app.py
```

The Streamlit application will open in the browser using the local URL shown in the terminal.

## Example

### Input

```text
I really enjoyed this movie!
```

### Output

```text
Sentiment: POSITIVE
Confidence: 99.XX%
```

### Another Example

**Input:**

```text
The service was extremely disappointing.
```

**Output:**

```text
Sentiment: NEGATIVE
Confidence: XX.XX%
```

## Application Workflow

```text
                 ┌─────────────────┐
                 │   User Input    │
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │    Streamlit    │
                 │    Interface    │
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │ Input Validation│
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │ Hugging Face    │
                 │    Pipeline     │
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │   DistilBERT    │
                 │      Model      │
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │    Sentiment    │
                 │   Prediction    │
                 └────────┬────────┘
                          │
                          v
                 ┌─────────────────┐
                 │ Positive /      │
                 │ Negative +      │
                 │ Confidence      │
                 └─────────────────┘
```

## Why DistilBERT?

DistilBERT is a smaller and faster version of BERT that provides strong language understanding while requiring fewer computational resources.

Using a pre-trained model allows the application to perform sentiment analysis without training a machine-learning model from scratch.

## Limitations

* The model predicts only Positive and Negative sentiment.
* Sarcasm may not always be correctly understood.
* Highly ambiguous sentences may produce incorrect predictions.
* Prediction performance depends on the wording and context of the input.
* The selected model is designed specifically for English sentiment classification.

## Future Improvements

The project can be enhanced with the following features:

* Add Neutral sentiment classification
* Support multiple languages
* Analyze multiple sentences
* Add sentiment history
* Display confidence using charts
* Add CSV file sentiment analysis
* Deploy the application online
* Add sentiment statistics
* Improve the user interface
* Add an API for external applications

## Learning Outcomes

Through this project, the following concepts are demonstrated:

* Natural Language Processing
* Transformer-based NLP models
* Hugging Face Transformers
* Pre-trained AI models
* Streamlit application development
* Model inference
* Confidence scores
* Python programming
* Git and GitHub
* AI application development

## Conclusion

This project demonstrates how a pre-trained Transformer model can be integrated with Streamlit to create a practical and interactive NLP application.

Instead of training a machine-learning model from scratch, the application uses a pre-trained DistilBERT model to perform sentiment classification.

The project provides practical experience in **Python, NLP, Hugging Face Transformers, Streamlit, AI model inference, and GitHub project management**.

Author

Madhumitha.U
