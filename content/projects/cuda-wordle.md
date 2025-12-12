---
title: cuda-wordle
slug: cuda-wordle
description: CUDA-Optimized Wordle solver using parallel computing for blazing-fast word elimination.
tags: ["C++", "CUDA"]
githubUrl: https://github.com/aniruddhs24/cuda-wordle
timestamp: 2023-05-05
featured: true
---

## Overview

My friend and I built a high-performance Wordle solver using NVIDIA
GPUs and parallel processing techniques. Our solution takes an information-theoretic approach to evaluating guesses, where we compute the Shannon entropy for each word in a preset dictionary. We build CUDA kernels to concurrently process data and compute the expected information for each guess. With over 11k words to search, we measured a (12x) speedup over a serial implementation of the algorithm.

You can read more
[here](https://github.com/AniruddhS24/cuda-wordle/blob/main/CUDA_Wordle.pdf).

## Technical Details

- Implements parallel word elimination using CUDA kernels
- Optimized for GPU memory access patterns
  - Coalesced memory access
  - Caching highly accessed word patterns in shared memory
- Ran experiments on an NVIDIA Quadro RTX 6000
