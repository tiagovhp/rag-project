# Mental Health Diagnosis - Retrieval-Augmented Generation (RAG) Project

This project leverages Retrieval-Augmented Generation (RAG) for efficient diagnosis and information retrieval in the domain of mental health, specifically using data from the *Diagnostic and Statistical Manual of Mental Disorders (DSM-5)*. The project involves extracting information from a PDF, categorizing it, generating embeddings, and storing them in a vector database for efficient querying. The system then uses an LLM to provide concise and context-aware answers to queries related to mental health.

## Project Overview
This work was completed as part of the Data Science & Machine Learning bootcamp at Ironhack. The goal is to demonstrate how RAG can be used to assist healthcare professionals and researchers by providing accurate and contextually relevant answers from the DSM-5 manual.

## File Structure
- **main.ipynb**: Jupyter notebook containing all the code used in the project.
- **RAG_Mental_Health_Diag.pdf**: Presentation of the project, including methods, results, and key insights.
- **Multi-Modal-RAG-Results.csv**: File containing the queries, generated answers, and evaluation scores from the LLM.
- **README.md**: This file, explaining the project in detail.
- **requirements.txt**: List of dependencies required to run the project.

## Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-repo-link
   cd your-repo-folder

2. **Create a virtual environment (recommended)**:
python -m venv venv
source venv/bin/activate   # On Linux/macOS
venv\Scripts\activate      # On Windows

3. **Install dependencies**:
pip install -r requirements.txt

## How It Works
- **Data Extraction**: The DSM-5 PDF is parsed to extract text, images, and tables using Python libraries like `unstructured`.
- **Data Categorization**: Extracted elements are categorized into text, tables, and images for efficient summarization and retrieval.
- **Summarization**: Each element is summarized using an LLM to optimize it for embedding and retrieval.
- **Text Chunking**: Summarized texts are chunked into manageable pieces to enhance the retrieval performance.
- **Embedding Generation**: Embeddings are created for each chunk using the OpenAI Embeddings model.
- **Database Creation**: A vector database (ChromaDB) is used to store the embeddings and associated texts.
- **Querying**: User queries are embedded and matched with stored embeddings to retrieve the most relevant information.
- **Answer Generation**: An LLM uses the retrieved context to generate and return answers.
- **Evaluation**: The LLM-generated responses are scored for relevance and accuracy using another LLM model as a judge.

## Example Queries
Here are some sample questions answered using this system:
- "What are the diagnostic criteria for Major Depressive Disorder?"
- "How does DSM-5 classify different anxiety disorders?"
- "What is the recommended treatment approach for PTSD?"
- "How are personality disorders grouped and diagnosed?"
- "What changes were introduced in DSM-5 for Autism Spectrum Disorder?"
- "How does the DSM-5 handle comorbid conditions?"
- "What are the symptoms required for a diagnosis of Bipolar I Disorder?"
- "How is schizophrenia diagnosed, and what are the exclusion criteria?"
- "What are the guidelines for diagnosing substance use disorders?"
- "How is obsessive-compulsive disorder differentiated from generalized anxiety disorder?"

## Evaluation
The responses from the LLM are evaluated using another LLM model. Each answer is scored out of 5 for relevance and accuracy, and detailed feedback is provided. This process ensures that the system's performance is rigorously assessed and improved.

## Requirements
- Python 3.8+
- Dependencies listed in `requirements.txt`

## Future Work
- Expand the project to include more comprehensive medical data.
- Integrate additional vector databases for larger-scale deployment.
- Improve the evaluation mechanism using human expert feedback.
- Explore more advanced chunking and summarization techniques.

## Acknowledgments
This project is part of my Data Science & ML bootcamp at Ironhack. Special thanks to the bootcamp instructors and my peers for their support and guidance.
