# LLM_from_scratch



## সিরিজ স্ট্রাকচার (১২-১৫ পার্ট)

### **Part 0: Introduction & Roadmap**
- কেন LLM from scratch শেখা জরুরি
- এই সিরিজ কাদের জন্য, কী কী থাকবে
- প্রয়োজনীয় প্রস্তুতি (Python, PyTorch basics)
- **প্রজেক্ট গোল:** ১০-৫০ মিলিয়ন প্যারামিটারের একটি ছোট GPT মডেল বানানো

---

### **Part 1: Tokenization (ভাষাকে সংখ্যায় রূপান্তর)**

**কী শেখাবেন:**
- কেন টোকেনাইজেশন দরকার (ইউনিকোড, ক্যারেক্টার vs সাবওয়ার্ড)
- **BPE (Byte Pair Encoding)** — গভীরভাবে
- **SentencePiece** এবং **Bengali text-এর চ্যালেঞ্জ**
- হাতে-কলমে: নিজের টোকেনাইজার বানানো (Hugging Face `tokenizers` library ছাড়া)

**Implementation:**
```python
# সহজ BPE from scratch
# Bengali text-এ টেস্ট করা
# Vocabulary size, merge rules visualization
```

**ডেপথ:** 
- BPE algorithm-এর time complexity
- Bengali-এর জন্য special considerations (conjuncts, diacritics)

---

### **Part 2: Embeddings (শব্দকে ভেক্টরে রূপান্তর)**

**কী শেখাবেন:**
- One-hot vs Dense embeddings
- **Word2Vec, GloVe** — historical context
- **Positional Encoding** — কেন দরকার, Sinusoidal vs Learned
- **Token + Position Embedding**

**Implementation:**
- `nn.Embedding` from scratch (PyTorch)
- Positional encoding visualization
- Embedding space-এ similarity দেখানো

---

### **Part 3: Attention Mechanism (মনোযোগের যন্ত্র)**

**কী শেখাবেন:**
- RNN/LSTM-এর সীমাবদ্ধতা
- **Self-Attention** — intuition থেকে math পর্যন্ত
- Query, Key, Value (QKV) — এনালজি দিয়ে ব্যাখ্যা
- **Scaled Dot-Product Attention**
- **Multi-Head Attention** — কেন একাধিক head

**Implementation:**
- Attention mechanism pure NumPy/PyTorch-এ
- Attention weights visualization (heatmap)
- Bengali sentence-এ attention pattern দেখানো

---

### **Part 4: Transformer Architecture (পূর্ণাঙ্গ কাঠামো)**

**কী শেখাবেন:**
- **Encoder-Decoder** vs **Decoder-only** (GPT স্টাইল)
- **Layer Normalization**, Residual Connections
- **Feed-Forward Network** (FFN)
- **Transformer Block** একসাথে

**Implementation:**
- একটি complete Transformer block
- Forward pass step-by-step debug
- Parameter counting

---

### **Part 5: Training Basics (প্রথম মডেল ট্রেইন)**

**কী শেখাবেন:**
- **Autoregressive Language Modeling** (next token prediction)
- **Loss function:** Cross-Entropy
- **Optimizer:** AdamW, learning rate scheduling
- **Gradient Clipping**
- **Training loop** from scratch

**Implementation:**
- ছোট ডেটাসেটে (Wikipedia Bengali, বা ছোট custom corpus)
- প্রথম ছোট মডেল (1-5M parameters)
- Training metrics, loss curve plotting

---

### **Part 6: Scaling & Efficiency (বড় মডেল ট্রেইন)**

**কী শেখাবেন:**
- **Mixed Precision Training** (FP16/BF16)
- **Gradient Accumulation**
- **Distributed Training** (DDP) — concept
- **Memory optimization:** Gradient checkpointing
- **Training dynamics:** Loss spikes, instability

**Implementation:**
- বড় মডেল (10-50M parameters)
- Training efficiency comparison
- Memory profiling

