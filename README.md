
# Textual Emotion-Cause Pair Extraction in Conversations

## Overview
This project was part of SemEval 2024 Task-3 (Subtask 1), focusing on developing a model to extract emotion-cause pairs from conversations. The dataset used was derived from the sitcom "FRIENDS." The primary objective was to predict the emotion expressed in a dialogue and identify the cause of that emotion from the conversation context.

## Dependencies
- Python 3.11.0
- TensorFlow 2.16.1
- RoBERTa pre-trained model
- Logistic Regression model

## Project Description
The project involves using two different models to predict the emotion and identify the corresponding cause in the given conversation data:
1. **Emotion Prediction:** A Logistic Regression model is used to predict the emotion expressed in the dialogue.
2. **Cause Extraction:** The problem of identifying the cause for the predicted emotion is treated as a question-answering task using a pre-trained RoBERTa model. The predicted emotion from the Logistic Regression model serves as the "question," and the conversation text provides the "context." The RoBERTa model then identifies the cause from the context.

## Dataset
The dataset provided by SemEval consists of conversations from the sitcom "FRIENDS," formatted as JSON files. 

- **Training Data:** 
  - Conversations: 1374 
  - Utterances: 13619 
- **Evaluation Data:** 
  - Conversations: 341 
  - Utterances: 3101 

### Structure
- `conversation_ID`: Unique identifier for the conversation.
- `conversation`: List of utterances exchanged in the conversation.
- `utterance_ID`: Unique identifier for each utterance.
- `text`: Text content of the utterance.
- `speaker`: Speaker who uttered the text.
- `emotion`: Emotion associated with the utterance.
- `emotion-cause_pairs`: List of emotion-cause pairs extracted from the conversation.

## Methodology
### Emotion Classification
- **Model:** Logistic Regression
- **Features:** TFIDF vectors of the utterances
- **Accuracy:** 72%

### Cause Extraction
- **Model:** Pre-trained RoBERTa
- **Approach:** The emotion predicted by the Logistic Regression model is used as a query to the RoBERTa model, which then extracts the cause from the conversation context.
- **Accuracy:** 60%

## Project Architecture

![Project Architecture](https://github.com/Shruti2301/Textual-Emotion-Cause-Pair-Extraction-in-Conversations/assets/71042986/16426e98-717c-49fe-bd12-b0c8f41f815f)

## Results
- **Emotion and Cause Interdependence:** The tasks of emotion extraction and cause extraction are not mutually independent. Knowing the emotion can help in identifying the cause and vice versa.
- **Performance Analysis:** Transformers like BERT and RoBERTa, although having lower accuracy in this limited data test, can capture complex relationships in text better than Logistic Regression, which focuses on more interpretable features.

## Motivation
- To advance emotionally intelligent systems
- To achieve contextual understanding in conversations
- To provide granular emotional analysis in text
- To potentially integrate with other modalities in future projects

## Citation
If you use this work in your research, please cite:

@ARTICLE{wang2023multimodal,
author={Wang, Fanfan and Ding, Zixiang and Xia, Rui and Li, Zhaoyu and Yu, Jianfei},
journal={IEEE Transactions on Affective Computing},
title={Multimodal Emotion-Cause Pair Extraction in Conversations},
year={2023},
volume={14},
number={3},
pages={1832-1844},
doi={10.1109/TAFFC.2022.3226559}
}

@InProceedings{wang2024SemEval,
author={Wang, Fanfan and Ma, Heqing and Xia, Rui and Yu, Jianfei and Cambria, Erik},
title={SemEval-2024 Task 3: Multimodal Emotion Cause Analysis in Conversations},
booktitle={Proceedings of the 18th International Workshop on Semantic Evaluation (SemEval-2024)},
month={June},
year={2024},
address={Mexico City, Mexico},
publisher={Association for Computational Linguistics},
pages={2022--2033},
url={https://aclanthology.org/2024.semeval2024-1.273}
}


