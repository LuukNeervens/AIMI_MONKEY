# Automated Inflammatory Cell Detection using FasterRCNN for Kidney Transplantations: Adaption capabilities

In this work, we train a Faster R-CNN model on PAS-Original and PAS-Diagnostic data and evaluate its performance on PAS-CpG data, both zero-shot and after fine-tuning, to quantify adaptation gains for cross-domain inflammatory cell detection.

## Authors

- **Femke Aminetzah** — femke.aminetzah@ru.nl
- **Martina Baricocchi** — martina.baricocchi@ru.nl  
- **Lisanne Huisman** — lisanne.huisman@ru.nl  
- **Luuk Neervens** — luuk.neervens@ru.nl  






## About

This project focuses on the development and evaluation of a deep learning pipeline for automated detection of inflammatory cells in kidney transplant biopsies using histopathological slides. Specifically, a Faster R-CNN object detection model is implemented which is trained on PAS-Original and PAS-Diagnostic datasets, and test its performance on the PAS-CpG domain.

Our aim is to investigate the cross-domain adaptability of detection models in digital pathology — a crucial step toward reliable and scalable clinical deployment. By evaluating both zero-shot performance and performance after fine-tuning on PAS-CpG, we quantify the gains achievable through domain adaptation.

This tool could support pathologists by automating part of the labor-intensive cell detection process, improving efficiency and consistency in diagnostic workflows for kidney transplant monitoring.

## Usage

The final product was implemented utilizing two notebooks: 
1. `patch_extraction.ipynb`
2. `pipeline.ipynb`

`patch_extraction.ipynb` was utilized to extract the patches (both for train and test) out of the original .tif files. For each patch, a corresponding unique .json file is constructed containing the annotations for that patch (i.e. the location of inflammatory cells). At the top of this notebook filepath variables are specified. It is important to change `root_folder` to your local directory in which the data is stored. Assuming an identical folder structure, the rest of the code should work automatically. Separate sections are implemented for extracting the training patches (from pas-diagnostics, pas-original, pas-cpg) and testing patches (from pas-cpg), respectively. Within each section, variables can be adjusted as desired (e.g. `NUM_PATCHES_PER_FILE`)

In `pipeline.ipynb`, the general pipeline is implemented wherein the model is trained and evaluated. On the top of the notebook, there is one cell with global variables that should be adjusted accordingly. It is important to note that the current implementation is structured for Kaggle usage, therefore, certain aspects might warrant slight alterations. The `..._DIR` variables specify the path to the previously extracted patches with corresponding annotation files.


## License
This project is licensed under the MIT License — see the LICENSE file for details.


## Contact
For any inquiries, please email luuk.neervens@ru.nl
