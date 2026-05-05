# Understanding Vision Models in AI

This guide explains the fundamental concepts required to understand modern vision models such as CNN, ViT, DETR, SAM, and YOLO.

---

## 1. Image Representation

### What is an Image in AI?
An image is represented as a 3D matrix:


Image = H × W × C


Where:
- H = Height
- W = Width
- C = Channels (RGB = 3)

---

## 2. Pixels

### Definition
The smallest unit of an image.

Each pixel contains intensity values:
- RGB → (R, G, B)

---

## 3. Feature

### What is a Feature?
A feature is a meaningful pattern extracted from an image.

Examples:
- Edges
- Corners
- Textures
- Shapes

---

## 4. Convolution

### What is Convolution?
A mathematical operation used to extract features.

### Equation

y(i,j) = Σ x(m,n) * w(i-m, j-n)


### Intuition
- Slide a filter over the image
- Detect patterns like edges

---

## 5. Filter (Kernel)

### Definition
A small matrix used in convolution.

Example:
- Edge detector
- Blur filter

---

## 6. Feature Maps

### Definition
Output of convolution layers.

They highlight important regions of the image.

---

## 7. Activation Function (ReLU)

### Definition
Introduces non-linearity.

### Formula

ReLU(x) = max(0, x)


---

## 8. Pooling

### What is Pooling?
Reduces image size while keeping important information.

### Types
- Max pooling
- Average pooling

---

## 9. Fully Connected Layer

### Role
Converts extracted features into final prediction.

---

## 10. CNN (Convolutional Neural Network)

### What it does
- Extracts hierarchical features from images

### Flow

Image → Convolution → ReLU → Pooling → FC → Output


### Key Idea
Local feature extraction

---

## 11. Patch (ViT Concept)

### Definition
Image divided into small patches.

Example:
- 224×224 image → 16×16 patches

---

## 12. Flattening

### Definition
Converting 2D patches into 1D vectors.

---

## 13. Embedding (Vision)

### Definition
Numerical representation of patches.

---

## 14. Attention Mechanism

### What it does
Finds relationships between different parts of the image.

### Formula

Attention(Q,K,V) = softmax(QK^T / √d) V


---

## 15. Vision Transformer (ViT)

### What it does
- Applies transformer to image patches

### Flow

Image → Patches → Embedding → Transformer → Output


### Key Idea
Global context understanding

---

## 16. Backbone

### Definition
Feature extractor (usually CNN)

Used in models like DETR

---

## 17. Transformer Encoder-Decoder

### Encoder
Processes input features

### Decoder
Generates output (like bounding boxes)

---

## 18. Object Detection

### Definition
Finding objects in an image and locating them

### Output
- Bounding box
- Class label

---

## 19. Bounding Box

### Definition
Rectangle around an object

---

## 20. DETR (Detection Transformer)

### What it does
- Detects objects using transformers

### Key Idea
- No anchor boxes
- Uses object queries

---

## 21. Object Queries

### Definition
Learned vectors that represent objects

---

## 22. Hungarian Matching

### Definition
Algorithm used to match predicted objects with ground truth

---

## 23. Segmentation

### What is Segmentation?
Pixel-level classification

Each pixel gets a label

---

## 24. SAM (Segment Anything Model)

### What it does
- Segments any object in an image

### Key Idea
- Prompt-based segmentation

---

## 25. Prompt (in Vision)

### Definition
Input hint:
- Point
- Box
- Text

---

## 26. Mask

### Definition
Binary map showing object region

---

## 27. Grid Division (YOLO)

### Definition
Image divided into grid cells

---

## 28. YOLO (You Only Look Once)

### What it does
- Real-time object detection

### Flow

Image → Grid → Bounding boxes → Output


---

## 29. Confidence Score

### Definition
Probability that an object exists

### Formula

Confidence = P(object) × IoU


---

## 30. IoU (Intersection over Union)

### Definition
Measures overlap between predicted and actual box

---

## 31. Real-Time Detection

### Meaning
Model runs fast enough for live systems

---

## 32. Classification vs Detection vs Segmentation

| Task | Output |
|------|--------|
| Classification | Label |
| Detection | Boxes + Labels |
| Segmentation | Pixel mask |

---

## 33. Data Flow Insight

Different models process images differently:

- CNN → Local features → Classification  
- ViT → Global attention → Understanding  
- DETR → Object queries → Detection  
- SAM → Mask decoding → Segmentation  
- YOLO → Grid prediction → Real-time detection  

---

## 34. Complexity Insight

- CNN → Low complexity  
- ViT → High compute  
- DETR → Balanced  
- SAM → Very high compute  
- YOLO → Optimized for speed  

---

## Final Understanding

Vision models evolve like this:


Pixels → Features → Objects → Regions → Real-time understanding


---

## Key Takeaway

- CNN → Feature extraction  
- ViT → Global understanding  
- DETR → Object detection  
- SAM → Segmentation  
- YOLO → Real-time detection  

Understanding these building blocks allows you to:
- Read any vision model diagram
- Understand AI pipelines
- Compare architectures effectively
