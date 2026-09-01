---
id: readme
lastUpdated: 2026-04-02
owner: kylesayrs@gmail.com
title: 'Attention Quantization in LLM Compressor #'
type: quantization_attention
description: Learn how to apply static per-head FP8 attention quantization to a model with LLM Compressor's QuantizationModifier, which also implicitly quantizes the kv cache.
tags:
  - quantization
  - attention
  - fp8
  - kv-cache
  - llm-compressor
---
# Attention Quantization in LLM Compressor #
LLM Compressor supports applying static attention quantization to models

## Per-Head FP8 Attention Example ##
For an example applying attention quantization, see [llama3_attention.py](/examples/quantization_attention/llama3_attention.py).

```python
recipe = QuantizationModifier(
    config_groups={
        "attention": QuantizationScheme(
            targets=["LlamaAttention"],
            input_activations=QuantizationArgs(
                num_bits=8, type="float", strategy="attn_head"
            ),
        )
    }
)
```

Accuracy should be almost identical to the base model for FP8 attention.
Note that attention quantization also implicitly applies kv cache quantization with the same quantization arguments.
