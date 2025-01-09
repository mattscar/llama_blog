---
title: 'Byte Latent Transformers'
slug: 'byte_latent_transformers'
description: 'New type of transformer: byte latent transformer (BLT)'
pubDate: 'December 20, 2024'
---

Corporations have been spawning new types of LLMs at a frenzied pace, but they all have one common characteristic: they analyze and generate text in blocks called *tokens*. Llama models tokenize text using OpenAI's popular [Tiktoken](https://github.com/openai/tiktoken), which creates the token set (vocabulary) using byte pair encoding, or [BPE](https://en.wikipedia.org/wiki/Byte_pair_encoding).

I'd thought transformers needed tokenizers, but Meta FAIR released a fascinating paper entitled [Byte Latent Transformer: Patches Scale Better Than Tokens]. This introduces a new type of transformer called the Byte Latent Transformer, which doesn't use a fixed vocabulary. Instead, it groups bytes into *patches* by computing how easy it is to predict the next byte. 

A byte latent transformer has three parts:
1. local encoder - map input bytes into input patches
2. local decoder - map output patches into output bytes
3. latent global transformer - transforms input patches into output patches 

It looks like the primary advantage of using patches is that they can grow much larger than tokens. This allows the transformer to process more data with each operation. As stated in the paper:

>With BLT models, we can simultaneously increase model size and patch size while maintaining the same
training and inference flop budget and keeping the amount of training data constant.

The conclusion clarifies this further: 

>BLT models can match the performance of tokenization-based models like Llama 3 at scales up to 8B and 4T bytes, and can trade minor losses in evaluation metrics for up to 50% reductions in inference flops.

In other words, BLT models can grow without incurring significant penalties in inference time. Sounds incredible. It's probably too new for the upcoming Llama 4 models, but it might be employed in Llama 5.