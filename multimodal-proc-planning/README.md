<!--- Created using: ... --->
<!--- Based on: 100.0% of the Paper --->
<!--- Reviewed: False --->
# Multimodal Procedural Planning via Dual Text-Image Prompting

**Relevance: ...**

**Link**:
- Paper: [Arxiv](http://arxiv.org/pdf/2305.01795v1)
- Code: N/A

**Authors**: Yujie Lu, Pan Lu, Zhiyu Chen, Wanrong Zhu, Xin Eric Wang, William Yang Wang

## Summary

**TL;DR: The paper presents a novel Text-Image Prompting (TIP) model that outperforms existing models in generating multimodal procedural plans, demonstrating superior accuracy, coherence, and informativeness, using newly collected WIKIPLAN and RECIPEPLAN datasets, despite some limitations in data and evaluation metrics.**

The paper introduces a new dual Text-Image Prompting (TIP) model for generating multimodal procedural plans with multiple steps towards a high-level goal. The model addresses the limitations of large language models (LLMs) and text-to-image (T2I) models, which often struggle with generating images requiring complex text comprehension and frequently result in inconsistency and incoherence when generating text and image plans separately.

### Approach

The TIP model employs a Text-to-Image Bridge (T2I-B) and an Image-to-Text Bridge (I2T-B) to guide the generation of text-grounded image plans and ground the textual plan reversely. The model was evaluated on a task of creating a procedural plan for making traditional Szechuan chicken, involving multiple steps from gathering ingredients to serving the dish. To address the lack of relevant datasets for the multimodal procedural planning (MPP) task, WIKIPLAN and RECIPEPLAN datasets were collected from the IHOW website, which provides a wide range of how-to articles related to everyday life topics. The model also incorporates visual knowledge into LLMs through visual imagination, using existing images as augmented visual features or generating images for additional visual supervision.

### Results

The TIP model outperformed various unimodal and multimodal baselines on WIKIPLAN and RECIPEPLAN in a zero-shot setting, demonstrating superior human preferences and automatic scores. The generated plans were informative, temporally coherent, and accurate, highlighting the potential of integrating knowledge from LLMs and T2I models for multimodal zero-shot planning. The model's effectiveness is further demonstrated through text-to-image generation showcases. The model was evaluated on four aspects: textual informativeness, visual informativeness, temporal coherence, and planning accuracy. Ablation studies confirmed the robustness of the TIP model and the importance of the T2I-B and I2T-B components. The procedure-based method achieves a 60% win rate over the step-based TIP, indicating the potential for uncovering multimodal reasoning capabilities in LLMs. However, there were some failure cases, such as the state of the almond remaining unchanged due to no explicit awareness of previous state change, and the generated image plan losing authenticity at certain steps.

### Conclusion

The TIP model presents a promising approach to multimodal procedural planning, providing more comprehensive and informative guidance than unimodal plans. It ensures the informativeness, temporal coherence, and accuracy of plans across modalities, making them useful guidelines for task completion. This work pioneers the multimodal procedural planning task and evaluates model performance using the newly collected WIKIPLAN and RECIPEPLAN datasets from the IHOW website. The robustness of the model and its superiority in generating semantically correct and aligned multimodal plans are further confirmed. Future work will continue to explore and refine this approach, with a focus on improving the pre-training gap between LLMs and T2I models to enhance language reasoning in multimodal generation models. Despite the limitations in the dataset and the lack of perfect metrics for evaluating text-image sequences, this research provides a promising direction for future work to lead LLMs and T2I models to become better multimodal procedural planners.
