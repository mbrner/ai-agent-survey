# ReAct: Synergizing Reasoning and Acting in Language Models 

**Link:** [Paper](https://openreview.net/forum?id=WE_vluYUL-X)

**Authors:** Shunyu Yao[^1], Jeffrey Zhao[^2], Dian Yu[^2], Nan Du[^2], Izhak Shafran[^2], Karthik Narasimhan[^1], Yuan Cao[^2]

[^1]: Department of Computer Science, Princeton University
[^2]: Google Research, Brain Team

The paper explores the use of large language models (LLMs) for generating both reasoning traces and task-specific actions in an interleaved manner. This approach is applied to various language and decision-making tasks. The model, named REACT, helps in inducing, tracking, and updating action plans as well as handling exceptions. It also interfaces with and gathers additional information from external sources like knowledge bases or environments. The authors claim that REACT outperforms state-of-the-art baselines and improves human interpretability and trustworthiness.