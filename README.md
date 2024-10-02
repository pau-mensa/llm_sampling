# LLM Sampling

A repo to test various LLM sampling methods.

## Entropy sampling

Taken from the ideas and posts of @_xjdr, @doomslide and others. The idea is to sample based on the entropy and varentropy of the logits.

From what I've been able to test, the entropy and varentropy thresholds, which are by far the most important parameters, are very sensitive to other sampling parameters (top_k, min_p, top_p), so it does not make much sense to talk about what thresholds work better.

More and deeper studies are needed in order to extract some conclusions here, but it is a fun/interesting way to test model capabilities.

### Highlights

I kept record of some interesting outputs, just for fun. Note that I am gpu poor, so I haven't been able to test long or varied generations.

><|begin_of_text|>Which number is larger: 9.9 or 9.11? Wait! Let's think step by step: 9.9 = 9 + 0.9 9.11 = 9 + 0.11 9.9 is larger because 0.9 > 0.11.<|end_of_text|>

>"<|begin_of_text|>Which number is larger: 9.9 or 9.11? Are they the same Wait! Let's think step by step: 9.9 = 9 + 0.9 = 9.1 9.11 = 9 + 0.11 = 9.11 The numbers are the same.<|end_of_text|>"

>"<|begin_of_text|>Which number is larger: 9.9 or 9.11? Wait! Let's think step by step: First, 9.9 is larger than 9.11 because 9.9 has the greater value of the two numbers.<|end_of_text|>"

