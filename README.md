Resume Analyzer
Overview
The Resume Analyzer is a Python-based tool that helps in evaluating resumes against job descriptions. It provides a similarity score between a resume and a job description, suggests improvements by identifying missing keywords, and extracts essential information like contact details and educational background. This tool leverages natural language processing (NLP) techniques using the BERT model for text encoding and transformers for summarization and named entity recognition (NER).

Features
Text Preprocessing: Cleans and tokenizes text, removing stopwords for better analysis.
Text Encoding: Uses the BERT model to convert text into numerical representations.
Similarity Calculation: Computes the cosine similarity between the encoded resume and job description.
Improvement Suggestions: Identifies missing keywords in the resume that are present in the job description.
Content Summarization: Summarizes long sections of text, making it easier to extract essential details.
Contact Information Extraction: Identifies and extracts Gmail addresses, phone numbers, and educational institutions mentioned in the text.
Requirements
Python 3.x
Transformers library
NLTK (Natural Language Toolkit)
PyTorch
Other dependencies listed in requirements.txt (if applicable)
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/resume-analyzer.git
cd resume-analyzer
Install the required Python packages:

bash
Copy code
pip install -r requirements.txt
Download NLTK stopwords:

python
Copy code
import nltk
nltk.download('stopwords')
Usage
Preprocess and Encode Text
Use the preprocess_text and encode_text functions to clean and encode the resume and job description texts:

python
Copy code
cleaned_text = preprocess_text(resume_text)
encoded_text = encode_text(cleaned_text)
Calculate Similarity and Suggest Improvements
Calculate the similarity score and suggest improvements for the resume:

python
Copy code
score, improvements = analyze_resume(resume_text, job_desc_text)
print(f"Similarity Score: {score}")
print(f"Suggested Improvements: {improvements}")
Summarize Content
Summarize sections of the resume or job description:

python
Copy code
summary = summarizer(long_text)
print(summary)
Extract Contact Information
Extract Gmail addresses, phone numbers, and educational background:

python
Copy code
contact_info = extract_contact_info(resume_text)
print(f"Contact Information: {contact_info}")
Example
python
Copy code
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
