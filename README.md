# TITLE

In this work, we train a Faster R-CNN model on PAS-Original and PAS-Diagnostic data and evaluate its performance on PAS-CpG data, both zero-shot and after fine-tuning, to quantify adaptation gains for cross-domain inflammatory cell detection.

---

## Table of Contents

- [About](#about)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Configuration](#configuration)  
- [Examples](#examples)  
- [API Reference](#api-reference)  
- [Contributing](#contributing)  
- [Tests](#tests)  
- [FAQ](#faq)  
- [License](#license)  
- [Contact](#contact)  
- [Acknowledgements](#acknowledgements)

---

## About

Detailed description of the project.  
Explain the motivation, what problem it solves, and why it’s useful.

---

## Usage

The final product was implemented utilizing two notebooks: 
1. patch_extraction.ipynb
2. pipeline.ipynb

`patch_extraction.ipynb` was utilized to obtain extract the patches (both for train and test) out of the original .tif files. In the top of this notebook 

```bash
# Example for Python
pip install project-name
