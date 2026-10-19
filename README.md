### Qirun Li

I train language models and measure what the training actually changes. Quant trader since 2018 (co-founded NV Capital); full-time on LLM training research since August 2026. The habits came with me: the prediction is written down before the run, every result has a noise floor, one variable changes at a time.

Looking for a model-training role at an AI lab: pretraining, post-training (including RL) or alignment. [LinkedIn](https://www.linkedin.com/in/qirunli/) · [Hugging Face](https://huggingface.co/icedduck) · qli858246@gmail.com

#### Research

**1. [LLM from scratch → the aha moment → a coding agent](https://github.com/bethehand/lab1-llm-scratch-to-aha-moment-to-coding-agent)** · complete · [report](https://bethehand.github.io/lab1-llm-scratch-to-aha-moment-to-coding-agent/en/) ([中文](https://bethehand.github.io/lab1-llm-scratch-to-aha-moment-to-coding-agent/zh/)) · [checkpoints](https://huggingface.co/icedduck)

Fifteen controlled experiments on 4× RTX 4090: pretraining 95M/201M models from scratch, SFT, GRPO on GSM8K, the R1 "aha moment" on Countdown (pass@1 .02 → .75), and a four-stage coding-agent RL curriculum. RL raised pass@1 at every stage while pass@32 barely moved: it reorders what the model can already do. Taking the visible tests away costs the RL agent 16 points, all of it in the fix loop; `bench_observation_price.py` measures that price on any Hugging Face model.

**2. [looped-scaling](https://github.com/bethehand/looped-scaling)** · complete, paper draft for TMLR · [report](https://github.com/bethehand/looped-scaling/blob/main/docs/report.md) ([中文](https://github.com/bethehand/looped-scaling/blob/main/docs/report.zh.md)) · [paper](https://github.com/bethehand/looped-scaling/blob/main/paper/paper.pdf)

A pre-registered scaling study of looped (recurrent-depth) transformers: 232 language models at 10M–160M parameters and 135 small models on a synthetic task, hypotheses frozen before the first run. On web text a loop buys parameter efficiency that grows with model size (worse than dense at 10M, better from 40M on), not compute efficiency anywhere measured, and it costs 2.4–2.5× the decoding time. On a task that needs serial steps it buys depth that extends at inference: one chain step per loop, longer chains with more loops, and for most training regimes the model's own confidence tells it when to stop.

**3. [olmo-rlvr-side-effects](https://github.com/bethehand/olmo-rlvr-side-effects)** · in progress · setup notes and open-instruct contributions in [olmo-hands-on](https://github.com/bethehand/olmo-hands-on)

Which RLVR training data changes what, outside the training domain? Ai2 publishes every post-training stage of Olmo 3 Think and its eval code, so a behaviour can be traced to the stage that changed it, measured the way Ai2 measures it; which data causes it is then tested with small open-instruct runs that change one data type at a time. So far: Ai2's safety numbers for the Olmo 3 7B Think stages replicated within 1 point of Table 52, with run-to-run noise ([open-instruct #1964](https://github.com/allenai/open-instruct/issues/1964#issuecomment-6247442515)); answer length across the SFT, DPO and RL stages, where DPO adds most of it and Olmo 3.1's longer RL adds about 10% that its new default system prompt hides ([#2002](https://github.com/allenai/open-instruct/issues/2002#issuecomment-6256732503)). Independent work, not affiliated with Ai2.

