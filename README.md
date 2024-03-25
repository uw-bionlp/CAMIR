# Corpus of Annotated Medical Imaging Reports (CAMIR)

Title: A Novel Corpus of Annotated Medical Imaging Reports and Information Extraction Results Using BERT-based Language Models (accepted @ LREC-COLING 2024)
Authors: Namu Park, Kevin Lybarger, Giridhar Kaushik Ramachandran, Spencer Lewis, Aashka Damani, Özlem Uzuner, Martin Gunn and Meliha Yetisgen

## Annotation Guidelines

 - The most recent version of the annotation guidelines for CAMIR: CAMIR_Annotation_Guidelines.pdf

## Dataset

 - De-identified dataset will be released upon the approval of the University of Washington IRB 

# PL-Marker++ for CAMIR

Source code for PL-Marker++ 
Example input and output will be added upon IRB approval.
PL-Marker++, which is the augmented version of PL-Marker, provides the classification of subtypes for extracted entities.

Original PL-Marker implementation can be found at https://github.com/thunlp/PL-Marker

## Step 1. Create virtual enviroments

 - Create 2 seperate Conda environments (both using python=3.8.18) using **mspert_req.txt** (mspert) and **plmarker_req.txt** (plmarker).
 conda create -n mspert_test python=3.8.18
 conda activate mspert_test
 pip install -r ./mspert_req.txt

 conda create -n plmarker_test python=3.8.18
 conda activate plmarker_test
 pip install -r ./plmarker_req.txt
 pip install --editable ./transformers

## Step 2. Put radiology reports in "sample_data" folder

 - Input radiology reports should be located in ./sample_data using .txt file format

## Step 3. Run shell script

 - bash ./run_plmarker.sh
   -> This shell script includes entity extraction, subtype extraction and relation extraction.
 - Final output file with entity, subtype and relation information (will be added uppon IRB approval) is "./example_input_ent_pred_test_normalized_with_RE.json"
    - Output with only entity extraction can be found in "./incidentaloma_models/PL-Marker-incidentaloma-bertbase-45/example_input_ent_pred_test.json"
    - Output with entity+subtype extraction can be found in "./example_input_ent_pred_test_normalized.json"
 - All predictions are performed in sentence-level.
