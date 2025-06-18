
# Product Feature Extraction from E-Commerce Images

Extract product features such as weight, height, and other details from product page images (e.g., Amazon) using three different pipelines: PaddleOCR with regex, MiniCPM VQA with regex, and Donut VQA with regex


## Contents

 - [Overview](#Overview)
 - [Features](#Features)
 - [Pipelines](#Pipelines)
 - [Installation](#Installation)
 - [Project Structure](#project-structure)
 - [Limitations](#Limitations)

## Overview

This project automates the extraction of structured product specifications from e-commerce product page images. It leverages state-of-the-art OCR and VQA models, combined with regular expressions, to identify and extract key product attributes such as weight, height, and more
## Features

- Extracts product specifications (weight, height, etc.) from images.

- Supports images from e-commerce sites like Amazon.

- Three extraction pipelines:

    - PaddleOCR + Regex

    - MiniCPM VQA + Regex

    - Donut VQA + Regex

## Pipelines

| Pipeline  | Description |
| ------------- | ------------- |
| PaddleOCR + Regex  | Uses PaddleOCR for text extraction, then applies regex to parse specifications.  |
| MiniCPM VQA + Regex  | Uses MiniCPM VQA for visual question answering, then regex for parsing.  |
| Donut VQA + Regex | Uses Donut VQA for document understanding, then regex for parsing. |

## Installation

1. Clone the repository:

```bash
git clone https://github.com/sharma-aryan-1/prod-img-feat-extract.git
cd prod-img-feat-extract
```

2. Install dependencies

```bash
pip install -r requirements.txt
```




## Project Structure
```text
prod-img-feat-extract/
│
├── pipelines/
│   ├── paddleocr_pipeline.py
│   ├── minicpm_pipeline.py
│   └── donut_pipeline.py
├── requirements.txt
└── README.md
```

## Limitations

1. While this study provides a good solution for extracting the dimensions and minute specifications from each product page, it fails to extract non-generalized, specific descriptions of the products, which is a challenging task and is not explored in our study. This can be a problem when a downstream task requires additional information, and the model must be retuned. This may involve exploring alternative approaches or fine-tuning specific steps of our pipelines.
2. While our models support multiple languages, we only employ them on English-based or numeric-only product images. Additionally, evaluation has only been carried out for English. The performance may vary when applying the model to images encompassing multiple languages or any uncommon, domain-specific abbreviations or terminologies.
