<!--- Created using: ... --->
<!--- Based on: 100.0% of the Paper --->
<!--- Reviewed: False --->
# Reflexion: Language Agents with Verbal Reinforcement Learning

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2303.11366v3)
- Code: N/A

**Authors**: Noah Shinn, Federico Cassano, Beck Labash, Ashwin Gopinath, Karthik Narasimhan, Shunyu Yao

## Summary

**TL;DR: Reflexion, a novel framework for training large language models, uses linguistic feedback and episodic memory to improve learning efficiency and decision-making, demonstrating significant improvements across diverse tasks, though it struggles with tasks requiring extensive exploration and diversity, suggesting areas for future development.**

Large language models (LLMs) are increasingly being utilized as autonomous decision-making agents in various environments. However, their learning efficiency from trial-and-error remains a challenge due to the extensive training samples and expensive model fine-tuning required by traditional reinforcement learning methods.

### Approach

This paper introduces Reflexion, a novel framework that reinforces language agents through linguistic feedback rather than weight updates. Reflexion agents reflect verbally on task feedback signals and maintain their reflective text in an episodic memory buffer to improve decision-making in subsequent trials. The Reflexion framework is modular, utilizing three distinct models: an Actor, which generates text and actions; an Evaluator model, that scores the outputs produced by the Actor; and a Self-Reflection model, which generates verbal reinforcement cues to assist the Actor in self-improvement. The Actor generations follow a specific form: Instruction, Function implementation, Unit test feedback, Self-reflection, and Instruction for next function implementation.

### Results

Reflexion has demonstrated significant improvements over a baseline agent across diverse tasks, including challenging Leetcode questions in 19 programming languages. It achieved a 91% pass@1 accuracy on the HumanEval coding benchmark, surpassing the previous state-of-the-art GPT-4 that achieves 80%. Reflexion was particularly effective in AlfWorld scenarios, where it was able to identify early mistakes in long trajectories and suggest new action choices or long-term plans, and exploit its experience memory over several trials to thoroughly search a room. In a HotPotQA trial, Reflexion used self-reflection to determine a better search method for the next trial, correcting its initial incorrect answer by researching the past and current bands of two musicians to accurately compare their band memberships. However, Reflexion struggled in the WebShop environment, a web-based problem-solving benchmark that tests agents to navigate an e-commerce website to locate and purchase products. The agent did not show signs of improvement after four trials, indicating that Reflexion may struggle with tasks requiring a significant amount of diversity and exploration.

### Conclusion

Reflexion presents a promising alternative to traditional reinforcement learning methods for training large language models. By leveraging verbal reinforcement and episodic memory, it enables more efficient learning and improved performance across a range of tasks. However, its performance in environments requiring extensive exploration and diversity, such as WebShop, indicates that there are still challenges to overcome. Future work is encouraged to extend the memory component of Reflexion with more advanced structures such as vector embedding databases or traditional SQL databases. Furthermore, the Reflexion approach could potentially make autonomous agents more interpretable and diagnosable, addressing some of the challenges in reinforcement learning. However, safety and ethical considerations are paramount, especially when these agents are put into misuse. Lastly, for reproducibility, it is advised to use isolated execution environments when running autonomous code writing experiments as the generated code is not validated before execution.

## Implications/Learnings for GPT4Hana

...
