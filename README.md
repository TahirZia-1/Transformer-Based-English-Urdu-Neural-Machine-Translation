
- **data/**: Contains parallel corpora for training, validation, and testing.
- **2021465_2021758.ipynb**: Notebook implementing a custom Transformer model from scratch.
- **huggingface_Model.ipynb**: Notebook fine-tuning the pretrained MarianMT model.
- **requirements.txt**: Lists all necessary Python packages.

---

## 🎯 Objectives

- Develop a custom Transformer model for English-to-Urdu translation.
- Fine-tune a pretrained MarianMT model for the same task.
- Evaluate and compare both models using BLEU and METEOR metrics.

---

## 🧠 Methodology

### Data Preprocessing

- Lowercasing text.
- Removing punctuation and extra whitespace.
- Tokenization.
- Applying Byte Pair Encoding (BPE).
- Padding/truncating sequences to a fixed length.

### Model Architectures

- **Custom Transformer**:
  - Implemented based on Vaswani et al.'s architecture.
  - Features encoder-decoder structure, multi-head attention, and positional encoding.
  - Hyperparameters: 6 layers, 512 hidden units, 8 attention heads.

- **Pretrained MarianMT**:
  - Utilizes Hugging Face's MarianMTModel.
  - Fine-tuned on the provided English-Urdu dataset.
  - Employs MarianTokenizer for preprocessing.

### Training Details

- **Custom Transformer**:
  - Optimizer: Adam with learning rate scheduler.
  - Loss Function: Cross-Entropy with label smoothing.
  - Batch Size: 64.
  - Epochs: 20.
  - Early stopping and gradient clipping applied.

- **MarianMT Model**:
  - Optimizer: AdamW.
  - Batch Size: 32.
  - Epochs: 10.
  - Early stopping based on validation loss.

---

## 📊 Evaluation Metrics

- **BLEU (Bilingual Evaluation Understudy)**:
  - Measures n-gram precision between machine and reference translations.
  - Scores range from 0 to 100; higher scores indicate better translations.

- **METEOR (Metric for Evaluation of Translation with Explicit ORdering)**:
  - Considers synonymy and stemming for more flexible evaluation.
  - Scores range from 0 to 1; higher scores indicate better translations.

---

## 📈 Results

| Model               | BLEU Score | METEOR Score |
|---------------------|------------|--------------|
| Custom Transformer  | 18.5       | 21.3         |
| Pretrained MarianMT | 26.7       | 29.8         |

The pretrained MarianMT model outperformed the custom Transformer model in both BLEU and METEOR scores, highlighting the advantages of transfer learning in low-resource language translation tasks.

---

## 🚀 How to Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/TahirZia-1/NLP-Project.git
   cd NLP-Project
