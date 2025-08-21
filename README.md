# Data Visualizations with Python — Exercises 1.3–1.7

**Updated:** 2025-08-21 (UTC)  
This repository collects the notebooks for Exercises **1.3 → 1.7**, progressing from environment setup to scraping, text mining, NLP, and network visualization.

## Contents (Notebooks)
- **1.3 Virtual Environments in Python.ipynb** — Create and manage isolated conda environments, install packages, and register the kernel for Jupyter.
- **1.4 Accessing Web Data with Data Scraping.ipynb** — Scrape web content (e.g., “Key Events of the 20th Century”) using Requests/BeautifulSoup or Selenium; persist raw and cleaned data.
- **1.5 Text Mining.ipynb** — Clean and tokenize text, remove stop words, POS‑tag, compute frequencies, and generate exploratory plots.
- **1.6 Intro to NLP and Network Analysis.ipynb** — Run NER to extract entities (countries/people), derive relationships and export an **edges** CSV for network building.
- **1.7 Creating Network Visualizations.ipynb** — Build a NetworkX graph, create static & interactive (PyVis) visualizations, detect communities (Leiden with Louvain fallback), and compute centralities (degree, closeness, betweenness).

## Suggested Folder Structure
```
.
├─ data/
│  ├─ raw/                     # scraped HTML/JSON assets
│  ├─ interim/                 # partially processed files
│  └─ processed/               # cleaned CSVs (e.g., tokens, edges)
├─ outputs/
│  ├─ figures/                 # PNG charts
│  ├─ tables/                  # CSV exports
│  └─ html/                    # PyVis HTML graphs
├─ notebooks/
│  ├─ 1.3 Virtual Environments in Python.ipynb
│  ├─ 1.4 Accessing Web Data with Data Scraping.ipynb
│  ├─ 1.5 Text Mining.ipynb
│  ├─ 1.6 Intro to NLP and Network Analysis.ipynb
│  └─ 1.7 Creating Network Visualizations.ipynb
└─ requirements.txt
```

## Quick Start (conda)
```bash
conda create -n 20th_century python=3.10 -y
conda activate 20th_century

# Core scientific + viz + scraping + NLP + networks
conda install -c conda-forge -y   pandas numpy matplotlib networkx pyvis beautifulsoup4 requests lxml   spacy scikit-learn nltk cdlib python-igraph leidenalg python-louvain jupyterlab

# Optional: Selenium (if used in 1.4 for dynamic pages)
conda install -c conda-forge -y selenium

# spaCy English model
python -m spacy download en_core_web_sm
```

## Workflow Summary
1. **1.3** — Create your environment; ensure Jupyter sees the kernel. Optionally export `requirements.txt` or `environment.yml`.
2. **1.4** — Scrape the target page(s). Save raw HTML to `data/raw/` and a cleaned dataset (CSV/JSON) to `data/processed/`.
3. **1.5** — Perform text mining (tokenization, stop words, POS). Save artifacts (e.g., `tokens.csv`, `top_terms.png`) to `outputs/`.
4. **1.6** — Run NER and extract relationships (e.g., co‑mentions). Export an edges CSV like `country_relationships.csv` for network analysis.
5. **1.7** — Build the network:  
   - Static plot (**NetworkX + matplotlib**) → `outputs/figures/static_network.png`  
   - Interactive **PyVis** HTML → `outputs/html/countries_network.html`  
   - Community detection (Leiden → Louvain fallback) → `outputs/html/countries_communities.html`  
   - Centralities (degree, closeness, betweenness) → PNG charts + CSVs in `outputs/`

## Common Outputs
- `outputs/figures/static_network.png`  
- `outputs/html/countries_network.html`  
- `outputs/html/countries_communities.html`  
- `outputs/tables/degree_centrality.csv` / `outputs/figures/degree_centrality.png`  
- `outputs/tables/closeness_centrality.csv` / `outputs/figures/closeness_centrality.png`  
- `outputs/tables/betweenness_centrality.csv` / `outputs/figures/betweenness_centrality.png`  

## License & Acknowledgements
- Typical licenses: MIT/Apache‑2.0 (add a `LICENSE` file as appropriate).  
- Built with: pandas, matplotlib, NetworkX, PyVis, spaCy, NLTK, CDlib, python‑igraph, leidenalg, python‑louvain.
