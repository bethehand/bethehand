### Qirun Li

I train language models and measure what the training actually changes. Quant trader since 2018 (co-founded NV Capital); full-time on LLM training research since August 2026. From trading I kept three habits: write the prediction down before the run, put a noise floor on every result, change one thing at a time.

Looking for a model-training role at an AI lab: pretraining, post-training/RL or alignment. [LinkedIn](https://www.linkedin.com/in/qirunli/) · [Hugging Face](https://huggingface.co/icedduck) · qli858246@gmail.com

#### Research

**1. [LLM from scratch → the aha moment → a coding agent](https://github.com/bethehand/lab1-llm-scratch-to-aha-moment-to-coding-agent)** · complete · [report](https://bethehand.github.io/lab1-llm-scratch-to-aha-moment-to-coding-agent/en/) ([中文](https://bethehand.github.io/lab1-llm-scratch-to-aha-moment-to-coding-agent/zh/))

Fifteen controlled experiments on 4× RTX 4090, from pretraining 95M/201M models through GRPO and the R1 "aha moment" (Countdown pass@1 .02 → .75) to an RL-trained coding agent. RL raised pass@1 at every stage while pass@32 barely moved: it reorders what the model can already do.

**2. [looped-scaling](https://github.com/bethehand/looped-scaling)** · complete, paper draft for TMLR · [report](https://github.com/bethehand/looped-scaling/blob/main/docs/report.md) ([中文](https://github.com/bethehand/looped-scaling/blob/main/docs/report.zh.md)) · [paper](https://github.com/bethehand/looped-scaling/blob/main/paper/paper.pdf)

A pre-registered scaling study of looped (recurrent-depth) transformers: 232 language models at 10M–160M. On web text a loop buys parameter efficiency that grows with size (better than dense from 40M on) but no compute efficiency at any scale measured, and decoding is 2.4–2.5× slower. On a synthetic task that needs serial steps it buys depth that extends at inference: more loops, longer chains.

**3. [olmo-rlvr-side-effects](https://github.com/bethehand/olmo-rlvr-side-effects)** · in progress · setup notes and contributions in [olmo-hands-on](https://github.com/bethehand/olmo-hands-on)

Which RLVR training data changes what, outside its own domain? I trace each change to the Olmo 3 post-training stage that made it, measured the way Ai2 measures it; next, small open-instruct runs will test which data causes it. So far: Ai2's safety numbers for the Olmo 3 7B Think stages, replicated within 1 point, plus their run-to-run noise ([open-instruct #1964](https://github.com/allenai/open-instruct/issues/1964#issuecomment-6247442515)); answer length, where DPO adds most of it ([#2002](https://github.com/allenai/open-instruct/issues/2002#issuecomment-6256732503)). Independent work, not affiliated with Ai2.
