# 🐦 Historic to FAIR: Extraction & Matching of Historical Biodiversity Terms

This repository contains the code and workflow used in the paper:  

**Fillies, J., Teich, M., Karam, N., Paschke, A., & Rehbein, M. (2024).  
*Historic to FAIR: Leveraging LLMs for Historic Term Identification and Standardization*. Datenbank-Spektrum.**  

The notebook `Historic_extraction_and_matchingmatching.ipynb` demonstrates how **large language models (LLMs)** can be applied to identify and align **historical species names** (common names) with their **modern equivalents** to support **FAIR data principles** (Findable, Accessible, Interoperable, Reusable).  
Data and annotation results will be provided as soon as the dataset is published.
---

## 📖 Background

Biodiversity records from historical sources, such as the 19th-century *Oberamtsbeschreibungen* from Württemberg (1824–1886), provide invaluable data on regional fauna. However, historical biodiversity terms present several challenges:

1. **Spelling variations** (e.g., *Thurmfalke* → *Turmfalke*)  
2. **Emergence of new terms** (e.g., *wildes Schwein* → *Wildschwein*)  
3. **Semantic shifts** between broad and specific terms (e.g., *Holzwespen* → specific species)  
4. **Generalization** of historically specific names (e.g., *Schwarzamsel* → *Amsel*)  
5. **Renaming and dialectal variation** (e.g., *Steißfuß* → *Haubentaucher*)  

The notebook operationalizes the methods described in the paper to **extract, detect, and match** these historical terms using multiple LLMs (GPT-4o, LLaMA3-405B, Mistral-8B, Qwen3-30B-A3B).

---

## Workflow in the Notebook

The notebook is structured around two main phases, mirroring the experiments in the paper:

### 1. **Entity Recognition**
- Identify historical **common names** and **scientific names** from text snippets.
- Evaluate recognition accuracy with and without additional context.
-> Achieved high precision (GPT-4o: 92% for common names, 98% for scientific names).

### 2. **Historical Alignment**
- Map historical terms to **modern equivalents**.  
- Address the five linguistic challenges listed above.  
- Compare performance across different LLMs.  
-> GPT-4o consistently outperformed other models in nuanced contextual alignment.


## Getting Started
### Data
- for data access please consult Maximilian Teich @ Chair of Computational Humanities, University of Passau, Passau, Germany.
- once the dataset is published we will provide a link here

### Requirements
- Python 3.9+  
- Jupyter Notebook  
- OpenAI API (for GPT-4o) and BLABLADOR account with API key for other models  
- Libraries: `pandas`, `numpy`, `openai`, `transformers`

### Run the Notebook
```bash
jupyter notebook Historic_extraction_and_matchingmatching.ipynb
```

You will need API access to LLMs (e.g., GPT-4o) to reproduce the results.

---

## Results Summary
- **Entity Recognition**: GPT-4o reached 92% (common names) and 98% (scientific names).  
- **Alignment**: GPT-4o solved 4/5 challenges with near-perfect accuracy; other models underperformed, especially on semantic generalization.  
- **Key Insight**: LLMs can substantially reduce manual effort in standardizing biodiversity records, though a human-in-the-loop remains essential.  

---

## FAIR Data Connection
This project supports **FAIR biodiversity data integration** by:
- Making **historic biodiversity records interoperable** with modern taxonomies.  
- Enhancing **findability and accessibility** of species across centuries.  
- Contributing to the **BiodivPortal ontology repository**, enabling semantic annotation of biodiversity data over time.  

---

## Citation
If you use this code, please cite:

> Fillies, J., Teich, M., Karam, N., Paschke, A., & Rehbein, M. (2024).  
> *Historic to FAIR: Leveraging LLMs for Historic Term Identification and Standardization*. tbd  

---

## Future Directions
- Expand to larger and multilingual historical datasets.  
- Test additional open-source LLMs with fine-tuning.  
- Integrate retrieval-augmented generation (RAG) for taxonomic lookups.  
