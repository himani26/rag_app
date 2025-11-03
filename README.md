#Life Sciences RAG Assistant

A Retrieval-Augmented Generation (RAG) pipeline designed for pharmaceutical document intelligence. This solution enables users to upload PDFs (e.g., drug monographs, clinical trial summaries, medical guidelines), build a searchable knowledge index, ask medical questions, and receive grounded, context-based answers.

⸻

🔍 Key Capabilities
	•	Upload pharma PDFs and build vector index
	•	Query drug-related information
	•	Generates context-aware and factual answers using LLM
	•	On-demand summarization of PDFs
	•	Embedded RAG evaluation script for precision scoring

⸻

📁 Project Structure

rag_pipeline/
│── app.py                 # Streamlit UI
│── src/
│   ├── build_index.py     # PDF loading, chunking, vector store creation
│   ├── rag_pipeline.py    # Retriever + RAG chain creation
│   ├── llm_config.py      # LLM + embedding config
│   ├── summarize.py       # PDF summarization pipeline
│   └── evaluate_rag.py    # RAG performance evaluation
└── vector_store/          # Persisted Chroma DB


⸻

⚙️ How It Works

1️⃣ Upload PDF & Build Index
	•	Loads PDF pages
	•	Splits into 1000-char chunks (150 overlap)
	•	Embeds using MiniLM HuggingFace embeddings
	•	Saves vectors in ChromaDB

2️⃣ Ask a Question
	•	Query is embedded
	•	Hybrid search retrieves most relevant text
	•	Claude Opus answers only using retrieved context

3️⃣ Optional — PDF Summary
	•	Map-reduce summarization pipeline
	•	Provides quick, structured medical insights

4️⃣ Evaluate RAG
	•	Cosine-similarity scoring vs human ground truths
	•	Retrieval & generation accuracy metrics

⸻

🧠 Tech Stack & Justification

Component	Choice	Reason
Vector DB	Chroma	Lightweight, fast, persistent, local
Embeddings	MiniLM	Small, accurate, fast for pharma domain
LLM	Claude-3 Opus	Strong factual grounding & medical reasoning
Framework	LangChain	Modular RAG orchestration, retrievers, wrappers
UI	Streamlit	Rapid prototyping + user-friendly


⸻

🚀 Running the Application

Install dependencies

pip install -r requirements.txt

Run Streamlit app

streamlit run app.py

Build Vector Index

Click “Build Index” in UI after uploading PDF

Ask Questions & View Answers

Type your query in the UI and hit Search

Evaluate RAG

python src/evaluate_rag.py


⸻

📊 Evaluation Method
	•	10 curated pharma questions (Repatha/Aimovig)
	•	Cosine similarity scoring
	•	Reports retrieval vs generation performance

⸻

📌 Business Value
	•	Accelerates access to medical knowledge
	•	Reduces manual search across 300-page drug docs
	•	Improves medical call-center productivity
	•	Enables medical reps & clinicians to get factual info fast
	•	Customizable for pharmacovigilance, medical affairs, clinical teams

⸻

🔮 Future Enhancements
	•	BM25 + dense hybrid retriever
	•	Reranking via cross-encoder (bio-med models)
	•	RAG hallucination guardrails
	•	Multi-document ingestion & multi-file search



