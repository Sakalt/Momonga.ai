
# japanese-gpt2-medium

![rinna-icon](./rinna.png)

This repository provides a medium-sized Japanese GPT-2 model trained on [Japanese CC-100](http://data.statmt.org/cc-100/ja.txt.xz). The model is provided by [rinna](https://corp.rinna.co.jp/).

# Use the model

*NOTE:* Use `T5Tokenizer` to initiate the tokenizer.

~~~~
from transformers import T5Tokenizer, AutoModelForCausalLM

tokenizer = T5Tokenizer.from_pretrained("rinna/japanese-gpt2-medium")

model = AutoModelForCausalLM.from_pretrained("rinna/japanese-gpt2-medium")
~~~~