# Vietnamese-text-classification
Finetune e5 base multilingual with synthetic vietnamese students feedback corpus (Torch and Tensorflow 2)

# Introduction
## Dataset
Synthetic-vietnamese-students-feedback-corpus Dataset is downloaded from [kaggle](https://www.kaggle.com/datasets/toreleon/synthetic-vietnamese-students-feedback-corpus/data)

This Dataset included student feedback with sentiment and topic of this feedback. The dataset is balanced with 8k training samples and 2k testing samples. 

Almost all feedback is short (longer feedback has 48 words).

## Pretrained model

[Multilingual e5 base](https://huggingface.co/intfloat/multilingual-e5-base) is initialized from xlm-roberta-base and continually trained on a mixture of multilingual datasets. It supports 100 languages from xlm-roberta (then they support Vietnamese xD), but low-resource languages may see performance degradation. This model is trained with 2 stages:

- Initialization: xlm-roberta-base
- First stage: contrastive pre-training with weak supervision
- Second stage: supervised fine-tuning

In my experience, this model will act very good in many public and secret dataset I tried.

# Motivation

Because text classification is a common task I need to do it a lot of time and I can reuse this code (just change the dataset). Previously, I only saved the code locally and didn't clean the code, so it was difficult to find and take advantage of the old code (I had to re-read the old code). I've also lost data with many important projects so I need to back it up to reuse and improve more easily.

# How to use it

Just run all my notebook, you can change, reuse and improve my code with other dataset:
- PyTorch code: [synthetic_vietnamese_students_feedback_corpus.ipynb](synthetic_vietnamese_students_feedback_corpus.ipynb)
- Tensorflow 2 code: [tf_synthetic_vietnamese_students_feedback_corpus2.ipynb](tf_synthetic_vietnamese_students_feedback_corpus2.ipynb)

Note that tensorflow changes so much with each update (the later version maybe bug with my code)

# Result

With both PyTorch and Tensorflow 2, I can achieve ~90% accuracy for sentiment and ~97% accuracy for topic.

# Requirements

- python 3>3.7
- torch
- tensorflow 2.15