---

### **Part 7: Text Generation Strategies (আউটপুট তৈরি)**

**কী শেখাবেন:**
- **Greedy Decoding**
- **Beam Search**
- **Sampling:** Temperature, Top-k, Top-p (Nucleus)
- **Repetition Penalty**

**Implementation:**
- বিভিন্ন decoding strategy ইমপ্লিমেন্ট
- Bengali text generation quality comparison
- Interactive generation demo

---

### **Part 8: Evaluation & Metrics (মডেল কেমন হলো?)**

**কী শেখাবেন:**
- **Perplexity** — কী বোঝায়, limitation
- **BLEU, ROUGE** — generation quality
- **Human evaluation** — কেন গুরুত্বপূর্ণ
- **Benchmarks:** Custom Bengali evaluation set

**Implementation:**
- Perplexity calculation from scratch
- Evaluation pipeline
- Error analysis (কোথায় মডেল ভুল করে)

---

### **Part 9: Fine-tuning (নিজের কাজে লাগানো)**

**কী শেখাবেন:**
- **Full Fine-tuning** vs **Parameter-Efficient Fine-Tuning (PEFT)**
- **LoRA (Low-Rank Adaptation)** — গভীরভাবে
- **Instruction Tuning** — কী, কেন
- **SFT (Supervised Fine-Tuning)** pipeline

**Implementation:**
- LoRA from scratch (custom implementation)
- Bengali QA/chatbot fine-tuning
- Memory comparison: Full vs LoRA

---

### **Part 10: Alignment & RLHF (মানুষের মতো আচরণ)**

**কী শেখাবেন:**
- **RLHF** — Reward Model, PPO
- **DPO (Direct Preference Optimization)** — সহজ বিকল্প
- **Constitutional AI** — concept
- **Safety & Bias** — Bengali context-এ

**Implementation:**
- DPO from scratch (simpler than RLHF)
- Preference data creation
- Before/after comparison

---

### **Part 11: Deployment & Optimization (প্রোডাকশনে নেওয়া)**

**কী শেখাবেন:**
- **Quantization:** INT8, INT4, GGUF
- **ONNX/TensorRT** — concept
- **vLLM, TGI** — serving
- **API building** with FastAPI

**Implementation:**
- মডেল কোয়ান্টাইজ
- FastAPI-তে REST API
- Latency/throughput benchmarking

---

### **Part 12: Advanced Topics (Bonus)**

- **Mixture of Experts (MoE)**
- **Multimodal LLM** concept
- **Long Context** (RoPE, ALiBi)
- **Speculative Decoding**
- **Current Research Trends**

---

## টেকনিক্যাল স্ট্যাক সাজেশন

```
Language:     Python 3.10+
Framework:    PyTorch (from scratch, minimal abstractions)
Tokenizer:    Custom BPE + Hugging Face tokenizers (reference)
Training:     PyTorch DDP (later parts)
Logging:      Weights & Biases / TensorBoard
Dataset:      Bengali Wikipedia, Common Crawl, or custom
Compute:      Colab / Kaggle 
```

---


#### GitHub Repo স্ট্রাকচার

```
llm-from-scratch-bn/
├── README.md (বাংলায়, সম্পূর্ণ রোডম্যাপ)
├── part-01-tokenization/
│   ├── blog.md
│   ├── tokenizer_from_scratch.py
│   └── bengali_bpe.ipynb
├── part-02-embeddings/
├── ...
├── data/
│   ├── bengali_wikipedia.txt
│   └── tokenizer_vocab.json
├── models/
│   └── small_gpt_config.yaml
└── requirements.txt
```

---

## রিসোর্স

- "Attention Is All You Need" paper (original)
- Andrej Karpathy's "Let's build GPT from scratch" (YouTube)
- "The Illustrated Transformer" by Jay Alammar
- Bengali NLP papers (tokenization, morphology)

---
