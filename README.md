# Predicting Patient Drug Ratings from Reviews

Deep learning + generative AI approach to multiclass rating prediction on the
[UCI ML Drug Review Dataset](https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29).

Master's mentorship assignment for Prof. Kobi Gal.
**Author:** Matias Guernik (207695511)

Full write-up: [`Report.pdf`](Report.pdf).

## Notebooks

- **`01_data_cleaning.ipynb`** — Cleaning the raw dataset (missing/truncated conditions, HTML 
  entities, stray quote marks, single-character reviews).
- **`02_eda.ipynb`** — Exploratory analysis informing later modeling decisions (rating 
  distribution, review length, vocabulary size).
- **`03_multiclass_10.ipynb`** — 10-class rating prediction: fine-tuned DistilBERT (Model A) 
  and a frozen-DistilBERT + drugName/condition embeddings variant (Model B), plus explainability.
- **`04_multiclass_3.ipynb`** — 3-class rating prediction: re-bucketed baseline vs. a TextCNN 
  trained from scratch, plus explainability. Original file with full outputs (including 
  interactive SHAP plots), too large for GitHub's inline preview — download to view, or open 
  in Jupyter/Colab.
- **`04_multiclass_3_lite.ipynb`** — Same notebook, lightweight version that previews normally 
  on GitHub. Code and markdown are unchanged; SHAP outputs are replaced with links to the 
  static PNGs in `04_multiclass_3_plots/`.
- **`05_genai_prompting.ipynb`** — Generative AI component: Qwen3-4B summarization + sentiment 
  labeling, prompt engineering across 4 approaches, final Excel outputs.

## `04_multiclass_3_plots/`

The 3-class notebook's SHAP explainability plots, rendered as static PNGs from the original 
interactive HTML output, referenced by `04_multiclass_3_lite.ipynb`.

## ⚠️ A note before you try to run these

These notebooks were built under real Google Colab session constraints — the free GPU quota 
ran out multiple times mid-project, sessions disconnected, and parts had to be re-run out of 
order or patched around a lost runtime. As a result:

- **Cell execution order and numbering may not be fully sequential or reproducible top-to-bottom.**
- Some cells are re-runs, patches, or duplicates left over from recovering a dropped session — 
  not all of them are needed, and a few may be accidental leftovers.
- Some cells assume prior state (saved checkpoints, variables from an earlier session) that 
  won't exist if you run the notebook fresh.

**I'd strongly recommend not trying to re-run these end-to-end.** They're included for 
transparency and to show the actual work, not as a clean, reproducible pipeline. The report 
(`Report.pdf`) is the reliable source for methodology and results.

## Outputs

- `output_approach_b.xlsx`, `output_approach_d.xlsx` — the two GenAI output files (drug name, 
  condition, review, rating, predicted rating, generated summary, sentiment) for the two 
  best-performing prompting approaches, per the assignment brief.

## Data

Not included here — download from the 
[UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29) 
or the [Kaggle mirror](https://www.kaggle.com/datasets/jessicali9530/kuc-hackathon-winter-2018).
