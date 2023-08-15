# AgentBench: Evaluating LLMs as Agents

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2308.03688v1)
- Code: [Github](https://github.com/thudm/agentbench)
- Leaderboard: [Website](https://llmbench.ai/)


**Authors**: Xiao Liu[^1], Hao Yu[^1], Hanchen Zhang[^1], Yifan Xu[^1], Xuanyu Lei[^1], Hanyu Lai[^1], Yu Gu[^2], Hangliang Ding[^1], Kaiwen Men[^1], Kejuan Yang[^1], Shudan Zhang[^1], Xiang Deng[^2], Aohan Zeng[^1], Zhengxiao Du[^1], Chenhui Zhang[^1], Sheng Shen[^3], Tianjun Zhang[^3], Yu Su[^2], Huan Sun[^2], Minlie Huang[^1], Yuxiao Dong[^1], Jie Tang[^1]

[^1]: Tsinghua University
[^2]: The Ohio State University
[^3]: UC Berkeley

## Summary

**TL;DR: This paper introduces AgentBench, a comprehensive benchmark for evaluating Large Language Models (LLMs) as agents across 8 diverse real-world tasks, revealing a significant performance gap between top-tier and open-source models, and providing a toolkit for future research and development in the field.**

![AgentBench Overview](./images/agent-bench-overview.png)

Large Language Models (LLMs) such as GPT-4 have shown impressive abilities in understanding human intent and executing instructions, leading to the development of applications like AutoGPT, BabyAGI, and AgentGPT. However, the absence of a systematic and standard benchmark to evaluate LLM-as-Agent presents a significant challenge. This paper introduces AgentBench, a multi-dimensional evolving benchmark that currently includes 8 distinct environments to assess the reasoning and decision-making abilities of LLM-as-Agent in a multi-turn open-ended generation setting. These environments include a simulated online shopping environment, Webshop, which tests the agent's ability to search, view, and choose items on a real e-commerce website. While games have been used as simulated environments for intelligent agent development, this paper focuses on text-based games, specifically a digital card game, as an ideal option for text-only LLM evaluation.

### Approach

Since LLM-as-Agent requires LLMs’ strong reasoning ability, Chain-of-Thought (CoT), which has been considered a de facto strategy in related evaluation together with actions, is also adopted in AgentBench. Despite many improved strategies were introduced, the authors evaluate LLMs with the most primitive CoT in AgentBench, as it reflects the most practical public user experience without multiple trails and repeated generation.

#### Environments

![AgentBench Environments](./images/agent-bench-envs.png)

- a) **Operating System (OS)**: Evaluation of LLMs in genuine OS’ interactive bash environments on human questions with deterministic answers or series of operations for practical goals
  - _Example consists of_: an instruction, a Docker environment, initialization and start scripts (optional), checking pipeline to verify correctness of the agent's answer/operation, and an example script (optional).
  - _Tasks_: Question Answering and operation
  - _Size_: 144 
  - _Metrics_: Success Rate
- b) **Database (DB)**:  Examine LLMs’ abilities to operate on real databases via SQL
  - _Example consists of_: an instruction, table info, table content, a correct answer
  - _Tasks_: Select, insert, or update queries
  - _Size_: 60
  - _Metrics_: Success Rate
- c) **Knowledge Graph (KG)**: In the context of engaging with a knowledge graph, the intelligent agent must demonstrate proficiency in comprehending intricate natural language, deconstructing intricate tasks into manageable steps, formulating strategic plans, and adapting flexibly as required. This task is characterized by a partially observable environment. All KG examples are constructed for the FREEBASE knowledge graph.
  - _Example consists of_: an input question, topic entities, action sequence, gold answers
  - _Tasks_: Select, insert, or update queries
  - _Size_: 500
  - _Metrics_: F1 score (predicted answers compared with gold answers), Exact Match (set of predicted answer exactly equal to gold answers), Executability (1 if the action sequence produces an answer)
- d) **Digital Card Game (DCG)**: Environment to test the agent's strategy and planning in a turn-based card game. The agent acts as a player managing a team of fishes with different talents to battle against another team (controlled by our baseline agent).
  - _Basic Rules_: Two-player battle game where each player controls a team of four pet fishes (cards) with unique abilities. Players take turns asserting the hidden identities of their opponent's fishes, aiming to reveal and damage them, while strategically using their fishes' active and passive abilities to secure victory by having more surviving fishes. An agent will be immediately deemed defeated if it fails to output legal actions within 5 attempts. 
  - _Metrics_: Full Play (round completion rate), Try Times (average number of illegal actions), Takedown (average number of defeated fish), Total DMG (total damage inflicted), Win Rate
- e) **Lateral Thinking Puzzles (LTP)**: The puzzle starts with a short story and the agent has to guess what happened by asking yes/no questions. The agents play in the role of the solver.
  - _Example consists of_: riddle/story, answer/solution
  - _Tasks_: Guess the solution
  - _Metrics_: Single Game Accuracy (proportion of rounds in which the agent approaches the truth), Round Effificiency (How fast the agents can guess out the truth), Query Relevance (Relevance between model’s questions and the truth), Game Progress (Proportion of groundtruth points reached by the agent)
