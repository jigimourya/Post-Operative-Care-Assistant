# 🏥 Post-Operative Care Assistant

### AI-Powered Clinical Support for Post-Surgical Recovery

The **Post-Operative Care Assistant** is an intelligent healthcare support system that helps patients and clinicians obtain **safe, relevant, and context-aware recommendations** after surgery.  
It uses a **Retrieval-Augmented Generation (RAG)** pipeline powered by **FAISS**, **text embeddings**, and **large language models (LLMs)** to provide accurate postoperative guidance and safety evaluations.

---

## 🚀 Features

- 🤖 **AI-Generated Clinical Advice** — Delivers safe, evidence-based postoperative recommendations.  
- 📚 **RAG-Based Retrieval** — Retrieves context from medical documents using FAISS and text embeddings.  
- 🩺 **Dynamic Context Control** — Slider to select how many context chunks (1–10) to retrieve for each query.  
- ✅ **Response Categorization** — Classifies model outputs (AI Recommendation, General Info, or Safety Alert).  
- ⚠️ **Safety Evaluation** — Automatically flags unsafe, incomplete, or irrelevant responses.  
- 💻 **Modern Gradio Interface** — Interactive web UI for entering patient data and viewing results.

---

## 🧩 System Architecture

```text
Patient Query + EHR Info
          │
          ▼
   Embedding Retrieval (FAISS)
          │
          ▼
   Context Fusion + LLM Response
          │
          ▼
Safety Evaluation → Categorization → UI Display
```

### Components

**1. Data Ingestion:** Loads and splits surgical/EHR text into smaller chunks for embedding.

**2. Context Retrieval:** Retrieves top-K relevant chunks using FAISS similarity search.

**3. Response Generation:** Combines user input with retrieved text to generate a safe, context-aware reply.

**4. Evaluation Module:** Flags potentially unsafe or incomplete advice.

**5. Gradio UI:** Displays query, AI output, and evaluation results neatly.

## 🖥️ Tech Stack

| Component    | Technology                                                                                          |
| ------------ | --------------------------------------------------------------------------------------------------- |
| Interface    | [Gradio](https://gradio.app)                                                                        |
| Backend      | Python 3.12                                                                                         |
| Vector Store | [FAISS](https://faiss.ai)                                                                           |
| Embeddings   | [Hugging Face Sentence Transformers](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) |
| LLM          | OpenAI / Hugging Face / Local Model                                                                 |

## 📊 Example Interaction

#### 🧾 Patient Query:

```Can I skip my antibiotics if I feel better after surgery? ```

#### 🏷 Surgery Type:

```Appendectomy```

#### 🧬 Allergies:

```None```

#### 🕒 Recovery Timeline:

```3 days post-op```

#### AI Response:

```Based on the information provided, it is recommended that you continue taking your prescribed antibiotics as directed by your healthcare provider after an appendectomy surgery for the full duration of your prescription to reduce the risk of infection...```

**Response Category:** _✅ AI Recommendation_

**Flagged?** _❌ False_


## ⚡ How It Works

1. User enters patient query, surgery type, allergies, and recovery timeline.

2. The system retrieves relevant medical context from the FAISS knowledge base.

3. The LLM generates a contextually accurate and safe response.

4. A safety evaluator checks for potential harm or misinformation.

5. Results are displayed in the Gradio dashboard.

## ⚠️ Disclaimer

This application is intended for educational and research purposes only.
It is not a substitute for professional medical advice, diagnosis, or treatment.
Always seek the guidance of a licensed healthcare provider for medical concerns.
