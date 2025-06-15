# Language Identifier – Character-level N-gram Approach

This project implements a fast and interpretable language identification system using character-level trigram profiles. The approach is based on the classic method by Cavnar & Trenkle and supports 13 major world languages.

## Table of Contents
- [Project Overview](#project-overview)
- [Supported Languages](#supported-languages)
- [How It Works](#how-it-works)
- [How to Run](#how-to-run)
- [Results](#results)
- [Limitations and Future Work](#limitations-and-future-work)
- [References](#references)

---

## Project Overview

This project provides an implementation of a simple but effective language identification model. It builds a frequency profile of character trigrams for each supported language, then predicts the language of new text by comparing trigram patterns.

- **Approach:** N-gram (trigram) language profiles
- **Dataset:** [Tatoeba Project](https://tatoeba.org/) sentences (balanced sample)
- **Accuracy:** 96.8% on a balanced test set (13 languages)

---

## Supported Languages

- English (`en`)
- German (`de`)
- French (`fr`)
- Spanish (`es`)
- Italian (`it`)
- Portuguese (`pt`)
- Russian (`ru`)
- Polish (`pl`)
- Finnish (`fi`)
- Turkish (`tr`)
- Chinese (`zh`)
- Japanese (`ja`)
- Korean (`ko`)

---

## How It Works

1. **Data Preprocessing:** Sentences are lowercased, cleaned, and mapped to standardized language codes.
2. **Trigram Profile Construction:** Character-level trigrams are extracted from each sentence, with boundary markers added. The top 300 most frequent trigrams form the profile for each language.
3. **Classification:** Given new input text, a trigram profile is built and compared to all language profiles using rank-order distance. The closest match is predicted as the language.
4. **Evaluation:** The model is tested on unseen sentences, achieving high accuracy and robust results across scripts.

---

## How to Run

1. **Clone this repository:**
    ```bash
    git clone https://github.com/RaminMod/language-identifier.git
    cd language-identifier
    ```

2. **Install dependencies:**
    (You’ll need to create a `requirements.txt` as explained in the next step.)
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the code:**
    - Open the notebook in Jupyter:
        ```bash
        jupyter notebook UKP__Language_Identifier(20250530145333_ModaresiRamin).ipynb
        ```
    - Follow the notebook cells for data processing, training, and evaluation.

4. **Data:**
    - The code downloads and processes data automatically from the [Tatoeba Project](https://tatoeba.org).
    - You can adjust the number of languages or sentences in the notebook settings.

---

## Results

- **Overall Accuracy:** 96.8%
- **High precision and recall** for most languages
- **Strong on distinct scripts** (Chinese, Japanese, Russian, Korean)
- **Some confusion** between similar European languages (e.g., Spanish & Portuguese)

---

## Limitations and Future Work

- Struggles with very short or mixed-language texts
- Designed for general sentences, not specialized vocabulary
- Future work: extend to more languages, improve performance on short or domain-specific texts, explore combining with other features or neural models

---

## References

- Cavnar, W. B., & Trenkle, J. M. (1994). N-gram-based text categorization. Proceedings of SDAIR-94.
- Tatoeba Project: https://tatoeba.org

---

*Project by Ramin Modaresi, 2025.*