- f) **House-Holding (Alfworld)**: ALFWorld is a benchmark with text-based household scenarios, where agents break down complex objectives into simple actions, receiving feedback from a simulation environment after each step to dynamically adapt their plan.
  - _Example consists of_: description household environment, objective, simulation environment
  - _Tasks_: Achieve the objective through a series of actions
  - _Size_: 134
  - _Metrics_: Success Rate
- g) **Web Shopping (WebShop)**: Evaluates agents' reasoning and decision-making abilities in online shopping scenarios. Agents navigate a simulated e-commerce website, searching, viewing, and choosing items based on textual instructions. The evaluation involves autonomous interaction and adaptation within the simulated web shop.
  - _Example consists of_: A goal along with expected attributes
  - _Tasks_: Selecting products through simulated online shopping interactions
  - _Size_: 500
  - _Metrics_: Matching reward (TextMatch, attributes, options, price, for chosen products based on expected attributes and user goals)
- h) **Web Browsing (Mind2Web)**: Mind2Web introduces a recently developed benchmark for training and evaluating web agents that can perform complex tasks across various website domains. It assesses agents' ability to interpret high-level user instructions and execute specific web interactions, such as clicking, typing, and selecting options, across diverse domains. During evaluation, a separate model ranks HTML elements, followed by a multi-choice QA for the agent to select the correct element, including specifying arguments for type and select option operations.
  - _Example consists of_: high-level goal, reference action sequence, webpage information as annotated HTML and previous interaction trajectory 
  - _Tasks_: Executing intricate tasks on websites, involving actions like clicking, typing, and selecting
  - _Size_: Cross Domain test set with 912 tasks from 73 websites
  - _Metrics_: Element Accuracy, Action F1 (Type and Select Option specific), Step Success Rate, Task Success Rate, measuring accuracy and success in various actions and task steps within web interactions.


![AgentBench Environments](./images/agent-bench-env-overview.png)

AgentBench is the first systematic benchmark to evaluate LLM-as-Agent across a wide array of real-world challenges and 8 distinct environments. A significant addition is the ALFWorld benchmark, which mimics household scenarios and requires the agent to break down complex high-level targets into a sequence of straightforward actions. The agent receives environment feedback after each step, allowing it to adapt the plan dynamically. The benchmark also includes a digital card game (DCG) environment, adapted from a simplified DCG system—Aquawar—from the 2021 Tsinghua University Agent Competition. In Aquawar, the agent acts as a player managing a team of fishes with different talents to battle against another team in a turn-based form, testing the model's understanding of game rules, operating logic, and strategic decision-making abilities. The game rules are simplified and include four types of pet fish, each with unique active and passive skills. The Webshop environment simulates an online shopping experience, with the agent interacting with a database of about a million products scraped from amazon.com. The evaluation setup employs a 1-shot evaluation setting, with the model's output assessed using the BLEU metric for similarity to valid action options. The evaluation process is divided into two parts: Initialization, where the task is described to the model along with a successful example, and Interaction, where the model generates thoughts and actions based on feedback and environment information. The Webshop environment also includes a reward function that maps the similarity of the attributes of the expected and actual bought product to a number between 0 and 1. The AgentBench design carefully balances evaluation comprehensiveness and efficiency, and the toolkit is designed to interact only with APIs, simplifying the process for LLMs that want to test on AgentBench.

### Results

![AgentBench Overview](./images/agent-bench-models.png)

The study extensively tests over 25 LLMs (including APIs and open-sourced models) and finds a significant disparity in performance between top commercial LLMs and open-sourced competitors. Top-tier models like GPT-4 are capable of handling a wide array of real-world tasks, including the digital card game environment and the Webshop online shopping simulation, indicating the potential for developing a potent, continuously learning agent. However, there is a significant performance gap between these top-tier models and their open-source counterparts. The performance of open-source LLMs on AgentBench tasks lags considerably, underscoring the need for additional efforts to enhance the learning abilities of open-source LLMs. The overall success rate, defined as the number of tasks successfully completed by the model divided by the total number of tasks, is used as a measure of model performance. The evaluation also includes metrics such as Element Accuracy, Action F1, and Step Success Rate. The latter is reported as the main metric due to the current struggles for LLMs to ensure overall task success rates. The overall score is calculated by averaging the scores of each task across all the models, scaling them to an average of 1. This method ensures fairness and consistency in evaluation, enabling easier comparisons and analysis in future research.
## Conclusion

AgentBench provides a comprehensive and systematic benchmark for evaluating LLMs as agents across diverse real-world challenges. It addresses the limitations of existing benchmarks and provides a more accurate reflection of the practical use-cases of LLMs. It serves as an ideal testbed for both LLM and agent evaluation, and reveals a significant performance disparity between top-tier and open-source models. The benchmark is continuously evolving to cover more scenarios and tasks in LLM-as-agent evaluation, with plans for further refinement and enrichment in its next version. The integrated toolkit, along with the associated datasets and environments, are made publicly available for the broader research community. The AgentBench design and toolkit, which is API-oriented and uses docker images for complex environments, simplifies the process for researchers and LLMs that want to test on AgentBench. The study also identifies specific challenges for LLMs in agent-formed tasks, including action validity, long context, and multi-turn consistency. The impact of code training is also considered. The performance of open-sourced LLMs, in particular, is significantly lower than that of API-based LLMs, with the most capable open-sourced model, openchat-13b-v3.2, still presenting a clear performance gap compared to gpt-3.5-turbo. This highlights the need for further research and development in the field of open-source LLMs.
