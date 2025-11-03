**🧠 Medical RAG Chatbot (LangChain + Chroma + Hybrid Search)**

This project is a Retrieval-Augmented Generation (RAG) app designed for medical documents.
It allows users to upload a PDF, build a knowledge index, ask medical questions, and generate summaries — powered by LangChain, ChromaDB, Hybrid Search (BM25 + Dense), and Claude Opus.

⸻

🚀 Features

Feature	Description
📄 PDF Upload	User uploads a medical PDF

⚙️ Vector Index Builder	Extract & embed document chunks (HuggingFace MiniLM)

🔍 Hybrid Retrieval	Dense + BM25 + Cross Encoder Re-ranking

🧠 RAG QA	Claude Opus answers using retrieved context

📝 Document Summary	Map-reduce summarization using LLM

💾 Persistent Chroma DB	Index remains across sessions

📊 RAG Evaluation Script	Measures retrieval & answer quality


⸻

🏗️ Architecture

User → Streamlit UI → Index Builder → ChromaDB → Hybrid Retriever → Claude Opus

Pipeline:

PDF Upload → Text Split → Embeddings → Chroma Vector Store
↓
Query → BM25 + Vector Search + Cross-Encoder Rerank
↓
Claude Opus LLM answers using retrieved context


⸻


📂 Project Structure


<img width="560" height="197" alt="image" src="https://github.com/user-attachments/assets/3aa41af3-ae7a-4697-b12d-fdd405d5e670" />



⸻


<img width="666" height="391" alt="image" src="https://github.com/user-attachments/assets/71639886-94e1-4c11-892e-3cffe82fb445" />



⸻

▶️ Run the Application

Python 3.10+ recommended

1️⃣ Install Dependencies

pip install -r requirements.txt

2️⃣ Run Streamlit App

streamlit run app.py

3️⃣ Upload PDF → Click Build Knowledge Index → Ask Questions ✅

⸻

🧪 RAG Evaluation

Run this to score retrieval + response quality:

python evaluate_rag.py

Evaluation Output Example:

Average Retrieval Similarity: 0.45
Average Generation Similarity: 0.56

Scores improve with better embeddings, improved chunking, and more data.

⸻

💼 Business Value 

✅ Faster access to scientific docs

✅ Reduces medical team workload

✅ Ensures context-grounded, compliant responses

✅ No hallucinations — answers only from uploaded docs

✅ Keeps proprietary research private (local vector DB)

⸻

🔐 Compliance Notes (Pharma/Healthcare)

	•	PDF is processed locally
	
	•	Chroma runs on enterprise VPC/desktop
	
	•	LLM API can be swapped with private deployment (Azure Anthropic/OpenAI)
	
	•	Enforces evidence-based answer grounding

⸻

🤝 Future Enhancements

	•	Enterprise DB support (PGVector / Milvus)
	
	•	FDA 21 CFR Part 11 audit logs
	
	•	Retrieval evaluation UI dashboard
	
	•	Prompt-level RAG guardrails
	
	•	Multi-document knowledge base support

