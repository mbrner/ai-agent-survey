<!--- Created using: ... --->
<!--- Based on: 89.7% of the Paper --->
<!--- Reviewed: False --->
# ProgPrompt: Generating Situated Robot Task Plans using Large Language Models

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2209.11302v1)
- Code: N/A

**Authors**: Ishika Singh, Valts Blukis, Arsalan Mousavian, Ankit Goyal, Danfei Xu, Jonathan Tremblay, Dieter Fox, Jesse Thomason, Animesh Garg

## Summary

**TL;DR: Singh et al.'s paper presents PROGPROMPT, a novel approach that uses large language models to generate task plans for robots, demonstrating its effectiveness in various environments and tasks, and introducing situated-awareness in robot task planning, while also highlighting potential improvements and acknowledging current limitations.**

The paper by Singh et al., 'Generating Situated Robot Task Plans using Large Language Models', explores the use of large language models (LLMs) for creating task plans for robots, eliminating the need for extensive domain knowledge. The authors highlight the importance of commonsense understanding and situated knowledge about the current environment for executing everyday household tasks.

### Approach

The authors propose PROGPROMPT, a unique prompting scheme that conditions LLMs beyond natural language using programming language structures. This scheme provides an LLM with a Pythonic program header that imports available actions and their expected parameters, presents a list of environment objects, and defines functions like 'make dinner' whose bodies are sequences of actions operating on objects. The paper emphasizes the need to incorporate situated state feedback from the environment, such as asserting preconditions of the plan and responding to failed assertions with recovery actions. The task planning is formulated as a problem of transforming the input state observation into a textual prompt and generating an output from the entire LLM vocabulary or scoring a predefined set of options. The authors use ViLD, an open-vocabulary object detection model, to identify and segment objects in the scene and construct the available object list for the prompt. The LLM outputs a plan containing function calls of form grab and putin(obj1, obj2). The approach was implemented on a Franka-Emika Panda robot with a parallel-jaw gripper, using a pick-and-place policy.

### Results

The model, using the PROGPROMPT scheme, effectively generates task plans based on the given prompts, achieving state-of-the-art success rates in VirtualHome household tasks. It was able to generate plans according to the prompts, such as sorting fruits on a plate and bottles in a box, while ignoring distractor objects. The method was also successfully implemented on a physical robot arm for tabletop tasks, demonstrating its practical applicability. The model's ability to correct errors before executing the next step, as shown in the microwave salmon example, further underscores its effectiveness. The PROGPROMPT significantly outperforms the baseline and LANGPROMPT in the evaluation of generated programs on Virtual Home. The performance of the system was evaluated using three metrics: success rate (SR), goal conditions recall (GCR), and executability (Exec). The variability in performance across runs arises from sampling LLM output. Furthermore, PROGPROMPT outperforms prior work by a substantial margin on all metrics using the same large language model backbone. The CODEX and DAVINCI models show mixed success at the task, with CODEX exceeding GPT3 performance on every metric, likely due to its explicit training on programming language data. The authors also conducted several ablations of PROGPROMPT, finding that feedback mechanisms and natural language comments within the programming language structure significantly improve performance.

### Conclusion

The paper presents a novel approach to robot task planning using LLMs and the PROGPROMPT scheme. This method proves effective across various environments, robot capabilities, and tasks, and importantly, introduces situated-awareness in LLM-based robot task planning. The inclusion of natural language comments in PROGPROMPT programs to explain the goal of the upcoming action further improves task success of generated plan programs. The method sidesteps traditional search-based planning to directly generate a plan that includes conditional reasoning and error-correction, setting it apart from previous works. The authors recommend the use of a program-like prompt for LLM-based task planning and execution, for which base GPT3 works well, and note that an LLM fine-tuned further on programming language data, such as CODEX, can do even better. However, the authors also note that many failures stem from the decision to make PROGPROMPT agnostic to the deployed environment and its peculiarities, which may be resolved through explicitly communicating, for example, object affordances of the target environment as part of the PROGPROMPT prompt. The authors also acknowledge the limitations of the current approach, such as incomplete generation due to LLM API caps and strict final state checking that may infer failure even when the task is completed. Future work could involve querying the LLM again with the prompt and partially generated plan, or introducing human verification for ambiguous tasks.
