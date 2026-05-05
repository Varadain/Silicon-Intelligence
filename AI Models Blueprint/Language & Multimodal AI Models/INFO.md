# Understanding Language & Multimodal AI Models

This guide explains the fundamental concepts required to understand modern AI models such as LLM, VLM, MLLM, and VLA.
---

## 1. Tokens

### What are Tokens?
Tokens are the smallest units of text that a model processes.

Examples:
- "Hello world" → ["Hello", "world"]
- "playing" → ["play", "ing"] (depending on tokenizer)

### Why Tokens?
Models cannot understand raw text directly.  
They convert text into tokens to process it mathematically.

---

## 2. Tokenization

### Definition
The process of converting text into tokens.

### Types
- Word-level
- Subword-level (most common)
- Character-level

### Example

"I have Computer"
→ ["I", "have", "Computer"]


---

## 3. Embeddings

### What are Embeddings?
Numerical vector representations of tokens.

### Why Needed?
Neural networks work with numbers, not text.

### Example

"cat" → [0.21, -0.45, 0.78, ...]


### Insight
- Similar words → similar vectors
- Forms semantic meaning space

---

## 4. Transformer

### What is a Transformer?
The core architecture behind modern AI models.

### Key Idea
Processes all tokens in parallel and learns relationships between them.

### Components
- Attention mechanism
- Feedforward layers
- Positional encoding

---

## 5. Attention Mechanism

### Simple Meaning
Helps the model focus on important words.

### Example
Sentence:

"The cat sat on the mat because it was tired"

"it" → refers to "cat"

### Formula

Attention(Q, K, V) = softmax(QK^T / √d) V


---

## 6. Self-Attention

### Definition
Each token attends to every other token.

### Purpose
Captures relationships within a sentence.

---

## 7. Cross-Attention

### Definition
One modality attends to another.

### Example
- Text attends to image features (in VLM)

---

## 8. Encoder vs Decoder

| Component | Role |
|----------|------|
| Encoder  | Understand input |
| Decoder  | Generate output |

---

## 9. LLM (Large Language Model)

### What it does
- Processes and generates text

### Input
- Tokens

### Output
- Next token prediction

### Key Idea

P(x_t | x₁, x₂, ..., x_{t-1})


---

## 10. SLM (Small Language Model)

### What it is
- Lightweight version of LLM

### Features
- Fewer parameters
- Faster inference
- Lower memory usage

### Techniques
- Quantization
- Pruning

---

## 11. CNN (Convolutional Neural Network)

### Used for
- Image processing

### Key Operation

y(i,j) = Σ x(m,n) * w(i-m, j-n)


---

## 12. Vision Transformer (ViT)

### What it does
- Applies transformer to images

### Process
- Image → patches → embeddings → transformer

---

## 13. VLM (Vision Language Model)

### What it does
- Combines image + text understanding

### Flow
Image → Vision Encoder  
Text → Language Encoder  
→ Fusion → Output

---

## 14. Fusion Layer

### Definition
Combines multiple modalities into a single representation.

### Example
- Image + text → shared embedding space

---

## 15. MLLM (Multimodal LLM)

### What it does
- Processes text, image, audio together

### Key Idea
Unified representation of different data types

---

## 16. VLA (Vision Language Action Model)

### What it does
- Converts perception into action

### Flow

Vision → Understanding → Decision → Action


### Used in
- Robotics
- Autonomous systems

---

## 17. Policy (π)

### Definition
Mapping from state to action

### Formula

π(a|s)


---

## 18. Feedback Loop

### Definition
System learns from its own output

### Example
Robot adjusts movement based on sensor feedback

---

## 19. Model Compression

### Techniques
- Quantization
- Pruning
- Distillation

### Purpose
- Reduce size
- Improve speed

---

## 20. Latency vs Throughput

| Term       | Meaning |
|-----------|--------|
| Latency   | Time per task |
| Throughput| Tasks per second |

---

## 21. Multimodal Learning

### Definition
Learning from multiple data types:
- Text
- Image
- Audio

---

## 22. Real-World Insight

- LLM → Understand language  
- VLM → Understand world (vision + language)  
- MLLM → Combine senses  
- VLA → Act in real world  

---

## Final Understanding

AI systems evolve like this:


Text → Understanding → Perception → Reasoning → Action
