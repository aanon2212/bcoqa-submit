# BCoQA
This repository contains the BCoQA dataset and evaluation scripts, which are part of our research on developing a robust Context-based Conversational Question Answering (CCQA) system for the Bangla language. The dataset is constructed by quality controlled machine translation and LLM based augmentation of established English CCQA datasets. The evaluation scripts provide a benchmark for assessing the performance of CCQA systems on the Bangla language.

The BCoQA dataset comprises over 14,000 conversations, featuring more than 140,000 question-answer pairs. Notably, the questions are conversational in nature, often requiring context from previous questions and answers to respond accurately. The answers are provided in free-form text, adding to the complexity and realism of the dataset.

## Table of Contents
- [Dataset](#dataset)
- [Evaluation](#evaluation)
- [Finetuning](#finetune)
- [Acknowledgement](#acknowledgement)

## Dataset

### Through JSON files
You can download the dataset directly from the following links to the JSON files:
- [Train Set](https://github.com/aanon2212/bcoqa-submit/raw/main/data/train.json?download=)
- [Valid Set](https://github.com/aanon2212/bcoqa-submit/raw/main/data/validation.json?download=)
- [Test Set](https://github.com/aanon2212/bcoqa-submit/raw/main/data/test.json?download=)

## Evaluation
To evaluate your model, go through the following steps:
- Save your model predictions: Save your model's output in the same JSON format as the [demo file](https://github.com/aanon2212/bcoqa-submit/raw/main/demo_output_bcoqa.json?download=).
- Run the evaluation script: Use the official evaluation [script](https://raw.githubusercontent.com/aanon2212/bcoqa-submit/main/bcoqa-eval.py?raw=true) to evaluate your model. To run the script, use the following command:
  ```
  python bcoqa-eval.py --test-file <path_to_test.json> --pred-file <path_to_predictions.json>.
  ```
## Finetune
There are various ways to build a good CCQA system. One simple approach is to fine-tune a model by adding the conversation history to the context. The [bt5-bcoqa-finetune.ipynb](https://github.com/aanon2212/bcoqa-submit/blob/main/bt5-bcoqa-finetune.ipynb) notebook demonstrates one of many ways to do this.

## Acknowledgement
We would like to extend our gratitude to the [CoQA](https://stanfordnlp.github.io/coqa/) and [QuAC](https://quac.ai/) teams for providing the original English datasets, which served as the foundation for our work. Additionally, we appreciate the CoQA team for sharing their base script, which we modified to create our own evaluation script. Their contributions have been invaluable to our project.
