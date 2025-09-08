#  CarDVLM: Car Damage Assessment using Vision-Language Models  

Accurate vehicle damage assessment is critical for **automotive eCommerce platforms**, where buyers depend on transparent visual evidence to make informed purchasing decisions. Traditional object detectors (e.g., YOLO, Mask R-CNN) can localise damage but fail to provide contextual explanations such as **type, location, and severity**.  

To address this gap, we introduce **CarDVLM**, a multimodal framework that integrates **GroundingCarDD** with a fine-tuned **vision–language model (LLaVA)**. The system detects and localises damages, then generates **structured, query-driven textual descriptions**, enabling interpretable and user-centric assessments.  

---

## 📑 Paper  

<span class="link-block">
  <span class="external-link button is-normal is-rounded is-dark">
    <span class="icon">
      <i class="ai ai-arxiv"></i>
    </span>
    <span>Paper (Under Review)</span>
  </span>
</span>  

---

##  Key Contributions  

- **CarDVLM Framework**  
  A domain-adapted system combining **phrase-grounded object detection** with multimodal reasoning for interpretable car damage analysis.  

- **Structured Automotive Dataset**  
  Constructed from public (CarDD) and private sources, with bounding box annotations and semantically aligned descriptions across **25 vehicle body parts**.  

- **CarDamageEval**  
  A two-tier evaluation framework that measures structured accuracy with precision, recall, F1, and human-aligned evaluation.  

- **Ablation Study under Real-World Scenarios**  
  Comprehensive testing across three challenging conditions:  
  - Clearly visible damages  
  - Spatially ambiguous damages (left/right or front/rear orientation)  
  - Extremely subtle or partially obscured damages  
  This validates CarDVLM’s robustness and practical deployment readiness.  

---

##  Results  

### Structured Evaluation (Pair-Matching)  
| Model      | Accuracy | Precision | Recall | F1 Score |
|------------|----------|-----------|--------|----------|
| ChatGPT    | 59.5     | 59.6      | 65.5   | 61.5     |
| LLaMA      | 70.6     | 77.6      | 75.5   | 75.3     |
| Qwen       | 74.9     | 87.4      | 80.5   | 82.3     |
| **CarDVLM** | **86.7** | **88.8**  | **90.2** | **89.5** |

CarDVLM delivers **state-of-the-art structured accuracy**, outperforming all baselines.  

---

## Model Architecture  

<p align="center">
  <img src="assets/cardvlm_architecture.png" alt="CarDVLM Architecture" width="650">
</p>  

*Figure: CarDVLM integrates [GroundingCarDD](https://hellojahid.github.io/paper/groundingcardd/groundingcardd.html) with a fine-tuned VLM (CLIP + LLaMA-2 13B + LoRA).*  

---



