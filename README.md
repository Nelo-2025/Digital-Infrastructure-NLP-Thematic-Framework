# Stay & Play Digital Infrastructure - NLP Analysis Pipeline for Community Session Summaries
---

## Table of Contents
1. Project overview
2. [Dataset]
3. -[Repository structure]
4. - [Pipeline architecture]
5. [Technical stack]
6. [Installation and setup]
7. [Running the notebook]
8. [Analysis modules - what each section does and why]
   - 8.1 Text extraction and preprocessing
   - 8.2 Named entity recognition and name removal
   - 8.3 Session builder -  the shared data contract
   - 8.4 Word frequency analysis
   - 8.5 Lemmatisation
   - 8.6 N-gram analysis
   - 8.7 Word cloud
   - 8.8 Part-of-speech tagging
   - 8.9 Sentiment analysis
   - 8.10 Programme theme scoring
   - 8.11 Keyword extraction- KeyBERT
   - 8.12 LDA topic modelling
   - 8.13 Per-session master table
   - 8.14 Time-series trend analysis
9. [Outputs and artefacts]
10. Key findings
11. Design decisions and data science rationale
12. limitation and future work
13. Social impact context
14. Author

### Project Overview
---

This digital infrastruture is collection of weekly session summary of community events from August-December 2025.  This is participants engagement data of parents and children that relax, connect, and play together in a supportive environment. The sessions support child development and promote emotional and mental well‑being for both children and their parents/caregivers.  The focus of this natural language processing (NLP)  is to assess whether the organisation is meeting its thematic focus. The code helps to ensure that each session fosters a safe, nurturing, and engaging atmosphere—especially for children and their parents.

This project transforms unstructured summaries into a structure, analytically rich dataset using an end-to-end NLP pipeline. The work spans every layer of text analysis: from preprocessing and lemmatisation through to unsupervised topic discovery, semantic keyword extraction, rolling sentiment trends, and a per-session master table that joins all analytical outputs on a common date key.

This pipeline wa designed and delivered ened-to-end by a single practitioner. It serves two concurrent purposes: providing evidence-based intelligence for programme management and demonstrating applied NLP capability across the full production lifecycle - raw data ingestion to exportable CSVs and publication quality charts.


2. **Dataset**

|property|Detail|
|--------|------|
|Source file|internal session log|
|format|microsoft word, paragraphs separated by DD/MM/YYYY date headings
|programme span|Aug - December 2025|
|Dated sessions|16 sessions groups(the unit of all per session analyses)
|Raw paragraphs| ~74 non-empty paragraphs across the document|
|Privacy| Coordinator names removed via spaCy NER + manual regex before any analysis|
|Participant data|NO child names, family identifiers, or sensitive personal data appear in the summaries|

**Required input:** stay_play.docx must be placed in the same category as stay_play.ipynb before running

3. **Repository Structure**
   
## Steps
Integrated an NLP text mining pipeline that ingest qualitative session summary logs.


"""
## LDA Topic Analysis Results

LDA analysis across N session summaries identified 5 recurring themes:

| # | Theme              | Sessions | % of total |
|---|--------------------|----------|------------|
| 1 | Emotional Wellbeing| 14       | 33%        |
| 2 | Child Development  | 10       | 24%        |
| 3 | Community Building | 8        | 19%        |
| 4 | Safe Environment   | 6        | 14%        |
| 5 | Creative Engagement| 4        | 10%        |

All 5 themes align directly with the programme's stated objectives,
providing evidence that delivery is consistently on-mission.
"""
