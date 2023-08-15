<!--- Created using: ... --->
<!--- Based on: 57.6% of the Paper --->
<!--- Reviewed: False --->
# LLM+P: Empowering Large Language Models with Optimal Planning Proficiency

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2304.11477v2)
- Code: N/A

**Authors**: Bo Liu, Yuqian Jiang, Xiaohan Zhang, Qiang Liu, Shiqi Zhang, Joydeep Biswas, Peter Stone

## Summary

**TL;DR: The paper presents a novel framework, LLM+P, that combines large language models (LLMs) and classical planners to significantly improve the solution of new planning problems, particularly in robot tasking, addressing the competence gap in LLMs, although future research is needed to enable LLMs to auto-detect when to apply LLM+P and reduce human dependency.**

Large language models (LLMs) such as Bert, CodeX, Opt, GPT-3, ChatGPT, GPT-4, LLAMA, and PaLM have demonstrated impressive zero-shot generalization capabilities, especially in robot planning tasks. However, they often falter when faced with long-horizon planning problems, a domain where classical planners excel. This exposes a competence gap in LLMs, as they frequently fail to generate feasible solutions for new planning problems.

### Approach

This paper presents LLM+P, a unique framework that merges the strengths of classical planners and LLMs. The approach involves translating a natural language description of a planning problem into a planning domain definition language (PDDL) file. Classical planners are then used to find an optimal solution, which is subsequently translated back into natural language using the LLM. The paper also emphasizes the ability of LLMs to rewrite planning prompts in PDDL format, treating it as a 'machine translation' task that LLMs excel at. The LLM+P method is directly applicable as a natural language interface for assigning tasks to robot systems. The approach was tested across a variety of planning scenarios including block rearrangement, cocktail creation, floor tile painting, object moving, crate lifting, complex structure building, and tire replacement. An automatic validation software was used to validate the correctness of the predicted problem PDDL file.

### Results

LLM+P was tested on a wide variety of benchmark problems from typical planning scenarios. The results showed that LLM+P could generate optimal solutions for most problems, significantly outperforming LLMs, which often failed to produce feasible plans. The paper also demonstrates the capability of LLMs for in-context learning, performing unseen downstream tasks by simply conditioning on a few input-label pairs. The study also compared LLM+P with LLM-AS-P, with the former showing much better performance. The context was found to play a crucial role in the success of LLM+P. The experiments were conducted using the TEXT-DAVINCI-003 model provided by OpenAI, with a deterministic response from the LLM. The FAST-DOWNWARD planner was used to process the PDDL responses, with a maximum search time of 200 seconds. The TYREWORLD domain showed the most performance boost from LLM-AS-P (without context) to LLM-AS-P (with context). However, LLM-AS-P failed in domains with complex spatial relationships, such as FLOORTILE, TERMES, and STORAGE.

### Conclusion

The study concludes that the LLM+P framework, which integrates classical planners with LLMs, significantly enhances the ability to solve new planning problems. This addresses the competence gap in LLMs and suggests that the approach could be extended to any problem class for which a reliable and comprehensive solver exists. However, a current limitation is that the LLM does not recognize when a prompt should be processed by LLM+P, indicating a potential area for future research. The LLM+P method could be particularly useful as a natural language interface for tasking robot systems. The paper also acknowledges concurrent work on integrating LLMs with PDDL, but highlights the more comprehensive nature of the LLM+P method. Future work could focus on enabling the LLM to auto-detect when and how to apply LLM+P, and reducing LLM+P’s dependency on information provided by humans, potentially involving fine-tuning.
