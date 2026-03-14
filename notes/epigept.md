---
layout: page
title: "EpiGePT: a pretrained transformer-based language model for context-specific human epigenomics"
permalink: /notes/epigept/
---

# EpiGePT: a pretrained transformer-based language model for context-specific human epigenomics

**Paper:** https://doi.org/10.1186/s13059-024-03449-7  
**Field:** Genomics · Deep Learning · Epigenomics

---

## Big picture: what problem does the paper solve?

- Understanding regulatory information in the non-coding genome is still a major challenge.
- Gene regulation depends strongly on cellular context and chromatin structure.
  - Regulatory elements such as enhancers and silencers interact with genes through 3D chromatin contacts, and their activity varies across cell types.
- Existing genomic deep learning models have two major limitations:
  - They rely mainly on DNA sequence alone.
  - They cannot generalize well to unseen cellular contexts.

## Core idea

The paper introduces **EpiGePT**, a transformer-based genomic language model that predicts epigenomic signals using DNA sequence, transcription factor activity, and chromatin interaction information.

- Main innovation:
  - incorporate transcription factor (TF) profiles to represent cellular context
  - incorporate 3D chromatin interaction data during training
- Goal: predict regulatory features across genomic regions and cell types.

## Data

The model is trained on large-scale epigenomic datasets, mainly from ENCODE.

- Training signals include:
  - DNase-seq (chromatin accessibility)
  - histone modification signals
  - TF binding signals
  - chromatin interaction data (HiChIP)

A key design decision: training examples are defined as **(genomic region + cellular context)** instead of just genomic region.

## Model

The model contains four main modules.

- Sequence module: processes long DNA sequences (~128 kb), uses convolution layers to extract sequence features.
- TF module: encodes cellular context using expression levels of transcription factors.
- Transformer module: uses self-attention to learn relationships across genomic positions.
- Prediction module: predicts multiple epigenomic signals simultaneously.

## Results

- Improved prediction of epigenomic signals
- Predicts long-range regulatory interactions
- Transformer attention scores can identify enhancer–promoter pairs, silencer–promoter pairs, chromatin loops
- Infers regulatory transcription factor networks
- Predicts effects of genetic variants

## Conclusions

EpiGePT is a pretrained transformer model for epigenomics that integrates DNA sequence, transcription factor context, and 3D chromatin interactions.
