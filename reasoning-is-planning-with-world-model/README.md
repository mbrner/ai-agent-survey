<!--- Created using: ('gpt-4',) --->
<!--- Reviewed: False --->
# ChatCoT: Tool-Augmented Chain-of-Thought Reasoning on Chat-based Large Language Models

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2305.14323v2)
- Code: N/A

**Authors**: Zhipeng Chen, Kun Zhou, Beichen Zhang, Zheng Gong, Wayne Xin Zhao, Ji-Rong Wen

## Summary

**TL;DR: The paper introduces ChatCoT, a tool-augmented chain-of-thought reasoning framework for large language models, which significantly improves complex reasoning performance by integrating tool manipulation and multi-turn conversations, demonstrating state-of-the-art results on the MATH and HotpotQA datasets.**

The paper investigates the challenges faced by Large Language Models (LLMs) in complex reasoning tasks, particularly those requiring specific knowledge and multi-step reasoning. Despite the use of Chain-of-Thought (CoT) prompting, which encourages LLMs to generate intermediate reasoning paths and reason step-by-step, LLMs still struggle with these tasks. The integration of external tools into LLMs often disrupts the CoT reasoning process, making complex reasoning tasks more challenging.

### Approach

The authors propose ChatCoT, a tool-augmented chain-of-thought reasoning framework for chat-based LLMs. This approach models the CoT reasoning as multi-turn conversations, allowing LLMs to focus on manipulating tools or accomplishing reasoning in the current step, without premature planning and sudden interruption. The tools used include a calculator, an equation solver, and a retriever, implemented using SymPy and SimCSE. The conversation is initialized with background knowledge, including tool descriptions, relevant task examples, and a demonstration of the decomposed chain-of-thought in chat. The LLMs are also trained to retrieve the most semantically similar exemplars from the training dataset using SimCSE, a sentence embedding method, to provide more useful knowledge for the given question. Existing CoT improvement strategies can also be adapted to the ChatCoT method.
### Results

ChatCoT achieved state-of-the-art performance on the MATH dataset and outperformed other baselines on the HotpotQA dataset. It achieved an 11.1% relative improvement on the MATH dataset and a 55.5% relative improvement on the HotpotQA dataset compared to CoT. Compared to the previous state-of-the-art method PHP, ChatCoT outperformed six of seven sub-tasks on the MATH dataset and achieved a 6.8% relative improvement. An ablation study confirmed the effectiveness of each component in ChatCoT, including conversational memory, tool knowledge memory, retrieval-augmented knowledge memory, and multi-turn reasoning format memory. Removing any of these components reduced the performance of ChatCoT, indicating their importance in complex reasoning. Despite the multi-turn dialogue approach, the computation expense of ChatCoT is not significantly larger than the CoT method.
### Conclusion

The paper concludes that the ChatCoT framework can significantly enhance the reasoning abilities of LLMs by integrating thought chain following and tool manipulation in a unified way. The authors have made their code and data available for further research and development. The ChatCoT framework is task-agnostic and can be applied to a variety of complex reasoning tasks that require suitable tools, making it a versatile tool for enhancing the reasoning capabilities of LLMs. The study also highlights the importance of retrieved exemplars in improving reasoning performance, particularly in specific domains such as geometry and number theory. The ChatCoT method can also be enhanced with existing CoT improvement strategies, demonstrating its adaptability and potential for further development. Future work will test the effectiveness of the proposed approach to more types of reasoning tasks and consider extending the number of available tools for solving different tasks.
