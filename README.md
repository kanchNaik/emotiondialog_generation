# 🎭 Bringing Characters to Life – Emotion-Based Dialogue Generation

A deep learning project aimed at building emotionally intelligent dialogue systems by modeling the complex interplay of **personality, mood dynamics, and emotional tone** in multi-turn conversations.

> 📍 Developed as part of the Applied Data Intelligence program at San Jose State University  
> 📁 Dataset: [PELD (Personality-Affected Emotion Lines Dataset)] – derived from *Friends* TV show scripts

---

## 🧠 Objective

To generate emotionally coherent responses by predicting a speaker’s emotion using:
- Dialogue context
- Personality traits (OCEAN model)
- Mood transitions in Valence–Arousal–Dominance (VAD) space

---

## 🔍 Dataset Overview

**PELD** is a dyadic conversational dataset containing:
- Three-turn conversations (`U1`, `U2`, `U3`)
- Emotion labels (7 classes: Joy, Sadness, Anger, Disgust, Fear, Surprise, Neutral)
- Fixed 5-D personality vectors (OCEAN) per character
- Projected into VAD space for modeling mood transitions

---

## 🏗️ Architecture Overview

### 🔄 Data Preprocessing
- BERT tokenization with `[CLS]` and `[SEP]`
- Emotion labels mapped to VAD vectors
- Personality projected into VAD space using Mehrabian mappings

### 🧩 Core Modules
- **Context Encoder**: BERT-base with VAD-enhanced token embeddings
- **Mood Transition Module**: Computes evolving mood vector based on emotion, context, and personality
- **Emotion Classifier**: Predicts final emotion from mood, context, and personality

---

## 🧪 Experiments

We implemented **six experimental architectures**, each exploring unique modeling approaches:

| Model | Highlights |
|-------|------------|
| **1. Multi-head VAD Attention** | Token-level attention aligned with Valence, Arousal, and Dominance |
| **2. Graph Neural Network (GNN)** | Graphs of utterances + personality vectors; GCN-based learning |
| **3. HTN + GRU** | Hierarchical Transformers + GRU for long-range mood tracking |
| **4. Autoencoder** | Joint reconstruction, emotion classification, and mood regression |
| **5. Temporal Convolutional Network (TCN)** | Modeled emotion shifts using temporal filters |
| **6. BERT + BiGRU** | Bidirectional context modeling fused with mood and personality |

---

## 📊 Results

| Model | Micro-F1 | Macro-F1 | Weighted F1 |
|-------|----------|----------|-------------|
| **Benchmark** | 0.41 | 0.33 | 0.33 |
| Multi-head Attention | 0.45 | 0.19 | 0.37 |
| GNN | 0.32 | 0.19 | 0.30 |
| **HTN + GRU** | 0.48 | 0.39 | 0.50 |
| Autoencoder | 0.41 | 0.38 | 0.42 |
| **TCN (Best)** | **0.55** | **0.43** | **0.54** |
| BERT + BiGRU | 0.43 | 0.34 | 0.39 |

✅ **TCN outperformed baseline by over 30% (Macro-F1)**  
✅ Notable gains in classifying low-frequency emotions (*Disgust*, *Surprise*, *Fear*)  

---

## 🎯 Key Innovations

- 💡 Personality-conditioned **mood modeling** in VAD space
- 💡 Multi-task learning for **emotion classification + mood regression**
- 💡 Integration of **psychologically grounded models** with NLP

---

## 📌 Skills & Tech Stack

- **Language Models**: BERT, BiGRU, Hierarchical Transformers
- **Temporal Models**: GRU, TCN
- **Graph Models**: GNN, GCNConv (PyTorch Geometric)
- **Frameworks**: PyTorch, Hugging Face, scikit-learn
- **NLP**: VAD emotion modeling, OCEAN trait fusion, conversational context encoding
- **Evaluation**: Macro-F1, Micro-F1, Mood vector MSE

---

## 🚀 Future Work

- Introduce **Graph Transformers** for improved discourse modeling
- Add **multimodal features** (audio/visual)
- Deploy interactive **persona-driven chatbot**
- Integrate **explainability** for mood/emotion reasoning

---

## 🤝 Contributors

- Kanchan Naik  
- Charishma Tamarana  
- Mrunali Katta  
- Soumya Challuru Sreenivas  
- Vaishnavi Nanduri  
- Yashasvi Kanchugantla

---

## 📄 References

Based on psychological mappings and techniques from:  
Mehrabian (1996), Rashkin et al. (2019), Majumder et al. (2019), Wen et al. (2024), and more (see full paper for citations).

---

