---
title: 'Llama 4 News'
slug: 'llama-four-news'
description: 'Discussion of recent news regarding Llama 4'
pubDate: 'November 4, 2024'
---

Meta had a conference call last Wednesday, and while there were no major announcements, Mark Zuckerberg had interesting things to say about the upcoming Llama 4 models:

>We're training the Llama 4 models on a cluster that is bigger than 100k H100s or bigger than anything that I've seen reported for what others are doing. I expect that the smaller Llama 4 models will be ready first, and they’ll be ready, we expect sometime early next year, and I think that they're going to be a big deal on several fronts -- new modalities, capabilities, stronger reasoning, and much faster. It seems pretty clear to me that open source will be the most cost-effective, customizable, trustworthy, performant, and easiest-to-use option that is available to developers, and I'm proud that Llama is leading the way on this.

I'm particularly interested in the "easiest-to-use" claim. I still haven't successfully deployed a Llama Stack server, so I access Llama using HuggingFace's [Transformers library](https://huggingface.co/docs/transformers/en/index). If there was a way to perform inference using PyTorch, I'll use that in a heartbeat.

It still hurts to see that Nvidia's CUDA has become the *only* language for GPU computing. I spent years writing a book and a blog about OpenCL, and I gave a handful of presentations on the topic. But now OpenCL is as dead as ActionScript, and that's why Nvidia is in the [Dow Jones Industrial Average](https://www.investors.com/news/nvidia-to-join-dow-jones-industrial-average-replacing-intel/) instead of Intel.