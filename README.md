---
language: ja
thumbnail: https://github.com/rinnakk/japanese-gpt2/blob/master/rinna.png
tags:
- ja
- japanese
- gpt2
- text-generation
- lm
- nlp
license: mit
datasets:
- cc100
---

# japanese-gpt2-medium

![rinna-icon](./rinna.png)

This repository provides a medium-sized Japanese GPT-2 model. The model is provided by [rinna](https://corp.rinna.co.jp/).

# How to use the model

*NOTE:* Use `T5Tokenizer` to initiate the tokenizer.

~~~~
from transformers import T5Tokenizer, AutoModelForCausalLM

tokenizer = T5Tokenizer.from_pretrained("rinna/japanese-gpt2-medium")
tokenizer.do_lower_case = True  # due to some bug of tokenizer config loading

model = AutoModelForCausalLM.from_pretrained("rinna/japanese-gpt2-medium")
~~~~

# Model architecture
A 24-layer, 1024-hidden-size transformer-based language model.

# Training
The model was trained on [Japanese CC-100](http://data.statmt.org/cc-100/ja.txt.xz) to optimize a traditional language modelling objective on 8\\*V100 GPUs for around 30 days. It reaches around 18 perplexity on a chosen validation set from the same data.

# Tokenization
The model uses a [sentencepiece](https://github.com/google/sentencepiece)-based tokenizer, the vocabulary was trained on the Japanese Wikipedia using the official sentencepiece training script.

# Licenese
[The MIT license](https://opensource.org/licenses/MIT)
