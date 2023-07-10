# Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning by Large Language Models 

**Link:** [Paper](https://arxiv.org/abs/2305.04091)

**Authors:** Lei Wang[^1], Wanyu Xu[^2], Yihuai Lan[^3], Zhiqiang Hu[^3], Yunshi Lan[^4], Roy Ka-Wei Lee[^3], Ee-Peng Lim[^1]

[^1]: Singapore Management University
[^2]: Southwest Jiaotong University
[^3]: Singapore University of Technology and Design
[^4]: East China Normal University

## Summary

The paper presents a new approach, termed Plan-and-Solve (PS) Prompting, to improve the reasoning capabilities of large language models (LLMs). The PS Prompting method addresses the limitations of Zero-shot Chain-of-Thought (Zero-shot-CoT) by dividing the task into smaller subtasks, planning and solving them sequentially. To tackle calculation errors and improve the quality of reasoning steps, the authors extend PS prompting with more detailed instructions, forming PS+ prompting. The experimental results indicate that PS and PS+ prompting methods significantly outperform Zero-shot-CoT, match or surpass Zero-shot-Program-of-Thought Prompting, and have comparable performance with 8-shot CoT prompting on math reasoning problems.