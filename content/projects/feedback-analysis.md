---
title: feedback-analysis
slug: feedback-analysis
description: Extract text snippets that characterize sentiment in customer feedback.
tags: ["PyTorch", "transformers", "GCP"]
githubUrl: https://github.com/aniruddhs24/feedback-analysis
timestamp: 2021-09-01
featured: false
---

## Overview

Feedback Analysis is a tool that extracts rationales from textual feedback that directly reflects user sentiment.

The project was inspired by the paper [Learning to Faithfully Rationalize by Construction](https://aclanthology.org/2020.acl-main.409/), which I originally tried to reimplement in an NLP reading group. While working on it, I realized a much more practical use case: **student feedback**.

In my high school, clubs often received 100–150 written feedback forms. Club officers had to read every response in full, even though much of the text was repetitive or low-signal. This tool helps surface the key phrases that actually express sentiment.

I built a lightweight Vue.js frontend where users can upload feedback forms and receive concise, sentiment-focused summaries.

## How It Works

The pipeline has three main components: a Feature Scorer, an Extractor, and a Predictor.

### Feature Scorer

<img src="https://github.com/AniruddhS24/feedback-analysis/blob/master/images/suppmodelimg.png?raw=true">

A pretrained BERT model is fine-tuned on binary sentiment classification. The goal isn't perfect sentiment accuracy, but rather to identify which parts of the text strongly influence sentiment.

To do this, the model uses attention scores from the [CLS] token as a proxy for token importance. These scores act as a signal for which words or phrases matter most.

### Extractor

<img src="https://github.com/AniruddhS24/feedback-analysis/blob/master/images/extmodelimg.png?raw=true">

The extractor converts token importance scores into short, readable text spans called rationales.

I experimented with several approaches:

- **Heuristic extractor**: Selects the top contiguous token spans with the highest attention scores.\
- **BiLSTM extractor**: Tags tokens to include them in rationales or not
- **BiLSTM + CRF**: Adds a CRF layer to encourage coherent selections.\

The CRF-based model produces the most consistent and readable rationales.

### Predictor

<img src="https://github.com/AniruddhS24/feedback-analysis/blob/master/images/predimg.png?raw=true">

Each extracted rationale is then classified for sentiment.

Models explored:

- **Deep Averaging Network (DAN)**: Fast and lightweight, worked surprisingly well.
- **BERT-based predictor**: More accurate but slower, trained on SST-5 for fine-grained sentiment.

## Technical Details

- Built in Python with PyTorch, Numpy, and Huggingface
- Trained models with GPU instances on GCP
