# Retrieval-Augmented Generation for Diabetes Treatment and Diagnosis

## Project Overview
This project implements a Retrieval-Augmented Generation (RAG) approach to assist in the treatment and diagnosis of diabetes. The system extracts information from a PDF of diabetes guidelines, summarizes the extracted data (including text, tables, and images), and uses this information to generate answers to user queries. It incorporates both text processing and image summarization, along with a vector database for efficient information retrieval.

## Features
- Extracts and categorizes data from PDF documents.
- Summarizes text, tables, and images for effective retrieval.
- Utilizes OpenAI's language model for generating responses based on retrieved data.
- Evaluates the quality of generated responses using self-assessment from the language model.

## Requirements
- Python 3.x
- Libraries:
  - `openai`
  - `unstructured`
  - `langchain`
  - `chromadb`
  - `pandas`
  - `numpy`
  
## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/diabetes-treatment-rag.git
    cd diabetes-treatment-rag
    ```

2. Create a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

4. Set up your OpenAI API key:
    ```bash
    export OPENAI_API_KEY='your_openai_api_key'  # On Windows use `set` instead of `export`
    ```

## Usage
1. Prepare your PDF file with diabetes guidelines and place it in the `data/` directory.
2. Run the main script:
    ```bash
    python main.py
    ```
3. Follow the prompts or review the outputs in the console to query the system.

## Code Structure
- `main.py`: The main script to execute the project.
- `data/`: Directory containing the PDF files to be processed.
- `figures/`: Directory for storing extracted images from the PDFs.
- `output/`: Directory for saving results, such as the CSV output of responses and evaluations.

### Important Functions
- **extract_pdf_elements(path, fname)**: Extracts text, tables, and images from the specified PDF file.
- **categorize_elements(raw_pdf_elements)**: Categorizes extracted elements into texts, tables, and images.
- **summarize_text_or_tables(text_or_tables, type_)**: Summarizes the extracted text and tables using OpenAI's model.
- **summarize_images(image_directory)**: Encodes and summarizes images extracted from the PDFs.
- **embed_text(text)**: Generates embeddings for text chunks for efficient retrieval.
- **evaluate_responses(queries)**: Evaluates the generated responses for accuracy and relevance.

## Evaluation
The project includes a self-evaluation component where the language model assesses the relevance and accuracy of its own responses based on user queries. This helps to refine the model's performance over time.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Special thanks to OpenAI for providing the GPT-4 model.
- The `unstructured` library for extracting data from PDFs.
- The `langchain` library for integrating LLMs into the workflow.
