# Automated Inflammatory Cell Detection using FasterRCNN for Kidney Transplantations: Adaption capabilities

In this work, we train a Faster R-CNN model on PAS-Original and PAS-Diagnostic data and evaluate its performance on PAS-CpG data, both zero-shot and after fine-tuning, to quantify adaptation gains for cross-domain inflammatory cell detection.

## Authors

- **Femke Aminetzah** — femke.aminetzah@ru.nl
- **Martina Baricocchi** — martina.baricocchi@ru.nl  
- **Lisanne Huisman** — lisanne.huisman@ru.nl  
- **Luuk Neervens** — luuk.neervens@ru.nl  

---

## Table of Contents

- [About](#about)  
- [Usage](#usage)  
- [License](#license)  
- [Contact](#contact)
- 
---

## About

Detailed description of the project.  
Explain the motivation, what problem it solves, and why it’s useful.

---

## Usage

The final product was implemented utilizing two notebooks: 
1. patch_extraction.ipynb
2. pipeline.ipynb

`patch_extraction.ipynb` was utilized to extract the patches (both for train and test) out of the original .tif files. For each patch, a corresponding unique .json file is constructed containing the annotations for that patch (i.e. the location of inflammatory cells). At the top of this notebook filepath variables are specified. It is important to change `root_folder` to your local directory in which the data is stored. Assuming an identical folder structure, the rest of the code should work automatically. Separate sections are implemented for extracting the training patches (from pas-diagnostics, pas-original, pas-cpg) and testing patches (from pas-cpg), respectively. Within each section, variables can be adjusted as desired (e.g. `NUM_PATCHES_PER_FILE`)

In `pipeline.ipynb`, the general pipeline is implemented wherein the model is trained and evaluated. On the top of the notebook, there is one cell with global variables that should be adjusted accordingly. It is important to note that the current implementation is structured for Kaggle usage, therefore, certain aspects might warrant slight alterations. The `..._DIR` variables specify the path to the previously extracted patches with corresponding annotation files.


## License
This project is licensed under the MIT License — see the LICENSE file for details.


## Contact
For any inquiries, please email luuk.neervens@ru.nl
