# ⏱️ Reading Time & Complexity Estimator Agent

An autonomous tool-using LLM Agent built with **`smolagents`** and the **Hugging Face Inference API** (`Qwen/Qwen2.5-72B-Instruct`). This agent dynamically delegates text analysis tasks to a deterministic Python tool (`estimate_reading_time`) to deliver exact word counts, estimated reading durations, length classifications, and lexical complexity evaluations without LLM estimation errors.

---

## 🚀 Key Features

* **Deterministic Precision:** Offloads counting and arithmetic to a custom Python tool (`estimate_reading_time`) rather than relying on probabilistic LLM token approximations.
* **Comprehensive Text Analytics:**
  * **Exact Word Count:** Uses regex-based tokenization (`\b\w+\b`) to handle punctuation, contractions, and hyphenated words accurately.
  * **Estimated Reading Time:** Computes reading duration based on the standard adult average of **200 words per minute (WPM)** (formatted in both minutes and seconds).
  * **Length Categorization:** Classifies content into *Short (< 2 min)*, *Medium (2–5 min)*, or *Long (> 5 min)*.
  * **Lexical Complexity Assessment:** Evaluates average word length and vocabulary richness to classify readability (*Simple*, *Moderate*, or *Complex*).
* **Secure Authentication:** Uses environment variables (`HF_TOKEN`) and interactive `getpass()` prompts to keep API keys completely out of source control.

---

## 🛠️ Tech Stack

* **Agent Framework:** `smolagents`
* **LLM Backbone:** `Qwen/Qwen2.5-72B-Instruct` via `huggingface_hub` (`InferenceClient`)
* **Language & Environment:** Python 3.10+, Jupyter Notebook (`agent_assignment.ipynb`)

---

## 📂 Repository Structure

```text
smolagents-tool-project/
├── agent_assignment.ipynb   # Main notebook containing the custom tool, unit tests, and agent workflow
├── requirements.txt         # Project dependencies
└── README.md                # Project documentation
