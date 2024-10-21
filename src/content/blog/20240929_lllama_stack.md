---
title: 'Adventures with the Llama Stack'
slug: 'adventures-llama-stack'
description: 'Concerning my efforts to work with Llama Stack'
pubDate: 'September 29, 2024'
---
Meta just released version 3.2 of their Llama model, and the announcement is [here](https://ai.meta.com/blog/llama-3-2-connect-2024-vision-edge-mobile-devices/). One item that grabbed my attention was the release of Llama Stack, whose goal is to " simplify the way developers work with Llama models in different environments". The Github page is [here](https://github.com/meta-llama/llama-stack).

I've been accessing Llama models using the [Transformers library](https://huggingface.co/docs/transformers/en/index) from HuggingFace. But when I saw the Llama Stack announcement, I figured I'd give it a try. So far, I'm impressed with the ambition but I'm disappointed with the execution. The software is still pretty buggy.

First of all, Llama Stack isn't a programming toolset like the Transformers library. It provides a command-line utility (`llama`) that makes it possible to download and use models. In addition, it doesn't just access the model in code&mdash;it creates a server that listens for prompts, submits prompts to the model, and provides responses. This requires Anaconda or Docker, and because I've had awful experiences with Anaconda, I invoke it using Docker.

Once the model is downloaded, the utility can be used in three main ways:
* `llama stack build` &mdash; creates the Dockerfile and builds the Docker image for the server
* `llama stack configure` &mdash; creates a YAML file containing the server's operating parameters
* `llama stack run` &mdash; creates a container from the image and launches the server

The first and second steps are straightforward, but when I run `llama stack run`, I get errors involving missing configuration files. I've managed to clear up some errors by setting environment variables, but then more errors crop up. I have yet to successfully run a Llama server.

I look forward to using the Llama Stack at some point. But for now, I'll stick to HuggingFace.
