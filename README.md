# pdf-rag-assistant
A lightweight, LLM-powered Question-Answering system using Retrieval-Augmented Generation (RAG). Upload a PDF document and ask questions about its content. Combines FAISS for vector search, SentenceTransformers for embeddings, and FLAN-T5 with LangChain for response generation. Deployed with Gradio for an interactive UI.

**What I Built**
I implemented a full end-to-end pipeline that includes:

**PDF Text Extraction**
Using the PyMuPDF library, I parsed and extracted raw text content from user-uploaded PDF files.

**Text Chunking**
The extracted text was split into manageable overlapping chunks using LangChain's RecursiveCharacterTextSplitter to ensure semantic continuity.

**Semantic Embedding Generation**
Each chunk was converted into vector representations using the all-MiniLM-L6-v2 model from the sentence-transformers library.

**Vector Store Creation (FAISS)**
I used FAISS to build an efficient vector index for fast retrieval of semantically similar chunks based on user queries.

**Retrieval + Prompt Construction**
When a user asked a question, the system retrieved the top-K relevant chunks and combined them into a prompt to give context to the language model.

**Answer Generation (LLM)**
I used the google/flan-t5-small model (a fine-tuned, instruction-following model) via Hugging Face Transformers to generate the final answer.

**Gradio Interface for Deployment**
Finally, I deployed the solution using Gradio, providing a clean, interactive web app where users can:

Upload a PDF file

Enter a natural language query

Get precise answers extracted and generated based on document content

**Technical Stack**
Python

PyMuPDF (fitz)

LangChain

Sentence Transformers (all-MiniLM-L6-v2)

FAISS (Facebook AI Similarity Search)

Hugging Face Transformers (flan-t5-small)

Gradio (for web UI and deployment)

**Outcome**
The result is a fast, modular, and easy-to-use question-answering tool for any PDF content. This solution can be extended to legal, financial, academic, or enterprise documents, and is a great example of practical RAG system development.
