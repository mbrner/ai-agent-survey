<!--- Created using: ('gpt-4',) --->
<!--- Reviewed: False --->
# Generative Agents: Interactive Simulacra of Human Behavior

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2304.03442v2)
- Code: N/A

**Authors**: Joon Sung Park, Joseph C. O'Brien, Carrie J. Cai, Meredith Ringel Morris, Percy Liang, Michael S. Bernstein

## Summary

**TL;DR: This study presents an architecture for generative agents using gpt3.5-turbo, capable of simulating human behavior and forming complex reflections, with potential applications in various fields, but also highlights the need for ethical considerations, improvements in memory retrieval, and cost-effectiveness.**

The paper explores generative agents, computational software agents that simulate human behavior. These agents, capable of forming opinions, initiating conversations, and recalling past experiences, have potential applications in various fields, including immersive environments, communication rehearsal spaces, prototyping tools, cognitive models, virtual environments, social robots, and non-playable game characters.

### Approach

The authors propose an architecture that uses a large language model, specifically gpt3.5-turbo version of ChatGPT, to store a comprehensive record of the agent's experiences in natural language. The architecture, comprising three main components - memory stream, reflection, and planning, allows the agents to synthesize memories into higher-level reflections over time and retrieve them dynamically to plan behavior. The generative agents are implemented in an interactive sandbox environment, Smallville, built using the Phaser web game development framework.
### Results

The evaluation reveals that these generative agents produce believable individual and emergent social behaviors. They make a wide range of inferences about themselves, other agents, and their environment; they create daily plans that reflect their characteristics and experiences, act out those plans, react, and re-plan when necessary. However, the agents' memory retrieval was not flawless. Instances were observed where agents failed to retrieve the correct or complete memory, leading to inconsistencies in their responses. Additionally, agents occasionally embellished their knowledge, adding details that were not part of their experiences or the world knowledge encoded in the language model.
### Conclusion

The study underscores the potential of generative agents in creating interactive and immersive environments. However, it also highlights the ethical and societal risks, including the risk of over-reliance on these agents in design processes. The authors argue that generative agents should not replace human input in studies and design processes, but rather be used to prototype ideas in early design stages or test theories that are challenging or risky to test with human participants. Future work can focus on improving the retrieval module, making the architecture more cost-effective, and addressing robustness concerns and data limitations for certain subpopulations. The paper also emphasizes the need for ethical and socially responsible deployment of generative agents.
