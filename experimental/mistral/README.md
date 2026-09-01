---
id: readme
lastUpdated: 2026-02-25
owner: dipikasikka1@gmail.com
title: Mistral-format model compression (experimental)
type: mistral
description: Learn how to quantize or compress Mistral-format models that lack a Hugging Face model definition (such as Devstral-Small, Magistral-Small, or mistral-large-3) using the model_free_ptq entrypoint.
tags:
  - mistral
  - quantization
  - compression
  - model-free-ptq
  - experimental
  - ptq
---
# Mistral-format model compression (experimental)

To quantize mistral models which do not have a huggingface model definition such as `mistralai/Devstral-Small-2505`, `mistralai/Magistral-Small-2506`, and `mistralai/mistral-large-3`, please use the [`model_free_ptq`](/src/llmcompressor/entrypoints/model_free/) entrypoint.