<!--- Created using: ... --->
<!--- Based on: 100.0% of the Paper --->
<!--- Reviewed: False --->
# Faithful Chain-of-Thought Reasoning

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2301.13379v2)
- Code: N/A

**Authors**: Qing Lyu, Shreya Havaldar, Adam Stein, Li Zhang, Delip Rao, Eric Wong, Marianna Apidianaki, Chris Callison-Burch

## Summary

**TL;DR: The study introduces the Faithful Chain-of-Thought (CoT) framework, a two-stage approach that improves Language Models' performance and interpretability on complex reasoning tasks by translating a natural language query into a reasoning chain and executing it with a deterministic solver, achieving state-of-the-art performance on multiple datasets, though it suggests room for improvement and further exploration in the translation stage and debugging interface.**

The study examines the Chain-of-Thought (CoT) prompting method, which improves Language Models' (LM) performance on complex reasoning tasks. However, the reasoning chain generated may not accurately reflect the model's faithfulness in reaching the answer, potentially leading to over-trust in the model in high-stake applications.

### Approach

The researchers introduce Faithful CoT, a framework that divides a reasoning task into two sequential stages: Translation and Problem Solving. In the Translation stage, an LM translates a Natural Language query into a reasoning chain, interweaving Natural Language and a task-dependent Symbolic Language. This process is exemplified in a user-robot interaction scenario, where a household task query is translated into a plan of actions. The reasoning chain consists of subtasks and symbolic goals in PDDL5, a language for defining and solving classical planning problems. In the Problem Solving stage, a deterministic solver such as a Python/Datalog interpreter or a PDDL planner is used to execute the reasoning chain and produce an answer. This approach is generalizable to multiple domains beyond arithmetic reasoning and simple symbolic reasoning, thanks to its flexible integration with any choice of Symbolic Language and external solver.

### Results

The proposed approach was evaluated on 10 reasoning datasets from 4 diverse domains, including Math Word Problems and Planning. It outperformed traditional CoT prompting on 9 out of the 10 datasets, with an average accuracy gain of 4.4 on Math Word Problems, 1.9 on Planning, 4.0 on Multi-hop Question Answering (QA), and 18.1 on Logical Inference, under greedy decoding. With self-consistency decoding, it achieved new state-of-the-art few-shot performance on 7 out of the 10 datasets. However, on StrategyQA, the performance was below CoT and standard prompting, likely due to the sparsity of Datalog in the pretraining data for Codex. An error analysis on StrategyQA revealed the most frequent error types to be Syntax and Infinite Loop. Syntax errors were related to invalid Datalog programs, while Infinite Loop errors were due to the LM generating an endless loop of subquestions. The study also provides an extensive analysis of the strengths and weaknesses of the method, showing its robustness to the choice of exemplars as well as the critical role of the solver.

### Conclusion

The Faithful CoT framework offers a more reliable and interpretable method for complex reasoning tasks, addressing the lack of faithfulness in existing CoT methods. This approach not only enhances performance but also improves the interpretability of the model's predictions, reducing the risk of over-trust in high-stake applications. The reasoning chain interleaves user-understandable natural language comments and executable symbolic language programs, thus providing interpretability of how the model arrives at the answer. The approach's generalizability to multiple symbolic languages and domains, and its structured interweaving of natural and symbolic language, distinguishes it from concurrent works. However, the performance on StrategyQA indicates room for improvement, particularly with further pretraining on Datalog. Despite these advancements, the Translation stage remains opaque, posing questions about potential improvements in its faithfulness. Future work should explore the use of the natural language comments in the reasoning chain as an interface for non-programming users to interactively debug the model, and conduct a human evaluation on the correctness of the generated reasoning chains.
