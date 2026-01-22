

The **CarDVLM dataset** is a multimodal prompt–response training dataset designed for vision language modelling of vehicle damage assessment. The dataset is released in **LLaVA compatible conversational JSON format**, enabling direct use for instruction tuning and evaluation of large vision language models.

The dataset is **derived entirely from publicly available data**, with all released annotations constructed from the CarDD dataset. To comply with licensing constraints, **original images are not redistributed**. Only **textual supervision and annotation metadata** are publicly released.

No private images, annotations, or proprietary data are included in this release.

---

## Key Contributions

The CarDVLM dataset provides:

- Bounding box–aware textual supervision for vehicle damage understanding  
- Explicit encoding of damage type, spatial location, and body part semantics  
- Multi-turn, query-driven conversational supervision aligned with visual grounding  
- Coverage of 25 vehicle body parts with fine-grained damage localisation  
- Direct compatibility with LLaVA style training pipelines  

---

## Dataset Format

Each sample follows the standard **LLaVA conversational schema**, grounded to an image identifier.

### Example structure

    {
      "id": "000001",
      "image": "000001.jpg",
      "conversations": [
        {
          "from": "human",
          "value": "<image>\nAre there any noticeable damages on this vehicle?"
        },
        {
          "from": "gpt",
          "value": "The following damages are detected:\n- Scratch: rear left wheel arch"
        }
      ]
    }

### Important notes

- The `image` field is a reference only and does not include image data  
- All released supervision is textual and semantic  
- Users must obtain original CarDD images separately  

---

## Bounding Box Colour Encoding

Bounding box colours are used as semantic identifiers to preserve consistent damage grounding across annotations and prompts.

| Bounding box colour | Damage type |
|--------------------|-------------|
| Blue | Dent |
| Dark green | Scratch |
| Magenta | Crack |
| Red | Shattered glass |
| Teal | Broken lamp |
| Orange | Flat tire |

Colour references are included only in text form and do not imply redistribution of visual overlays.

---

## Vehicle Body Part Coverage

Damage descriptions are aligned to **25 vehicle body parts**, including:

- Front and rear bumpers  
- Doors and quarter panels  
- Fender and wheel arch regions  
- Headlights, tail lights, and lamps  
- Windscreens and side windows  
- Wheels and tires  

This supports structured reasoning over damage–part relationships rather than coarse image-level descriptions.

---

## Data Source and Licensing

### Source dataset

- All annotations are derived from the CarDD dataset  
- Used under its original academic research licence  

### Redistribution policy

- Original images are not redistributed  
- This repository releases text-only annotations  
- No private or proprietary data are included  
- Users must download CarDD images from the official source to reconstruct full training data  

---

## Intended Use

The LLAVA-CarDVLM dataset is intended for:

- Instruction tuning of vision language models  
- Multimodal grounding and damage localisation research  
- Evaluation of structured automotive damage descriptions  

The dataset is released for academic research purposes only, consistent with the licence of the source dataset.

---

## Citation

If you use this dataset, please cite:

- The CarDVLM paper  
A BibTeX entry will be provided upon paper acceptance.

---

## Acknowledgements

We acknowledge the authors of the CarDD dataset(https://cardd-ustc.github.io/) for making their dataset publicly available.

