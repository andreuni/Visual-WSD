
# Visual WSD: Multimodal Word Sense Disambiguation

This project explores **Word Sense Disambiguation (WSD)** using a multimodal approach that combines text and image embeddings. The focus is on improving the accuracy of WSD tasks across multiple languages, including English, Italian, and Farsi.

---

## Overview

### Objectives:
- Leverage **text and image embeddings** for WSD tasks.
- Explore translation techniques and context generation to improve accuracy in low-resource languages (e.g., Italian and Farsi).

### Key Features:
1. **Clip Base**:
   - Extracts **text embeddings** and **image embeddings**.
   - Calculates similarity using the mean of similarities between embeddings.
   - Initial Accuracy:
     - English: **0.5053**
     - Italian: **0.1836**
     - Farsi: **0.07**

2. **Translation Pipeline**:
   - Italian to English using **MarianMT** (`Helsinki-NLP/opus-mt-it-en`).
   - Farsi to English using **MT5** (`persiannlp/mt5-base-parsinlu-opus-translation-fa-en`).
   - Accuracy Improvements:
     - Italian: **+0.2459** (0.4295 total)
     - Farsi: **+0.235** (0.305 total)

3. **Context Generation**:
   - **GPT-Neo**: Generates descriptive sentences for improved disambiguation.
   - Example:
     - Input: "Neptune Statue"
     - Output: "The Neptune Statue is a sculpture of Neptune, the Roman god of the sea, located in the port of Naples, Italy."
   - Accuracy Improvements:
     - English: **+0.0649** (0.5702 total)
     - Italian: **+0.263** (0.446 total)
     - Farsi: **+0.260** (0.33 total)

4. **WSD Methods**:
   - **Simple**: Matches the first synset where the context appears in the definition.
   - **Lesk Sentence Embeddings**:
     - Uses **Sentence Transformers** (`All-Mini-LM-L6`) for embedding comparisons.
     - Accuracy Improvements:
       - English: **+0.1275** (0.6328 total)
       - Italian: **+0.3155** (0.5016 total)
       - Farsi: **+0.245** (0.315 total)

5. **Image Captioning**:
   - Generates captions using **Vit-GPT2-Image-Captioning**.
   - Compares similarity between caption and context using embeddings.
   - Accuracy:
     - English: **0.2678**
     - Italian: **0.0393**
     - Farsi: **0.025**

---

## Results

### Final Accuracy Summary:
| Method             | English  | Italian  | Farsi   |
|--------------------|----------|----------|---------|
| **Clip Base**       | 0.5053   | 0.1836   | 0.07    |
| **Translation**     | -        | 0.4295   | 0.305   |
| **Context (GPT)**   | 0.5702   | 0.446    | 0.33    |
| **WSD (Lesk)**      | 0.6328   | 0.5016   | 0.315   |
| **Image Captioning**| 0.2678   | 0.0393   | 0.025   |

---

   git clone https://github.com/your-username/visual-wsd.git
