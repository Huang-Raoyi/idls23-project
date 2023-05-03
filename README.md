# IDLS23 Project

**ChatGPT-Empowered Summarization Model**

Team Members: 
* Cathy Huang (raoyih)
* Yuanchen Bai (ybai2)
* Kexuan Cai (kexuanc)
* Meghna Iyengar (maiyenga)

TA Mentor:
* Josh Li (liangzel)

## Directory
```
Make a GitHub folder structure like:
├── README.md
├── Baseline Models
│   ├── BART
│   ├── Peagus
│   ├── Prophetnet
│   └──  cnn_dailymail (test dataset)
│   
├── Data
└── BART-finetune-distill
    └── BART-large-full-GPT (models fine-tuned on full GPT data and some test results)
    ├── Codes for finetuning and distillation
    └── Test Result
```    
    
## Documents 
- Model survey: https://docs.google.com/spreadsheets/d/1oaH8wEdbP3o2mx_IcusdNBpudNhHU4CJLOcceRNJIzE/edit?usp=sharing
- Interim report: https://drive.google.com/file/d/1i99Ep1RBRl5rXy9Am9M4TAK0smTetrps/view?usp=sharing
- Test result: https://docs.google.com/spreadsheets/d/1nuIVUUzraZFVFtB-UX6lMN4AJAy_MSjiSIaOHfwEl0M/edit?usp=sharing
- Final presentation slides: https://docs.google.com/presentation/d/19S5laqod3Y4nArRCuUQ_m1lVQoqlbo3jOy2DF1JBu9Y/edit?usp=share_link
(Please log into your CMU account before view those documents)

# Experiment

## Data
* In this study, we used the Samsum dataset.
* From Samsum dataset, we created the hybrid dataset and full-ChatGPT dataset by OpenAI ChatGPT API.
    * Hybrid dataset: created by replace half of the summaries by the summary outputs of ChatGPT given the Samsum dialogues
    * ChatGPT dataset: created by replace all of the summaries by the summary outputs of ChatGPT given the Samsum dialogues
* Evaluate the models on Samsum evaluation dataset and DialogSum dataset.


## Evaluation
* ROUGE-1, ROUGE-2, ROUGE-L - Lexical similarity
* BERTScore - Semantic similarity


## Model 

### GPT3.5
```
Baseline: gpt-3.5-turbo
Temperature = 0.7 (default)
Prompt: 
[
  {"role": "user", "content": f"{user_input_dialogues}."}
]
```