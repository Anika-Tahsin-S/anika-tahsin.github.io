---
layout: page
title: Intended Sarcasm Detection in English (SemEval 2022 Task A)
description: Transformer-based NLP with bias-aware labeling and BERT fine-tuning
# img: assets/img/projects/sarcasm/cover.png
importance: 4
category: work
related_publications: true
---

- Built an NLP pipeline to detect **intended sarcasm** in English conversational text as a **binary classification** task (SemEval 2022 iSarcasmEval, Task A).
- Consolidated and re-labeled multi-part dataset splits into a unified binary corpus; prepared robust training/evaluation loops.
- Fine-tuned **BERT-base** (primary) and explored **DistilBERT** variants; applied class weighting and careful validation.
- Achieved a **peak F1 (sarcastic class) of 0.6529** (epoch 5), exceeding the **SemEval 2022 winning score of 0.6052** reported for the same task.

**Repo:** [GitHub](https://github.com/Anika-Tahsin-S/Intended-Sarcasm-Detection-In-English)  
**SemEval (Task site):** <https://sites.google.com/view/semeval2022-isarcasmeval>  
**Dataset:** <https://github.com/iabufarha/iSarcasmEval>  
**Associated Paper:** <https://aclanthology.org/2022.semeval-1.111.pdf>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/sarcasm/1.png" title="Dataset structure & relabeling" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/sarcasm/2.png" title="BERT-based classification head" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/sarcasm/3.png" title="Confusion matrix & PR curves" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Left: unifying the three dataset parts into a binary task; Middle: BERT fine-tuning head; Right: evaluation artifacts (confusion/PR).
</div>

**Highlights**
- **Task & Data:** iSarcasmEval (SemEval 2022) English subset; **6,134** training examples and **1,400** test examples after consolidation  
- **Labeling Strategy:** Converted each split into single-text entries with {sarcastic, non-sarcastic} labels; used winning annotator labels where applicable  
- **Models:** BERT-base (primary), DistilBERT (explored)  
- **Training (BERT-base):** batch size 4, epochs 10, learning rate 2e-5, weight decay 0.01  
- **Metrics:** F1 (sarcastic), precision/recall, calibration and error slicing  
- **Result:** **F1 (sarcastic) = 0.6529** @ epoch 5 (vs. **0.6052** SemEval winning score for Task A)

---

### Dataset & Labeling Overview
- **Part 1:** Sarcastic tweets + human **unsarcastic rephrases** → sarcastic = “sarcastic” / rephrase = “non-sarcastic”  
- **Part 2:** Texts with **5 annotator votes** → use majority label  
- **Part 3:** **Paired** sarcastic vs. non-sarcastic texts → add both items with corresponding labels  
This yields a diverse binary dataset reflecting author-reported sarcasm and annotator validation.

**Example (EN)**
> Sarcastic: “Gotta love people who follow you and unfollow because you don’t follow them within an hour or 2. Sorry I don’t stay on Twitter 24/7.”  
> Unsarcastic: “I dislike people who follow me, only to unfollow me when I don’t follow back right away. I’m not on Twitter that much to follow right away.”

---

### Model & Hyperparameters
We fine-tuned **BERT-base** for binary classification; DistilBERT was also tested as a lighter alternative.

| Parameter       | Value  |
|---|---|
| Batch size      | 4      |
| Epochs          | 10     |
| Learning rate   | 2e-5   |
| Weight decay    | 0.01   |

---

### Results (Validation)
Best F1 on the sarcastic class reached **0.6529 at epoch 5**.

| Epoch | Train Loss | Val Loss | F1 (sarcastic) |
|---:|---:|---:|---:|
| 1 | 0.5382 | 0.2890 | 0.5900 |
| 2 | 0.5203 | 0.4868 | 0.6217 |
| 3 | 0.3473 | 0.5875 | 0.6499 |
| 4 | 0.2091 | 0.7926 | 0.6453 |
| **5** | **0.0925** | **0.9241** | **0.6529** |
| 6 | 0.0718 | 0.8687 | 0.6352 |
| 7 | 0.0714 | 1.0984 | 0.6300 |
| 8 | 0.0389 | 1.2328 | 0.6352 |
| 9 | 0.0241 | 1.2649 | 0.6403 |
| 10 | 0.0142 | 1.3279 | 0.6377 |

> **Note:** Despite rising validation loss after epoch 5, F1 peaked at epoch 5—indicating mild overfitting; we select epoch 5 by metric.

---

### Limitations
- Primary data source is **Twitter**, which may limit generalization across platforms/domains.  
- Sarcasm manifests differently by community and context; cross-domain robustness requires further data and adaptation.

---

### Conclusion
Our BERT-based system (with DistilBERT explored) effectively detects intended sarcasm on iSarcasmEval. It achieves a **peak F1 of 0.6529** on the sarcastic class, demonstrating strong performance and surpassing the SemEval 2022 reported winning score for Task A. Future work: domain adaptation beyond Twitter, richer context modeling, and improved calibration.