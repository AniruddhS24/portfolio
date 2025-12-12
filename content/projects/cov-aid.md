---
title: cov-aid
slug: cov-aid
description: COVID-19 case projection with deep learning and recurrent neural networks.
tags: ["Python"]
githubUrl: https://github.com/aniruddhs24/cov-aid
timestamp: 2021-06-01
featured: false
---

## Overview

COV-(AI)D forecasts COVID-19 cases in U.S. states using historical case data plus **human mobility trends** from Apple Maps. The idea was that people moving around more meant more transmission risk.

## How It Works

I noticed that case spikes seemed to follow increases in human movement. So instead of just training on past COVID numbers like most models, I fed the LSTM both case counts (from Johns Hopkins) and daily mobility data (from Apple Maps routing requests).

Used a 3-layer LSTM with 30-day sequences. The model hit an MAE of around 600 cases on 30-day forecasts, which beat traditional time-series methods like ARIMA.

## Technical Details

- Python + PyTorch
- 3-layer LSTM for multivariate time-series
- Trained on COVID cases + Apple Maps mobility data
