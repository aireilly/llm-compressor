---
id: readme
lastUpdated: 2026-03-03
owner: '@kylesayrs'
title: 'Sequential Pipeline #'
type: sequential
description: Learn how to compress models with GPTQModifier or SparseGPTModifier using the sequential data pipeline for layer-by-layer calibration and quantization.
tags:
  - sequential
  - pipeline
  - gptq
  - sparsegpt
  - quantization
  - calibration
  - compression
---
# Sequential Pipeline #
The sequential pipeline is a data pipeline, primarily used for compressing models with the
[GPTQModifier](/src/llmcompressor/modifiers/gptq/base.py) or the
[SparseGPTModifier](/src/llmcompressor/modifiers/pruning/sparsegpt/base.py).
