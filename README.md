# PCSK9-analysis

Principal component analysis (PCA) of molecular dynamics simulations of the PCSK9–LDLR complex and of PCSK9 missense variants.

## Background

Proprotein convertase subtilisin/kexin type 9 (PCSK9) binds the low-density lipoprotein receptor (LDLR) and induces its degradation. Gain-of-function (GOF) PCSK9 variants increase LDLR degradation and cause familial hypercholesterolemia (FH).

This analysis supports a study of PCSK9 missense variants identified by exon-targeted sequencing in 113 Brazilian FH patients (annotated with ANNOVAR). Eight variants in the pro-domain (p.E32K, p.E57K), catalytic domain (p.R237W, p.P279T, p.A443T) and C-terminal histidine-cysteine-rich (CHR) domain (p.R469W, p.Q619P, p.R680Q) were modeled. MD showed that the catalytic- and CHR-domain variants lie more than 22.5 Å from the LDLR-EGF-A interface, and that p.A443T, p.R469W and p.Q619P perturb internal interactions, mainly with the pro-domain. In cells, the GOF variants p.E32K and p.R469W reduced surface LDLR by less than 11%.

## Contents

| File | Description |
|---|---|
| `PCA-PCSK9-gmf-maestro.ipynb` | PCA conformer plots for the PCSK9 pro-domain (chain P), catalytic + CHR domains (chain A) and LDLR-EGF-A (chain E) |

## Method

Backbone atoms of each MD frame were extracted and aligned with `trj_selection_dl.py` and
`trj_align.py` (Schrödinger Suite 2019v.4). Individual simulations were merged into a single
trajectory and CMS file with `trj_merge.py`, and principal components were computed with
`trj_essential_dynamics.py`. PCA conformer plots (PC1 × PC2, states and motions) are
generated in the notebook with Matplotlib, Seaborn, NumPy and pandas.

## Requirements

Python 3 with Jupyter and the libraries listed below. Trajectories and
Schrödinger Suite outputs are **not** included in this repository.

```bash
pip install jupyter numpy pandas matplotlib seaborn
```

## Author

**Glaucio Monteiro Ferreira** — Research Associate, Institute of Chemistry, University of São Paulo (IQ-USP) · [LIBNM · Ferreira Lab](https://ferreiralab.com.br) · [ORCID](https://orcid.org/0000-0002-1952-9428) · [FAPESP profile](https://bv.fapesp.br/pt/pesquisador/703612/glaucio-monteiro-ferreira/) · [gmf@usp.br](mailto:gmf@usp.br)
