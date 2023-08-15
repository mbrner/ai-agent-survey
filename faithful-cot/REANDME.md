<!--- Created using: ... --->
<!--- Reviewed: False --->
# Faithful Chain-of-Thought Reasoning

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2301.13379v2)
- Code: N/A

**Authors**: Qing Lyu, Shreya Havaldar, Adam Stein, Li Zhang, Delip Rao, Eric Wong, Marianna Apidianaki, Chris Callison-Burch

## Summary

**TL;DR: The study introduces Faithful CoT, a two-stage framework for reasoning tasks, which outperforms traditional methods in accuracy and reliability across diverse domains, achieving state-of-the-art performance on 7 out of 10 datasets tested.**

The study examines the Chain-of-Thought (CoT) prompting method used to enhance Language Models' (LM) performance on complex reasoning tasks. However, the generated reasoning chain does not necessarily reflect the model's faithfulness in reaching the answer, which can be misleading in high-stake applications.

### Approach

The researchers introduce Faithful CoT, a two-stage framework for reasoning tasks. The first stage translates a natural language query into a symbolic reasoning chain using an LM, and the second stage uses a deterministic solver to convert the reasoning chain into an answer.

### Results

The Faithful CoT was tested on 10 reasoning datasets from 4 diverse domains. It outperformed traditional CoT prompting on 9 out of the 10 datasets, with an average accuracy gain of 4.4 on Math Word Problems, 1.9 on Planning, 4.0 on Multi-hop Question Answering (QA), and 18.1 on Logical Inference, under greedy decoding.

### Conclusion

The Faithful CoT, when combined with self-consistency decoding, achieved new state-of-the-art few-shot performance on 7 out of the 10 datasets. This demonstrates a strong synergy between faithfulness and accuracy, providing a more reliable interpretability of the model's predictions.
