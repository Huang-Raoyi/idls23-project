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
│   ├── BART.ipynb
│   ├── Peagus.ipynb
│   └── Prophetnet.ipynb
├── Data
│   ├── Crawler.ipynb
│   └── Partial Crawled data
└── BART-finetune-distill
│   ├── Finetune.ipynb
│   └── Distilled.ipynb
└── Test (Test results on DialogSum or Samsum evaluation datasets)
```    
    
## Documents 
- [Model survey](https://docs.google.com/spreadsheets/d/1oaH8wEdbP3o2mx_IcusdNBpudNhHU4CJLOcceRNJIzE/edit?usp=sharing)
- [Interim report](https://drive.google.com/file/d/1HogyOlWi5YUpRtdBvv9H9kuN8HBR8WEr/view?usp=sharing)
- [Test result](https://docs.google.com/spreadsheets/d/1nuIVUUzraZFVFtB-UX6lMN4AJAy_MSjiSIaOHfwEl0M/edit?usp=sharing)
- [Final presentation slides](https://docs.google.com/presentation/d/19S5laqod3Y4nArRCuUQ_m1lVQoqlbo3jOy2DF1JBu9Y/edit?usp=share_link)
- [Model-full-ChatGPT](https://drive.google.com/drive/folders/1Z41xhxxcJdfDhto5YQpCBER0w4kYieiE?usp=sharing): models are too large to be uploaded
- [full-ChatGPT-dataset](https://drive.google.com/file/d/1uWdBBvrRNE23hsJVmVlRHZudjmccH4e8/view?usp=sharing): crawled and preprocessed full dataset is too large to be uploaded

(Please log into your CMU account before view those documents)

# Experiment

## Data
* In this study, we used the [Samsum dataset](https://huggingface.co/datasets/samsum).
* From Samsum dataset, we created the hybrid dataset and full-ChatGPT dataset by OpenAI ChatGPT API.
    * Hybrid dataset: created by replace half of the summaries by the summary outputs of ChatGPT given the Samsum dialogues
    * ChatGPT dataset: created by replace all of the summaries by the summary outputs of ChatGPT given the Samsum dialogues
* Evaluate the models on Samsum evaluation dataset and [DialogSum dataset](https://huggingface.co/datasets/knkarthick/dialogsum).


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
