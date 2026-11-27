# Biomedical NLP: Abbreviation and Long-Form Detection

## Project Overview

This project explores Natural Language Processing techniques for identifying abbreviations and their corresponding long forms in biomedical and scientific text.

The work includes dataset exploration using the PLOD dataset and a Named Entity Recognition (NER) application built with a pre-trained RoBERTa token-classification model. A Flask API provides an endpoint for submitting text and receiving entity predictions.

## Project Objectives

- Explore and understand the structure of the biomedical abbreviation dataset.
- Examine labelled text sequences using the BIO tagging approach.
- Use a transformer-based NER model to identify entities in text.
- Build a Flask web service to make predictions through a REST API.
- Test the prediction endpoint and record prediction activity.

## Methodology

### 1. Dataset Exploration

The `Visualization Of Dataset - Understanding.ipynb` notebook focuses on understanding and visualising the dataset, including its text and annotation structure.

The project uses the PLOD dataset, which contains biomedical text annotated for abbreviation and long-form identification.

### 2. Named Entity Recognition

The application uses a pre-trained RoBERTa model for token classification:

`dipteshkanojia/roberta-large-finetuned-ner`

The Hugging Face Transformers pipeline processes submitted text and returns NER predictions.

### 3. Flask API Development

A Flask application exposes a prediction endpoint:

- **Endpoint:** `/predict`
- **Method:** `POST`
- **Input:** JSON containing a `text` field
- **Output:** JSON containing the model's entity predictions

Example request:

```json
{
  "text": "Example biomedical text containing an abbreviation."
}
```

The application also converts model outputs into JSON-serialisable values and logs the timestamp, input text and prediction output in `predictions.log`.

## Repository Structure

| File | Description |
|---|---|
| `Visualization Of Dataset - Understanding.ipynb` | Dataset exploration and visualisation |
| `app.py` | Flask application and NER prediction endpoint |
| `test_deployed_endpoint.ipynb` | Notebook for testing the deployed endpoint |
| `requirements.txt` | Python dependencies |
| `predictions.log` | Logged prediction requests and outputs |

## Technologies Used

- Python
- Natural Language Processing (NLP)
- Biomedical Text Processing
- Named Entity Recognition (NER)
- RoBERTa
- Hugging Face Transformers
- Flask
- NumPy
- Jupyter Notebook

## Running the Application

Clone the repository:

```bash
git clone https://github.com/nimishaarajesh/Natural-Language-Processing.git
cd Natural-Language-Processing
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python app.py
```

The application runs on port `5000` and exposes the `/predict` endpoint.

## Notes

The repository demonstrates dataset exploration, transformer-based entity recognition and API integration. The prediction application loads a pre-trained model from Hugging Face; model training is not included in the Flask application code.

