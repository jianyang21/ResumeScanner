# Resume Analyzer

## Overview

The Resume Analyzer is a Python-based tool designed to evaluate resumes against job descriptions. It provides a similarity score between a resume and a job description, suggests improvements by identifying missing keywords, and extracts essential information like contact details and educational background. This tool utilizes natural language processing (NLP) techniques, including the BERT model for text encoding and transformers for summarization and named entity recognition (NER).

## Features

- **Text Preprocessing**: Cleans and tokenizes text, removing stopwords for improved analysis.
- **Text Encoding**: Converts text into numerical representations using the BERT model.
- **Similarity Calculation**: Computes cosine similarity between the encoded resume and job description.
- **Improvement Suggestions**: Identifies missing keywords in the resume that are present in the job description.
- **Content Summarization**: Summarizes long sections of text for easier extraction of essential details.
- **Contact Information Extraction**: Identifies and extracts Gmail addresses, phone numbers, and educational institutions mentioned in the text.

## Requirements

- Python 3.x
- Transformers library
- NLTK (Natural Language Toolkit)
- PyTorch
- Other dependencies listed in `requirements.txt` (if applicable)

## Installation

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/yourusername/resume-analyzer.git
    cd resume-analyzer
    ```

2. **Install the Required Python Packages:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Download NLTK Stopwords:**

    ```python
    import nltk
    nltk.download('stopwords')
    ```

## Usage

1. **Preprocess and Encode Text**

   Use the `preprocess_text` and `encode_text` functions to clean and encode the resume and job description texts:

    ```python
    cleaned_text = preprocess_text(resume_text)
    encoded_text = encode_text(cleaned_text)
    ```

2. **Calculate Similarity and Suggest Improvements**

   Calculate the similarity score and suggest improvements for the resume:

    ```python
    score, improvements = analyze_resume(resume_text, job_desc_text)
    print(f"Similarity Score: {score}")
    print(f"Suggested Improvements: {improvements}")
    ```

3. **Summarize Content**

   Summarize sections of the resume or job description:

    ```python
    summary = summarizer(long_text)
    print(summary)
    ```

4. **Extract Contact Information**

   Extract Gmail addresses, phone numbers, and educational background:

    ```python
    contact_info = extract_contact_info(resume_text)
    print(f"Contact Information: {contact_info}")
    ```

## Example

```python
resume_text = """
John Doe
Email: john.doe@gmail.com
Phone: 123-456-7890
Bachelor of Technology in Artificial Intelligence
Shiv Nadar University
"""

job_desc_text = """
We are looking for a data scientist with experience in artificial intelligence, machine learning, and data analysis.
"""

score, improvements = analyze_resume(resume_text, job_desc_text)
print(f"Similarity Score: {score}")
print(f"Suggested Improvements: {improvements}")

contact_info = extract_contact_info(resume_text)
print(f"Contact Information: {contact_info}")
