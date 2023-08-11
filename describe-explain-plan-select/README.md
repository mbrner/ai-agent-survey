<!--- Created using: ('gpt-4',) --->
<!--- Reviewed: False --->
# Describe, Explain, Plan and Select: Interactive Planning with Large Language Models Enables Open-World Multi-Task Agents

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2302.01560v1)
- Code: N/A

**Authors**: Zihao Wang, Shaofei Cai, Anji Liu, Xiaojian Ma, Yitao Liang

## Summary

**TL;DR: The paper presents 'Describe, Explain, Plan and Select' (DEPS), a novel planning method based on Large Language Models, which significantly improves task completion in Minecraft by addressing long-term planning challenges and introducing a proximity-based goal Selector, outperforming other methods and demonstrating potential for application in other open-ended environments.**

The paper investigates the challenges of planning in Minecraft, a platform for developing multi-task embodied agents. The main difficulties include the need for complex, multi-step reasoning due to the long-term nature of tasks, and the inefficiency of traditional planners that do not consider the agent's current proximity when arranging parallel sub-goals. Tasks in Minecraft typically involve mining and crafting goals, which require the agent to collect raw materials and synthesize them using appropriate tools. Successful execution of a task often involves satisfying exact numerical constraints, which adds to the complexity.

### Approach

The authors propose 'Describe, Explain, Plan and Select' (DEPS), an interactive planning method based on Large Language Models (LLMs). DEPS addresses error correction during long-term planning and introduces a sense of proximity through a goal Selector. This Selector is a learnable module that ranks parallel sub-goals based on estimated completion steps, modifying the original plan to increase efficiency and success rate. The DEPS system also includes a descriptor that summarizes the current situation as text and provides feedback to the LLM-based planner when a failure occurs, allowing for error identification and re-planning. The system also incorporates a low-level multi-task controller for decision-making, which can be trained by reinforcement learning or imitation learning methods. The controller is trained using the observation space provided by MineDoJo, which includes an RGB camera view, yaw/pitch angle, GPS location, and the type of 3 × 3 blocks surrounding the agent. The action space is discretized into 42 discrete actions, and a modified goal-sensitive Impala CNN is used as the backbone network. Additionally, the DEPS method includes a Goal Mapping component that maps the plan expressed in free-form language to the pre-defined controller skills set, and a Prompt Generator that translates task instructions into prompt text, enhancing the generalization of the LLM to different tasks.
### Results

Experiments conducted on 71 tasks in Minecraft demonstrate that DEPS is the first multi-task agent capable of successfully completing over 70 Minecraft tasks, nearly doubling overall performance. DEPS is also the first planning-based agent to achieve an above-zero success rate on the challenging ObtainDiamond task. The DEPS method was compared with other LLM-based planners, including Zero-shot Planner, Prog-Prompt, Chain of Thought, Inner Monologue, and Code as Policies. These methods were adapted to the Minecraft specification for the comparison. The DEPS method outperformed these methods, demonstrating its effectiveness. Furthermore, the DEPS method showed improved success rates under different maximum rounds of interactive feedback, indicating its adaptability and robustness. Additional experiments showed that the Selector significantly improved the final task success rate, especially in efficiency-sensitive tasks. Different implementations of the Selector were tested, with the horizon-predictive Selector showing the best performance.
### Conclusion

The research highlights the challenges of planning in open-ended environments like Minecraft and presents a novel approach to address them. The DEPS method, based on Large Language Models, shows significant improvements in task completion, paving the way for the development of more advanced artificial intelligence. The contributions of this research are twofold: the proposal of the DEPS method and the demonstration of its effectiveness in improving task completion rates. The Selector component of DEPS, particularly the horizon-predictive Selector, plays a crucial role in this success. The DEPS planner is zero-shot, allowing it to generalize to other long-horizon open worlds, setting it apart from previous efforts that focused on improving the low-level controller. However, the approach has limitations, including reliance on privately-held LLMs and the explicit planning in the system, which can prevent the model from being further scaled up. Future work will explore using open-sourced models and integrating the planning within an end-to-end trainable goal-conditioned policy.

## Implications/Learnings for GPT4Hana

...
