# From Cliché to Canon: Patterns, Tradition, and Innovation in 2000 Titles of Russian Novels (1763-1917)

This repository contains code and data for a computational study of 2,000+ titles of Russian novels published in the Russian Empire between 1763 and 1917.

## Research questions

- How did the formal structure of novel titles evolve over 150 years?
- Do canonical titles differ from non-canonical ones in measurable ways?
- What semantic clusters and patterns emerge across the corpus?

## Methods

**Formal analysis** — POS-tagging to identify structural patterns (e.g. `NOUN`, `ADJF NOUN`, `NOUN NOUN`) and track their evolution over time. Key finding: short nominal constructions rose from 19.7% to 51.8% after 1830 (χ²=26.92, p<0.0001).

**Semantic analysis** — sentence embeddings via [`sberbank-ai/sbert_large_nlu_ru`](https://huggingface.co/sberbank-ai/sbert_large_nlu_ru). Used to measure pairwise similarity, novelty (cosine distance from the running mean of preceding titles), and inter-period drift.

## Data

| File | Description |
|------|-------------|
| `novels_titles_raw.csv` | Raw dataset |
| `data/novels_titles_processed.csv` | Filtered and normalized dataset |
| `data/sberbank-ai-sbert_large_nlu_ru_mp.pickle` | Precomputed title embeddings |
| `data/sberbank-ai-sbert_large_nlu_ru_mp.csv` | Pairwise cosine similarity matrix (2029 × 2029) |

## Key results

- Canonical titles are significantly shorter than non-canonical ones (t=−6.51, p<0.0001)
- Canonical and non-canonical titles do not differ in semantic novelty (Mann–Whitney U=81685, p=0.36)
- The 1830s mark a structural turning point: long descriptive titles give way to short nominal ones
