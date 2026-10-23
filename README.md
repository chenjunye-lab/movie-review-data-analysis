# The Making of Reflexive Cultural Confidence: History as Contemporary Critique in the Chinese Film Industry

## 1. Project Overview
This repository contains the data collection protocol and the data processing code for the paper: **"The Making of Reflexive Cultural Confidence: History as Contemporary Critique in the Chinese Film Industry"**. 
The materials are provided to ensure the reproducibility of our empirical analysis and to support the application for the Open Materials Badge.

## 2. Ethical Statement & Data Availability
**Full Dataset Restriction:** The complete raw dataset of movie reviews is **NOT** publicly shared in this repository. 
**Reason:** Douban's copyright notice explicitly prohibits any use, collection, or extraction of its public information without prior written permission. Publicly redistributing the full scraped dataset would constitute unauthorized dissemination. We strictly comply with this policy. 

**Alternative:** To balance transparency and ethical constraints, we provide a highly desensitized sample dataset (`sample_dataset.csv`, containing 15 rows) solely to demonstrate the data structure. 
Specifically:
*   User IDs and timestamps have been replaced with indices (e.g., `User 1`, `T01`).
*   Review titles have been fully anonymized (e.g., `Title 1`).
*   To prevent de-anonymization through search engines, the textual content has been intentionally truncated, and specific entity names have been replaced. This sample is solely for format demonstration, not for reproducing the full empirical results.

## 3. Data Collection Methodology (The "Script")
The data was collected using the visual web scraping tool **Octopus**. 
*Note: Since the local task cache was cleared after extraction, the original configuration file is unavailable. To ensure reproducibility, we provide the reconstructed extraction logic below:*

*   **Target:** Douban reviews for the film "The Lychee Road".
*   **Extracted Fields:** Author, Publish Time, Review Content, Upvotes, Downvotes, Reposts, and Review Title.
*   **Pagination Logic:** Auto-clicking the "Next Page" button sequentially.
*   **Post-processing:** Removed duplicates, dropped empty reviews.

## 4. Data Analysis Code (The Code)
The analysis was conducted using **Python**. The script (`analysis.py`) contains the full pipeline for data cleaning, natural language processing (NLP), and visualization. 

Key processing steps include:
*   **Data Cleaning:** Used the `re` (Regular Expression) library to remove punctuation, emojis, and special characters.
*   **Tokenization:** Utilized `jieba` and `jieba.analyse` for Chinese word segmentation and stop-word removal.
*   **Descriptive Statistics & Word Frequency:** Calculated the length of reviews and extracted the top 15 high-frequency keywords. Visualized using `matplotlib`.
*   **Topic Modeling:** Implemented **Latent Dirichlet Allocation (LDA)** to uncover underlying thematic structures.
*   **Specific Case Verification:** The script also includes specific code segments used to calculate the exact occurrence of certain words mentioned in the paper's case study section.

## 5. Repository Structure
```text
├── README.md
├── analysis.ipynb             
└── sample_dataset.xlsx        
