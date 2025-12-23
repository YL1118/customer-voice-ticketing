# customer-voice-ticketing
The objective of this project is to automatically transform a large volume of customer feedback into actionable work orders, thereby reducing manual triage costs and shortening response times.

# Customer Voice → Auto Ticketing (Clustering + Classification)

## Overview
This project turns large volumes of customer feedback (complaints/reviews) into actionable support tickets.
It includes:
1) Topic discovery via clustering (VOC themes)
2) Stable issue classification for routing
3) Ticket generation (department, priority, summary) for workflow automation

## Motivation
Companies receive massive customer feedback daily. Manual triage is time-consuming and costly.
This project aims to automate issue categorization and ticket creation, and provide insights for process improvement.

## Problem Statement
Given a piece of customer feedback text, automatically:
- assign an issue type (e.g., billing, login, delivery, service attitude)
- route to a responsible department
- estimate priority
- generate a short ticket summary and key evidence

## Dataset
- Source: (to be filled)
- Size: (to be filled)
- Fields used: text, label (if any), timestamp/rating (optional)

> Note: Raw data is not committed to this repository. See `data/` section.

## Approach
### 1) Preprocessing
- cleaning, normalization, tokenization (optional)

### 2) Clustering (Theme Discovery)
- embeddings + KMeans / BERTopic
- cluster interpretation: representative samples + top keywords
- human-in-the-loop naming to define `issue_type`

### 3) Classification (Stable Routing)
- train a supervised classifier on labeled issue types
- evaluate with macro-F1, confusion matrix

### 4) Ticket Generation
Ticket schema (example):
- ticket_id
- issue_type
- department
- priority
- summary
- evidence
- confidence

## Results (WIP)
- Baseline: (to be filled)
- Clustering quality: (to be filled)
- Classification: (to be filled)

## Repository Structure
- `notebooks/`: experiments and analysis
- `src/`: reusable pipeline code
- `reports/`: business insights and analysis writeups
- `assets/`: figures for README/report

## How to Run
### Setup
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
