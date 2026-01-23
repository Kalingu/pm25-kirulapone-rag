# PM2.5 Kirulapone RAG – Retrieval-Augmented Generation for Air Quality Insights

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline to provide **instant answers (0.0s)** on PM2.5 air pollution in Kirulapone, Colombo. It combines **vector embeddings** from historical air quality data with a **language model** (LLM) to enable **contextual, natural language querying**.  

*Role:* Contributor – implemented vector search and integrated LLM-based responses.

---

## Dataset

- **Source:** Local air quality monitoring station, Kirulapone, Colombo  
- **Time period:** Hourly readings from **9th January 2022 to 5th December 2025**  
- **Number of records:** 24,864  
- **Features:**  
  - **Target variable:** `pm2_5` (fine particulate matter)  
  - **Other variables:** `pm10`, `carbon_monoxide`, `carbon_dioxide`, `nitrogen_dioxide`, `sulphur_dioxide`, `ozone`, `aerosol_optical_depth`, `dust`, `uv_index`, `uv_index_clear_sky`, `ammonia`, `methane`  
- **Data quality:** No missing values in the `pm2_5` column

---

## RAG Pipeline Overview

1. **Data preprocessing:** Clean PM2.5 dataset, create vector embeddings  
2. **Vector store:** Store embeddings for efficient retrieval  
3. **Query handling:** User query → nearest vectors retrieved  
4. **LLM generation:** LLM (llama3.2) produces context-aware answers  
5. **Output:** Instant answer (0.0s) with reference to dataset

*Optional:* Include a pipeline diagram:  
`images/rag_pipeline.png`

---

## Example Queries

| Query | Time | Answer |
|-------|------|--------|
| "N-BEATS RMSE?" | 0.0s | 1.66 µg/m³ |
| "Average PM2.5 in 2023?" | 0.0s | 12.3 µg/m³ |
| "Max PM2.5 this year?" | 0.0s | 89.2 µg/m³ |

---

## Quick Start

Step 1: Install dependencies
```bash
pip install -r requirements.txt
```
Step 2: Pull the local LLM using Ollama
```bash
ollama pull llama3.2:3b
```
Step 3: Place the PM2.5 report PDF:  
[HNDDS242_011 Report.pdf](https://github.com/user-attachments/files/24811575/HNDDS242_011.Report.pdf)

Step 4: Run the notebook:
```bash
jupyter notebook pm25_rag_complete.ipynb
```






