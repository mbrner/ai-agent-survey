<!--- Created using: ('gpt-4',) --->
<!--- Reviewed: False --->
# ChatCoT: Tool-Augmented Chain-of-Thought Reasoning on Chat-based Large Language Models

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2305.14323v2)
- Code: N/A

**Authors**: Zhipeng Chen, Kun Zhou, Beichen Zhang, Zheng Gong, Wayne Xin Zhao, Ji-Rong Wen

## Summary

**TL;DR: ChatCoT, a novel framework, enhances the reasoning abilities of Large Language Models by modeling reasoning as multi-turn conversations and integrating tool manipulation, achieving significant improvements in complex tasks, as demonstrated in experiments on MATH and HotpotQA datasets, while maintaining a comparable computational expense to existing methods.**

ChatCoT is a novel framework designed to enhance the reasoning abilities of Large Language Models (LLMs) by modeling reasoning as multi-turn conversations. This approach allows LLMs to interact with tools and perform complex reasoning tasks in a more natural and integrated way, overcoming the limitations of existing methods.

### Approach

ChatCoT addresses the challenges LLMs face with complex reasoning tasks by integrating the thought chain following and tools manipulation in a unified manner. It utilizes the Chain-of-Thought (CoT) prompt strategy to guide LLMs for performing step-by-step reasoning. The CoT prompt consists of few exemplars involving a series of intermediate reasoning steps. ChatCoT initializes the early turns of the conversation by the tools, tasks, and reasoning format, and proposes an iterative tool-augmented reasoning step to perform step-by-step reasoning. The tools used include a calculator, an equation solver, and a retriever, each with specific functions. These tools are implemented using different interfaces of SymPy, a Python library for mathematical symbolic calculation, and SimCSE, a sentence embedding model to measure text semantic similarity. Existing CoT improvement strategies can be adapted to ChatCoT, demonstrating its flexibility and adaptability.
### Results

ChatCoT's effectiveness was demonstrated through experiments on two complex reasoning datasets (MATH and HotpotQA), where it achieved a 6.8% relative improvement over the state-of-the-art baseline. In the MATH dataset, ChatCoT outperformed other models in all categories, with the highest performance in Algebra and Geometry. In the HotpotQA dataset, ChatCoT achieved a score of 59.1, significantly higher than the CoT with and without tools. The ablation study results showed that the use of tool knowledge, retrieval-augmented task knowledge, and multi-turn reasoning format at early turns of the conversation significantly improved the performance. Furthermore, ChatCoT achieved 11.1% and 55.5% relative improvements on the MATH and HotpotQA datasets respectively, compared to CoT. It also outperformed the previous state-of-the-art method PHP in six of seven sub-tasks on the MATH dataset. Despite guiding LLMs to reason through multi-turn dialogue, the computation expense of ChatCoT is not significantly larger than the CoT method.
### Conclusion

ChatCoT significantly improves the reasoning abilities of LLMs, particularly in complex tasks requiring specific knowledge and multi-hop reasoning. It offers a more unified way to integrate CoT reasoning and tool manipulation, enhancing the continuity of the reasoning process. The tool's code and data are publicly available for further research and development. It is a general framework that can be applied to a variety of complex reasoning tasks that require suitable tools. However, it is important to note that directly utilizing external tools during reasoning can harm performance by disrupting the continuity of reasoning and causing confusion about the reasoning step. Despite this, the computational expense of ChatCoT is not significantly larger than existing methods, making it a viable option for complex reasoning tasks. Future work will test the effectiveness of the proposed approach to more types of reasoning tasks and consider extending the number of available tools for solving different tasks.
