## Project_03

## Document Question Answering & Summarization System

### Project Overview
This project implements a document processing system that can answer questions about uploaded documents and generate summaries. The system supports PDF, Word (.docx), and plain text (.txt) files, using natural language processing models to provide accurate answers and concise summaries.

### Key Features
**1. Document Processing:**
- Extracts text from PDF, Word, and plain text files
- Handles multi-page documents seamlessly

**2. Question Answering:**
- Uses DistilBERT model fine-tuned on SQuAD dataset
- Provides answers with confidence scores
- Shows answer location within the document

**3. Summarization:**
- Utilizes Facebook's BART-large-CNN model
- Generates concise summaries (30-150 words)
- Preserves key information from documents

**4. User Interface:**
- Intuitive Gradio web interface
- Supports simultaneous question answering and summarization
- Shows detailed output with confidence metrics

## Technical Implementation

### Core Components
**1. Text Extraction:**
- PyPDF2 for PDF processing
- python-docx for Word document parsing
- Native Python file handling for text files

**2. NLP Models:**
- distilbert-base-cased-distilled-squad for question answering
- facebook/bart-large-cnn for summarization
- Both models run locally after initial download

**3. Web Interface:**
- Gradio for simple web app creation
- File upload widget with format validation
- Configurable options for question and summary

### Key Functions
- extract_text_from_file(): Handles document parsing for different formats
- process_document(): Orchestrates QA and summarization tasks
- Gradio interface: Provides user interaction layer

### System Requirements
- Python 3.7+
- Required packages:
- transformers
- torch
- gradio
- PyPDF2
- python-docx

### Usage Guide
1.	Launch the application
2.	Upload a document (PDF, Word, or text file)
3.	Optionally enter a question about the document
4.	Check the "Generate Summary" box if you want a summary
5.	Click "Submit" to process the document
6.	View results in the output box

### Performance Considerations
- Initial model loading may take time (models are downloaded on first run)
- Large documents may take longer to process
- For production use, consider:
        - Adding document size limits
        - Implementing caching
        - Using GPU acceleration
        - Setting up a queuing system for multiple requests

### Limitations
- Current version is a demo with basic functionality
- Accuracy depends on the pre-trained models
- Very large documents may exceed memory limits
- Complex formatting may not be preserved in text extraction

### Future Enhancements
**1. Advanced Features:**
- Document chunking for large files
- Multiple question processing
- Support for more file formats (e.g., PPT, HTML)
- Youtube

**2. Performance Improvements:**
- Model quantization for faster inference
- Batch processing capabilities

**3. User Experience:**
- Progress indicators
- History of previous queries
- Export functionality for results

## Conclusion
This Document Question Answering & Summarization System provides a powerful yet accessible tool for extracting information from documents. By combining state-of-the-art NLP models with a simple interface, it makes document analysis accessible to non-technical users while offering customization options for more advanced requirements.
The project demonstrates how modern NLP can be applied to practical document processing tasks, and serves as a foundation for more specialized document analysis applications.

### References
- https://seqlegal.com/free-legal-documents (for legal free templates)
- https://huggingface.co/distilbert/distilbert-base-cased-distilled-squad
- ChatGPT for creation of examples of legal documents
- https://www.sfgov.org/adultprobation/sites/default/files/P-600%20Contract%20Sample%20post%20on%20website2.pdf




## Notes:
### Use of DistilBERT fine-tuned on SQuAD

**DistilBERT:** 
    DistilBERT is a lightweight and faster version of BERT, a popular natural language processing model. It achieves similar performance to BERT while being significantly smaller and faster, making it suitable for various applications.

**Fine-tuning:** 
    Fine-tuning is a process where a pre-trained model, like DistilBERT, is further trained on a specific dataset and task. In this case, DistilBERT is fine-tuned on the SQuAD dataset, which is a collection of questions with corresponding answers and context. 

**SQuAD (Stanford Question Answering Dataset):** 
    SQuAD is a widely used dataset for training and evaluating question answering models. It consists of questions about given Wikipedia articles, with the answers extracted as spans of text from the article.

**Benefits of fine-tuning:** 
    By fine-tuning DistilBERT on SQuAD, the model becomes more adept at understanding the relationship between questions and their answers within a context. This results in improved performance on question answering tasks and can lead to more accurate and reliable answers. 
