# Digital Infrastructure — Natural Language Processing (NLP) Pipeline

### Programme Overview

This is a weekly community programme where parents and children come together to relax, connect, and play in a supportive environment. Sessions are designed to support child development and promote emotional and mental wellbeing for both children and their parents/caregivers.

Each week, I write summary of the session in a word document. This pipeline turns that growing archive of unstructured summaries into a structured, analysable dataset — enabling the programme to monitor its own impact systematically rather than anecdotally.

### Why Natural Language Processing?

The core question driving this work is whether the organisation is consistently meeting its thematic and developmental objectives across sessions, coordinators, and time. NLP was chosen because the underlying data — weekly session summaries — is unstructured by nature, and manual review does not scale as the number of sessions grows.

This pipeline was designed and built to serve two concurrent purposes:
1. **Programme intelligence** — providing evidence-based insight to inform resource allocation and programme management decisions.
2. **Applied NLP capability** — demonstrating a full production-grade text analytics lifecycle, from raw data ingestion through to exportable datasets and publication-quality visual reporting.

### What the Pipeline Does

The system spans the full text-analysis stack:

- **Preprocessing & normalisation** — cleaning, tokenisation, and lemmatisation of raw coordinator summaries
- **Semantic keyword extraction** — KeyBERT-based extraction to surface the most representative terms and phrases per session
- **Unsupervised topic discovery** — LDA topic modelling to identify recurring themes across sessions without predefined categories
- **Sentiment analysis** — rolling sentiment tracking to monitor emotional tone over time
- **Linguistic structure analysis** — POS tagging and n-gram analysis to characterise how sessions are described
- **Theme scoring system** — a custom scoring layer that maps extracted themes back to the programme's core developmental objectives
- **Master analytical table** — a per-session table joining all analytical outputs on a common date key, forming a single source of truth for reporting
- **Interactive reporting dashboard** — a six-panel interactive Plotly dashboard for exploring trends across themes, sentiment, and time


### Technical Stack
| Layer | Tooling |
|---|---|
| Data source | Coordinator-authored session summaries (Word/Google Docs) |
| Data engineering & NLP | Python (Jupyter Notebook) — spaCy/NLTK, KeyBERT, Gensim (LDA), scikit-learn |
| Visualisation & reporting | Plotly (interactive dashboard), CSV export for downstream reporting |

### Impact

- **Evidence-based decision-making** — gives programme managers objective, data-driven insight for resource allocation and programme design, replacing manual, subjective review of session notes.
- **Organisational knowledge hub** — creates a structured, searchable record of programme themes over time, rather than summaries sitting unused in a document archive.
- **Grant and funder reporting** — produces a reusable, grant-ready analytical output that strengthens funding applications and impact reporting.

### Data Protection and Privacy

Names are intentionally excluded from processing outputs to keep the focus strictly on key programme themes and activities.

### Community File & Input Format

The community log file is not included in this repository. If you need assistance with or need to process session summary files, please format your data using a Word document (.docx) or a Google Doc. Instructions for logging events: Write the date at the beginning of each week before summarising the events for each day.

### Key Summary of Processing Steps

1. Document Loading: Reads text from structured Word documents (.docx).
2. Text Cleaning & Anonymisation: Converts text to lowercase, removes punctuation/stopwords, and filters out common personal names to maintain privacy.
3. NLP Analysis: Performs lemmatisation, n-gram analysis (bigrams and trigrams), word frequency distribution, and topic modeling (LDA).

### Author's Note

This pipeline was independently designed, developed, and delivered on a voluntary basis as Data Science & Programme Support Lead for the programme, covering the full lifecycle from raw text ingestion to the final analytical dashboard.
