# Agentic AI Interview Evaluator (RAG-Based)

## Overview
This project is an Agentic AI-powered interview evaluator that assesses candidate answers using:
- Large Language Model (Mistral-7B)
- Retrieval-Augmented Generation (RAG)
- FAISS vector similarity search

The system dynamically decides whether external context is needed and evaluates answers with structured scoring.

---

## Key Features
- Agent-based decision making (retrieval vs no retrieval)  
- RAG pipeline using FAISS and Sentence Transformers  
- Automated answer evaluation with scoring (0–10)  
- Context-aware feedback generation  
- Robust parsing for LLM outputs  
- Interactive interview simulation  

---

## Architecture

User Input (Answer)
        ↓
Agent Decision (LLM)
        ↓
Retrieval Needed?
        ↓ Yes
FAISS Vector Search
        ↓
Context Retrieved
        ↓
Answer Evaluation (LLM)
        ↓
Structured Output (Score + Reason)

---

## Tech Stack

- LLM: Mistral-7B-Instruct  
- Embeddings: all-MiniLM-L6-v2  
- Vector Database: FAISS  
- Framework: Hugging Face Transformers  
- Language: Python  

---

## Project Structure

├── data/
│   └── normalized_ds_questions.csv  
├── notebook/
│   └── agentic_ai.ipynb  
├── README.md  

---

## Installation

pip install faiss-cpu sentence-transformers transformers torch pandas

---

## How It Works

1. Data Preparation  
- Load dataset with question-answer pairs  
- Convert into embeddings  

2. Vector Indexing  
- Store embeddings in FAISS for fast retrieval  

3. Agent Decision  
- LLM decides if retrieval is required  

4. Retrieval (Optional)  
- Fetch top-k similar question-answer pairs  

5. Evaluation  
- LLM evaluates answer using strict scoring rules  

---

## Example Flow

Question: What is overfitting?  

Your Answer: Model is too complex  

Output:  
Score: 5  
Reason: Partial answer, lacks explanation  

---

## Output Format

Score: <0–10>  
Reason: <short explanation>  

---

## Key Components

Retrieval Function  
- Uses FAISS similarity search  

Agent Decision  
- Determines if context is required  

Evaluation Engine  
- Applies strict scoring logic via LLM  

Prompt Engineering  
- Ensures structured and controlled outputs  

---

## Limitations

- Requires GPU for optimal performance  
- LLM outputs may occasionally need parsing safeguards  
- Retrieval quality depends on dataset quality  

---

## Future Improvements

- Build UI using Streamlit  
- Fine-tune domain-specific model  
- Deploy using FastAPI  
- Integrate with vector databases (Pinecone, Weaviate)  
- Add multi-turn interview capability  

---

## Use Cases

- Interview preparation platforms  
- Automated candidate screening  
- Educational AI systems  
- HR technology solutions  

---

## Author

Roji Vincent C.
