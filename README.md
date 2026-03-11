## AI Relevance Workshop

Hands‑on materials to compare embedding models (BM25, BERT, SBERT, E5, cross‑encoder reranker) on retrieval tasks using a single Jupyter notebook.

### Setup
- **Python**: 3.9+ recommended.
- (Optional) Create and activate a virtualenv or conda env.
- **Install dependencies:** in a fresh environment, run the “Install dependencies” cell in the notebook once (`%pip install ...`). Restart the kernel afterward if imports still fail.

### Running the workshop
1. Start Jupyter Notebook or JupyterLab in this folder.
2. Open `Embeddings.ipynb`.
3. Run cells from top to bottom:
   - Load models (BERT, all‑MiniLM, E5, cross‑encoder, BM25).
   - Encode queries/passages and build the BM25 index.
   - Compute similarities, ranking metrics, and timing.
   - Render the `retrieval_performance_comparison.png` visualization.

### Notebook structure
- **Intro & install** – Workshop goal, model list, optional dependency cell.
- **Model code** – `ModelManager` class and helpers (BERT, SBERT, E5, cross‑encoder, BM25); config, encoding, and BM25 index builder.
- **Data** – Curated query–passage sets (10 queries, each with one relevant and three distractor passages).
- **Load & encode** – Set device, load all models, encode queries/passages, build BM25 index.
- **Similarities** – Compute scores for every query–passage pair for every model.
- **Metrics** – Top‑1 / Top‑3 accuracy and nDCG@4 per model.
- **Charts** – Bar charts of metrics and encoding time; saves `retrieval_performance_comparison.png`.
- **Single-query view** – Similarity heatmap for one chosen query across models.
- **Rank view** – Where the relevant passage ranks per model for each query (table/visual).
- **Model behavior**: how BM25, BERT, SBERT, E5, and a cross‑encoder reranker rank relevant vs. distractor passages.
- **Metrics**: Top‑1 / Top‑3 accuracy and nDCG@4 across a small set of curated query–passage pairs.
- **Latency vs. quality trade‑offs**: encoding and reranking time per model.

### Repository contents
- `Embeddings.ipynb` – main workshop notebook.
