# Fundamentals of Natural Language Processing 
## Overview
The project spans three major NLP segments, addressing both rule-based language modeling (English) and low-resource complex morphology handling (Urdu).

The main components are:
1. **Part A: ELIZA-Type Mental Health Support Chatbot**
2. **Part B: Urdu Sentence Segmentation and Tokenization**
3. **Part C: Commentary on the UrduLM Paper**

---

## Part A: ELIZA-Type Mental Health Support Chatbot
A rule-based conversational agent mimicking the mechanics of the classical **ELIZA** chatbot. Tailored specifically as a first-point-of-contact mental health support therapist, the bot applies Rogerian psychology techniques.
- **Pronoun Reflection:** Dynamically reflects user responses (e.g., swapping "I am" for "you are") to maintain empathetic continuity.
- **Regex Pattern Matching:** Detects intents regarding stress, anxiety, depression, sleep issues, and crises and responds with pre-defined, empathetic templates.

## Part B: Urdu Sentence Segmentation and Tokenization
Standard tokenizers (like WordPiece or BPE) typically fail on informal, social-media Urdu due to missing punctuations or informal spacing norms. This implementation tackles Nastaliq script issues without relying on rigid tools:
- **Noise Cleaning & Whitespace Normalization:** Handles invisible characters (Zero-Width Joiners/Non-Joiners), removes English mentions/URLs, and fixes the Space Insertion/Omission problem.
- **Tokenization:** Word tokenization that deliberately isolates Urdu punctuation to avoid character binding.
- **Sentence Segmentation (Dual Strategy):**
  - *Terminator-Based:* Explicitly splitting on `۔`, `؟`, `!`.
  - *End-Word Heuristic:* Utilizes linguistically-motivated dictionaries of verbs (`ہے`, `ہیں`, `تھا`) that typical close sentences, coupled with start-words.

## Part C: UrduLM Paper Commentary
An analytical review of the paper *"UrduLM: A Resource-Efficient Monolingual Urdu Language Model"*. 
- Discusses the creation of the 33GB robust monolingual Urdu text corpus.
- Compares vocabulary capacity, explaining why a 100M parameter Urdu-only model outperforms multi-lingual colossal models (mBERT, XLM-RoBERTa) on specifically Pakistani and Urdu-idiomatic tasks like formal grammar, hatespeech, and sentiment analysis.

---

## Repository Contents

* **`M_Umer_Shehzad_BS_23_IB_101047.ipynb`**: The main Jupyter Notebook holding the Python code for the chatbot and the Urdu parsing logic.
* **`MUmerShehzad_BS_23_IB_101047.pdf` / `.docx`**: Detailed project report containing architecture reasoning, logic explanations, dictionary constraints, and the UrduLM analysis.
* **`HS_Urdu_Tokenized.csv`**: Hate Speech Social Media Dataset containing noisy Urdu tweets used to evaluate tokenizer robustness.
* **`UrduCorpus_tokenized.csv`**: Reference formal Urdu text data used for comparative metric evaluation (Precision/Recall/F1).

## Usage
If you'd like to test the chatbot or the tokenizer:
1. Clone the repository.
2. Ensure you have Jupyter Notebook/JupyterLab installed with a recent Python kernel.
3. Open `M_Umer_Shehzad_BS_23_IB_101047.ipynb` and run the cells step-by-step.
4. For text testing, refer to the provided `csv` dataset snippets or provide your own string lines directly in the notebook environment.
