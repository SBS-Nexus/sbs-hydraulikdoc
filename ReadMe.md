# SBS Nexus – Technical Intelligence (HydraulikDoc)

> Technische Dokumenten-KI für Industrie & Hydraulik – beantwortet komplexe Servicefragen aus Datenblättern und Handbüchern in Sekunden.

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-red.svg)](https://streamlit.io/)
[![RAG](https://img.shields.io/badge/AI-RAG-blueviolet.svg)](#)

## 🎯 Zweck

HydraulikDoc ist der **Technical-Baustein** der SBS Nexus Plattform.  
Es durchsucht lange technische Datenblätter und Handbücher und beantwortet Fragen wie:

- „Wie hoch ist der Prüfdruck für den CDH2 Zylinder?“
- „Welche Dichtungsarten gibt es für dieses Modell?“
- „Für welche Medien ist die Dichtungsart M geeignet?“

Statt 80 Seiten PDF zu lesen, erhalten Serviceteams eine geprüfte Antwort in Sekunden.

---

## 🧱 Architektur (Kurzfassung)

- **App:** Streamlit (oder React-Frontend + FastAPI Backend)
- **RAG-Stack:** LangChain + Vector-DB (z.B. Pinecone/Weaviate)
- **Embeddings:** Claude / OpenAI Embeddings
- **Storage:** S3-kompatibler Storage für PDFs
- **Indexierung:** Chunking der PDFs + Embeddings pro Chunk
- **Quelle:** Bosch Rexroth, Herstellerdatenblätter, Normen, interne Manuals

---

## 🚀 Quickstart (Dev)

```bash
git clone https://github.com/SBS-Nexus/sbs-hydraulikdoc.git
cd sbs-hydraulikdoc

python -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt

cp .env.example .env
# LLM-Keys, Vector-DB-Keys etc.

streamlit run app.py
