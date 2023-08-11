<!--- Created using: ('gpt-4',) --->
<!--- Reviewed: False --->
# TPTU: Task Planning and Tool Usage of Large Language Model-based AI Agents

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2308.03427v1)
- Code: N/A

**Authors**: Jingqing Ruan, Yihong Chen, Bin Zhang, Zhiwei Xu, Tianpeng Bao, Guoqing Du, Shiwei Shi, Hangyu Mao, Xingyu Zeng, Rui Zhao

## Summary

**TL;DR: This study presents a structured framework for Large Language Models (LLMs) based AI agents, introducing a novel approach for flexible problem-solving, and demonstrating through evaluations that these agents, particularly ChatGPT, show significant potential in task planning, tool usage, and managing complex tasks, thus highlighting their promising prospects for future research and real-world applications.**

The paper presents a structured framework for Large Language Models (LLMs) based AI agents, focusing on their task planning and tool usage capabilities. It introduces two types of agents, one-step and sequential, to facilitate the inference process. The study is particularly interested in the AI Agent that employs the LLM techniques due to its high efficiency and flexibility in various tasks and domains. The LLMs evaluated include models developed by various organizations such as OpenAI, Anthropic, Shanghai AI Lab, IDEA, and Tsinghua University. The paper also discusses the limitations of traditional deep learning approaches and the advantages of LLMs in terms of comprehension of tool functionality, user intentions, and common sense reasoning abilities.

### Approach

The study proposes a novel approach to foster flexible problem-solving with the LLM-based AI agent. The agent is prompted to generate multiple sequences, each consisting of a key-value pair in the format of {tool: subtask description} that associates a tool with its respective subtask description. This allows simultaneous planning of the tool choice and subtask without the risk of improper matching. The approach also offers the flexibility to update the planned sequences in real-time based on evolving problem feedback, enhancing adaptability and efficiency when addressing complex tasks. A unique prompt is designed to encourage this advanced problem-solving strategy. The paper also discusses the integration of sensor data, transformation of natural language instructions into code fragments, and the construction of inner monologues for effective robot control strategies. The paper further discusses how LLMs can utilize software tools such as search engines, mobile apps, Microsoft Office, calculators, deep models, and other APIs to enhance model performance or complete complex workflows.
### Results

The evaluation results showed a marked improvement when the tool-subtask pairs are generated in a unified format compared to separate generation of tools and subtasks. In the evaluation of end-to-end ability of multiple tools, ChatGPT achieved a performance rate of 50% in the TPTU-OA evaluation, significantly outperforming the other models, with InternLM at 15%, while both Ziya and Chinese-Alpaca did not manage to complete any tasks successfully, resulting in a score of 0%. In the TPTU-SA evaluation, ChatGPT maintained its leading position, with a slightly improved performance rate of 55%. InternLM also exhibited better performance, achieving a score of 20%, whereas Ziya and Chinese-Alpaca-Plus again failed to register any successful task completion.
### Conclusion

The study introduces a structured framework designed for LLM-based AI Agents, emphasizing their abilities in task planning and tool usage. The framework, along with the design of two distinct types of agents for the inference process, allows for a comprehensive evaluation of the capabilities of current open-source LLMs, providing critical insights into their effectiveness. The research underscores the significant potential of LLMs in managing complex tasks and their promising prospects for future research and development. As the exploration and improvement of these models continue, we move closer to unlocking their full potential in a wide range of real-world applications. The study also highlights the importance of tailoring evaluation and training methodologies to the individual strengths and weaknesses of each model. The paper also underscores the potential of LLM-based agents in real-world applications, and the need to push their boundaries through continued research and development.

## Implications/Learnings for GPT4Hana

...
