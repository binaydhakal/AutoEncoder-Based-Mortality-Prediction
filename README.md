# Autoencoder-Based Mortality Prediction from Multi-Compartment Microbiome Data

Code for the peer-reviewed study on predicting patient mortality by learning joint representations of microbiome data across multiple body-site compartments, fused with clinical parameters.

## Publication

> **Integrating multi-compartment microbiome data with clinical parameters enhances mortality prediction using autoencoder**
> Dhakal B, Savarapu LSK, Sayed K
> *Journal of Microbiological Methods*, Vol. 238, 107267 — November 2025

[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.mimet.2025.107267-c9a24b?style=flat-square)](https://doi.org/10.1016/j.mimet.2025.107267)
[![PubMed](https://img.shields.io/badge/PubMed-40972768-326599?style=flat-square)](https://pubmed.ncbi.nlm.nih.gov/40972768/)

## Approach

Microbiome data is high-dimensional and sparse, and samples drawn from different body-site compartments carry complementary signal. This work compresses each compartment into a dense latent representation with an autoencoder, then combines those representations with clinical parameters to predict mortality — outperforming models built on clinical parameters or any single compartment alone.

| Stage | What happens |
|---|---|
| Preprocessing | Filtering and normalization of sparse taxa abundance data per compartment |
| Representation learning | Autoencoder compresses each compartment into a low-dimensional latent space |
| Fusion | Learned embeddings concatenated with clinical parameters |
| Prediction | Downstream classifier predicts mortality outcome |
| Evaluation | Compared against clinical-only and single-compartment baselines |

## Contents

- `AutoencoderBasedAnalysis.ipynb` — full pipeline: preprocessing, autoencoder training, fusion, evaluation

## Running it

```bash
pip install numpy pandas scikit-learn tensorflow matplotlib seaborn
jupyter notebook AutoencoderBasedAnalysis.ipynb
```

## Related work

Exploratory analysis of the lung compartment — abundance, beta diversity, and taxa relevance — lives in [BaselineLungAnalysis-MicrobiomeDA](https://github.com/binaydhakal/BaselineLungAnalysis-MicrobiomeDA).

## Citation

```bibtex
@article{dhakal2025microbiome,
  title   = {Integrating multi-compartment microbiome data with clinical parameters enhances mortality prediction using autoencoder},
  author  = {Dhakal, Binaya and Savarapu, Lakshmi Sai Kishore and Sayed, Khaled},
  journal = {Journal of Microbiological Methods},
  volume  = {238},
  pages   = {107267},
  year    = {2025},
  doi     = {10.1016/j.mimet.2025.107267}
}
```

---

Research conducted as a Research Assistant at the University of New Haven.
