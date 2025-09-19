# codegen-student-350m-distill-rag

This repository provides a **complete, reproducible workflow** for training, distilling, and serving a **small code-generation model (~350M parameters)** and integrating it with a **retrieval-augmented generation (RAG)** pipeline powered by **FAISS**.  

The project was designed to demonstrate how a large teacher model (e.g., *StarCoder, GPT-style models*) can be **distilled into a compact student model** while retaining useful capabilities. Once trained, the model can be deployed with **retrieval support** over your own dataset (documentation, codebase, research notes, etc.), enabling more accurate and context-aware code generation.

> Your uploaded notebook (`notebooks/distill_codegen350M_light.ipynb`) is the seed for this project. This repository generalizes it into a GitHub-ready structure.

---

## 🔍 Project Overview

Modern code LLMs like StarCoder or CodeLlama are powerful but often **too large to run on modest GPUs** or edge devices. The solution is to **distill** knowledge from a large "teacher" model into a smaller "student" model.  

This repository shows how to:
1. **Distill / fine-tune** a small student code model (≈350M parameters) from a teacher model.
2. Use **PEFT/LoRA adapters** to make training memory-efficient, then **merge adapters** into the base model.
3. Build a **retrieval index (FAISS)** over your documents/corpus.
4. Combine the student model with **retrieval-augmented generation (RAG)** so that answers use relevant snippets from your data.
5. Serve the model via a **FastAPI** backend for easy integration into apps or tools.

In short:  
➡️ **Distillation** reduces compute requirements.  
➡️ **RAG** improves factual grounding.  
➡️ **FastAPI** deployment makes it practical.  

---

## ✨ Features

- **Distillation & fine-tuning**: train a compact student from a teacher.
- **LoRA/PEFT adapters**: efficient training with low memory usage.
- **Merging adapters**: export a standalone student checkpoint.
- **Lightweight RAG**: FAISS index + Sentence Transformers for semantic retrieval.
- **Configurable CLI tools**: `train.py`, `merge.py`, `infer.py`, `serve.py`.
- **Production-ready FastAPI server**: expose `/generate` for inference.
- **Reproducible repo structure**: ready for GitHub publishing.



