# NeurIPS 2026: find your institution

Accepted NeurIPS 2026 main-track papers by institution, with each institution's research-area mix.

**Live page:** {{SITE_URL}}

![NeurIPS 2026 poster](assets/poster.png)

## What's here

- `index.html`: the search page (static, no build step, works on GitHub Pages).
- `data.js`: the data the page loads. Institution-level totals only.
- `neurips2026_institutions.csv`: the same table as a CSV.
- `assets/poster.png`: the summary poster.

## Data

| Column | Meaning |
|---|---|
| `rank` | Rank by paper count. Institutions with the same count share a rank. |
| `institution` | Normalized institution name. |
| `papers` | Accepted main-track papers with at least one author from this institution. |
| `pct_of_papers` | `papers` as a share of all 5,629 main-track papers. Shares add up to more than 100%. |
| `fractional_papers` | Each paper split equally across its authors, then across each author's institutions. Adds up to 5,629. |
| `country` | Country code, for institutions in the hand-checked table. Blank otherwise. |
| `sector` | `academia` or `industry`. |
| Area columns | Papers per research area. Each paper is in exactly one area. |

## How it was made

- **Source.** The official neurips.cc program data for NeurIPS 2026, which lists each author's institution as written on their OpenReview profile. Snapshot taken 2026-10-17. Main track only.
- **Names.** Institution strings are normalized with a hand-checked table of about 380 institutions plus rules for sub-units ("School of CS, X University" counts as X University). Google includes DeepMind. Meta includes FAIR. All Chinese Academy of Sciences institutes are merged. HKUST and HKUST (Guangzhou) are separate. Less common names are grouped by exact spelling, so a small institution can appear under more than one name.
- **Research areas.** Not official tags. Titles and abstracts were embedded with `BAAI/bge-small-en-v1.5`, clustered with k-means (k=14), and the clusters were merged and named into 12 areas from their top terms. Borders between neighbouring areas such as LLMs, LLM agents and multimodal are fuzzy. With only a few papers, an institution's mix is noisy.
- **Sector.** Companies and corporate labs are industry. Universities and public or non-profit institutes such as CAS, Max Planck, RIKEN, Shanghai AI Lab and Mila are academia.
- **Privacy.** Only institution-level totals are published. No author names and no per-paper records are included.

## Corrections

Found a wrong or split institution? Please [open an issue]({{REPO_URL}}/issues/new) with the institution name and what it should be.

## Credit

Made by Jueun Kim (POSTECH) · [@jueun_kim_](https://x.com/jueun_kim_). Format inspired by Pierre-Alexandre Balland's NeurIPS 2025 institution treemap.
