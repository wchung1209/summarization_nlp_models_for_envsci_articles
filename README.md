# Abstractive Summarization of Academic Articles using SOTA Models (PEGASUS, T5, BART) in the Environmental Sciences Field
This is a project repo for DATASCI266: Natural Language Processing project.

## Abstract 

This project delves into the topic of abstractive text summarization. We aim to create a model that can accurately summarize scholarly journal articles, specifically in the environmental sciences discipline. We use three state-of-the-art models, PEGASUS, FLAN-T5, and BART models and fine-tune them to compare model performances.

## Directory
-
The below list explains the point of each folder and file within this repository:
- dataset_to_df.ipynb: notebook used for the conversion of all files pulled from API into a single, cleaned file.
- model_evaluation.ipynb: notebook used for the evaluation of all models and general EDA of model performance.
- modeling_BART.ipynb: notebook used for the summary generation of the BART models, both baseline and finetuned. Also includes the actual fine tuning of the BART model.
- modeling_pegasus.ipynb: notebook used for the summary generation of both Pegasus models, both baseline and finetuned. Also includes the actual fine tuning of the Pegasus model.
- modeling_t5flan.ipynb: notebook used for the summary generation of of the t5 models, both baseline and finetuned.
- modeling_t5flan_finetuned.ipynb: creation of the t5 finetined model.
- parse_data_param.ipyb: parameterized notebook to dynamically get papers and download and convert them to CSV files for modeling.