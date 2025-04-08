# Medical Chatbot using LangChain and Flask

A sophisticated medical chatbot that leverages LangChain, OpenAI, and Pinecone to provide accurate medical information from a comprehensive The Gale Encyclopedia of Medicine Vol-1.

## Overview

This project implements a medical chatbot with the following key features:
- Web-based chat interface using Flask and Bootstrap
- PDF document processing and text chunking
- Vector embeddings using HuggingFace transformers
- Vector storage and similarity search using Pinecone
- Question answering using OpenAI's language model
- Retrieval Augmented Generation (RAG) for accurate responses

## Architecture

```
MedicalBot_01/
├── app.py               # Flask application
├── store_index.py       # Vector store initialization
├── template.py          # Project structure creator
├── setup.py             # Package configuration
├── requirements.txt     # Dependencies
├── src/
│   ├── helper.py        # Utility functions
│   ├── prompt.py        # System prompts
│   └── __init__.py
├── static/
│   └── style.css        # Chat UI styling
├── templates/
│   └── index.html       # Chat interface
├── Data/
│   └── Medical_book.pdf # Medical encyclopedia (Data set)
└── research/
    └── trials.ipynb     # Development notebook
```

## Features

1. **Document Processing**
   - Loads PDF medical encyclopedia
   - Splits text into manageable chunks
   - Creates embeddings using HuggingFace transformers

2. **Vector Storage**
   - Uses Pinecone for vector storage
   - Implements similarity search
   - Serverless architecture on AWS

3. **Chat Interface**
   - Real-time chat using Flask
   - Responsive Bootstrap design
   - Clean and intuitive UI

4. **Question Answering**
   - Context-aware responses
   - Uses OpenAI's language model
   - Retrieval augmented generation

## Setup

1. Clone the repository:
```bash
git clone [<repository-url>](https://github.com/CSzzs/Medical-chatbot-with-custom-dataset)
cd MedicalBot_01
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file with your API keys:
```
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

4. Initialize the vector store:
```bash
python store_index.py
```

5. Run the application:
```bash
python app.py
```

## Usage

1. Access the chat interface at `http://localhost:8000`
2. Type your medical question in the chat input
3. Receive accurate responses based on the medical encyclopedia

## Technical Details

- **Embeddings**: Uses `sentence-transformers/all-MiniLM-L6-V2` model
- **Vector Dimension**: 384
- **Chunk Size**: 500 characters with 20 character overlap
- **Similarity Search**: Top 3 most relevant chunks
- **LLM Temperature**: 0.4 for balanced responses

## Dependencies

- langchain==0.3.23
- flask
- pypdf
- python-dotenv
- pinecone-client[grpc]
- langchain-pinecone==0.2.4
- langchain-community==0.3.21
- langchain-openai==0.3.12
- sentence-transformers==2.3.0
- transformers==4.35.0

## License

MIT License

Copyright (c) 2024 Chandima Senarathna

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Author

Chandima Senarathna
Email: chandima.senarathna97@gmail.com

## Acknowledgments

- OpenAI for the language model
- Pinecone for vector storage
- HuggingFace for transformers
