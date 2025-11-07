# Abstractive Summarization of Academic Articles using SOTA Models (PEGASUS, T5, BART) in the Environmental Sciences Field
This is a project repo for DATASCI266: Natural Language Processing project.

## Abstract 

This project delves into the topic of abstractive text summarization. We aim to create a model that can accurately summarize scholarly journal articles, specifically in the environmental sciences discipline. We use three state-of-the-art models, PEGASUS, FLAN-T5, and BART models and fine-tune them to compare model performances.

## Directory

The below list explains the point of each folder and file within this repository:
- dataset_to_df.ipynb: notebook used for the conversion of all files pulled from API into a single, cleaned file.
- model_evaluation.ipynb: notebook used for the evaluation of all models and general EDA of model performance.
- modeling_BART.ipynb: notebook used for the summary generation of the BART models, both baseline and finetuned. Also includes the actual fine tuning of the BART model.
- modeling_pegasus.ipynb: notebook used for the summary generation of both Pegasus models, both baseline and finetuned. Also includes the actual fine tuning of the Pegasus model.
- modeling_t5flan.ipynb: notebook used for the summary generation of of the t5 models, both baseline and finetuned.
- modeling_t5flan_finetuned.ipynb: creation of the t5 finetined model.
- parse_data_param.ipyb: parameterized notebook to dynamically get papers and download and convert them to CSV files for modeling.

## Motivation

Environmental science knowledge is critical for public awareness due to rising climate concerns. However, they are often out of reach to the public due to difficulty of access and difficulty of understanding for non-experts. Summarization models can bridge this gap, providing easy-to-understand insights from scholarly content. 

Our objective is to create a summarization model from vast publicly available scholarly articles and acandemic journals that can be adapted to create effective abstractive summarization for the environmental sciences domain. We explore multiple pre-trained models and finetune them to compare their effectiveness. 

## Dataset

We use the Semantic Scholar Open Research Corpus (S2ORC) which consists of 81.1 million English academic paper spanning many disciplines. By accessing the API directly provided through the corpus, we identify a subset of 4,160 articles in the env sci field. Detailed code for API, parsing, and cleaning data can be found in the code repository. 

## Models 

We experiment with and finetune the following pre-trained models:

- PEGASUS: Transformer-based encoder-decoder, excellent for abstractive summarization with academic text
- FLAN-T5: Instruction-tuned transformer, modeling different levels of summarization on prompt complexity
    - Level 1: "Summarize: "
    - Level 2: "Summarize this scholarly article: "
    - Level 3: "Summarize this scholarly article for someone that wants to learn about environmental science: "
 - BART: Sequence-to-sequence auto-encoder, known for robust generative capabilities

**Methods**

- Baseline: Pre-trained models evaluated out-of-the-box
- Finetuned: All models fine-tuned using the academic dataset; training scripts can be found in the code repo
- Evaluation: ROUGE, METEOR, BERTScore metrics are applied to measure summarization scores, and human evaluation is added for more detailed scoring

## Results

<img width="742" height="358" alt="image" src="https://github.com/user-attachments/assets/bd476ebf-7c11-462e-89ac-1705ff0d1882" />
<img width="635" height="360" alt="image" src="https://github.com/user-attachments/assets/c945df5a-65da-490d-a07c-68dffaa2efde" />

Due to model parameter restrictions largely due to limited resources, we make a choice to summarize on a more concise length. As a result, semantic matching of abstracts provided (to evaluate) do not appear to show high scores. However, human evaluation shows that fine-tuned models show impressive summarization ability not apparent with the scores. For example:

<img width="825" height="359" alt="image" src="https://github.com/user-attachments/assets/589e15e5-36a6-4d22-b82d-622e62f97fdb" />

The highest scoring models across the evaluation metrics in the fine-tuned FLAN-T5 Level 3, while the highest scoring human evaluated model was the PEGASUS.
