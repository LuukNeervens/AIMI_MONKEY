# Automated Inflammatory Cell Detection using FasterRCNN for Kidney Transplantations: Adaption capabilities

In this work, we train a Faster R-CNN model on PAS-Original and PAS-Diagnostic data and evaluate its performance on PAS-CpG data, both zero-shot and after fine-tuning, to quantify adaptation gains for cross-domain inflammatory cell detection.

## Authors

- **Femke Aminetzah** — femke.aminetzah@ru.nl
- **Martina Baricocchi** — martina.baricocchi@ru.nl  
- **Lisanne Huisman** — lisanne.huisman@ru.nl  
- **Luuk Neervens** — luuk.neervens@ru.nl  

## About

This project investigates the automated detection of inflammatory cells in kidney transplant biopsies using histopathological whole slide images (WSIs). Accurate quantification of inflammation plays a critical role in diagnosing transplant rejection, yet manual cell annotation is time-consuming and subject to inter-observer variability.

To address this, we develop a pipeline based on Faster R-CNN, a state-of-the-art object detection model, and evaluate its performance across different data domains. The model is initially trained on the PAS-Original and PAS-Diagnostic datasets and then tested on the PAS-CpG domain to assess generalizability. We further analyze performance improvements through fine-tuning on PAS-CpG, enabling us to measure the benefits of cross-domain adaptation.

A last model is defined (i.e. model C) which is solely trained on PAS-CpG and tested on PAS-CpG, to measure baseline performance.

## Preprocessing

The workflow begins with the extraction of 256 by 256 sized patches from high-resolution `.tif` whole slide images using the `patch_extraction.ipynb` notebook. Each patch is paired with a corresponding `.json` annotation file that specifies ground-truth boxes for inflammatory cells. Patch generation is modular and configurable, allowing adjustment of parameters such as the number of patches per file and the specific dataset split (training or testing).



## Evaluation and Metrics
Model training and evaluation are performed in the `pipeline.ipynb` notebook. We assess performance using Intersection over Union (IoU) as a way to compute standard object detection metrics. These metrics include:

- Precision
- Recall
- F1-score 
- Free-Response Receiver Operating Characteristic curves(FROC)
  
These metrics allow us to quantify the model’s detection accuracy, domain transferability, and gains from fine-tuning.

Ultimately, this project contributes to the development of more robust, adaptable AI tools in computational pathology that can assist clinicians in identifying inflammation across diverse staining protocols and imaging variations.

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
