# 🧠 Next-Word Prediction using PyTorch

*A language-model notebook built using PyTorch for next-word prediction.*

## 📌 Overview

This project demonstrates how to build a **Next-Word Prediction Model** using **PyTorch**.
The notebook (`next_word_prediction.ipynb`) covers the complete workflow:
text preprocessing → tokenization → building a vocabulary → creating training sequences → defining a PyTorch model → training → inference.

The model predicts the next likely word given a partial sentence.

---

## 🚀 Features

* Built entirely using **PyTorch**
* Custom neural network for next-word prediction
* Tokenization and vocabulary building
* Dataset → tensor conversion
* Training loop written manually (no high-level wrappers)
* Inference using model output probabilities
* Easy to extend (larger models, more layers, pretrained embeddings, etc.)

---

# 🏗️ Project Workflow

## **1. Data Preprocessing**

* Load text data directly in the notebook.
* Clean and normalize (lowercasing, punctuation removal).
* Tokenize into words.

## **2. Vocabulary Creation**

* Map each unique word to an integer index.
* Create:

  * `word_to_index`
  * `index_to_word`

## **3. Sequence Generation**

* Convert text into input sequences for training.
* Example:

  ```
  Input:  "I love deep"
  Label:  "learning"
  ```

## **4. Dataset & Dataloader**

* Build PyTorch tensors for:

  * Input sequences
  * Target (next word)
* Use DataLoader for batching.

## **5. Model Definition**

Typical components include:

* **Embedding layer**
* **LSTM / GRU / RNN**
* **Linear (Fully Connected) output layer**
* **Softmax** for prediction over vocabulary

Defined using:

```python
import torch.nn as nn
```

## **6. Training Loop**

The notebook implements:

* Forward pass
* Loss calculation (CrossEntropyLoss)
* Backward pass
* Optimizer step
* Epoch-level logging

## **7. Next-Word Prediction**

Given input text:

```python
predict_next_word("The world is")
```

The model:

* Tokenizes
* Passes through network
* Gets softmax probabilities
* Selects highest-probability next word

---

# 🧩 Tools & Libraries Used

| Library                   | Purpose                       |
| ------------------------- | ----------------------------- |
| **PyTorch**               | Model, training loop, tensors |
| **NumPy**                 | Data operations               |
| **NLTK** (optional)       | Tokenization / stopwords      |
| **re**                    | Text cleaning                 |
| **Matplotlib** (optional) | Plotting loss                 |

No TensorFlow or Keras is used.

---

# 📦 Installation & Setup

### **1. Create environment**

```bash
python -m venv venv
source venv/bin/activate     # macOS/Linux
venv\Scripts\activate        # Windows
```

### **2. Install dependencies**

Example `requirements.txt`:

```
torch
numpy
nltk
matplotlib
```

Install:

```bash
pip install -r requirements.txt
```

### **3. Launch notebook**

```bash
jupyter notebook next_word_prediction.ipynb
```

---

# 🧪 Usage

### **Run training**

Execute all cells — the notebook will preprocess data, build vocabulary, train the PyTorch model, and save it if implemented.

### **Predict next word**

At the bottom of the notebook:

```python
predict_next_word("I want to")
```

Output example:

```
"learn"
```

---

# 📁 Project Structure

```
├── next_word_prediction.ipynb   # Main PyTorch notebook
├── requirements.txt             # Dependencies
└── README.md                    # Documentation
```

