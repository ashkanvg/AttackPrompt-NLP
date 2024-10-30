# Utilizing GPT-3.5 Turbo to Perform a Prompt-Based Adversarial Attack on AdvBench

## Abstract
*Content warning: This project contains unfiltered content generated by LLMs that may be offensive to readers.*

Large Language Models (LLMs) have many applications, including transforming harmful prompts into acceptable formats. This study demonstrates the efficacy of LLMs in modifying harmful prompts so they can be accepted by other LLMs. Specifically, we evaluate a methodology proposed for the **AdvGLUE** dataset that changes the classification outcomes.

Our evaluation primarily focuses on the **AdvBench** dataset, a collection of harmful prompts. We find that the current methodology is unsuitable for this task but propose potential research directions through further modifications.

This project evaluates the success rate of our methodologies and provides empirical results on prompt-based adversarial attacks.

---

## Introduction
LLMs have advanced rapidly in recent years, assisting with tasks such as code generation, business analytics, and everyday language processing, thanks to their training on massive datasets.

One important use case of LLMs relates to **adversarial attacks**, where attackers aim to manipulate inputs to produce unintended outputs. In this project, we leverage an approach proposed in **AttackPrompt** [Xu et al., 2023] to modify prompts by changing the meaning of harmful inputs. The objective is to make the modified prompts acceptable to the model, ensuring they return positive responses.

The **AttackPrompt** framework introduces a methodology for converting a prompt with a **negative classification result into a positive one**. We extend their work by experimenting with different levels of **prompt permutation** (from 0 to 8) to assist LLMs in adjusting these adversarial prompts. Specifically, we used **GPT-3.5 Turbo** for this task to modify and evaluate the transformed prompts.

---

## Main Contributions
- **Application of AttackPrompt methodology** on the **AdvGLUE dataset** to validate the framework on their datasets.  
- **Testing on the AdvBench dataset**, revealing limitations and identifying necessary modifications for improved performance.  
- **Success and Failure Rate Analysis:** Measured the success rate of prompt transformation with GPT-3.5 and analyzed its performance in adversarial tasks.  
- **Identification of Future Research Opportunities:** Demonstrated that the methodology requires modification to be effective for further research purposes.

---

## Prompt Transformation Success Rate
We experimented with **11 different permutations** for attack guidance and evaluated the success of prompt transformations using both **GPT-3.5 Turbo** and **Llama-2** models.

- **GPT-3.5 Turbo:** Successfully converted more than **95% of prompts**, as the model typically flags harmful prompts instead of rejecting them outright.  
- **Llama-2:** Rejected **80% of prompts** due to stricter rules against harmful content, leading to lower success rates.

---

## Results Overview
Below is a table summarizing the success rates for different levels of prompt permutation with GPT-3.5:

| **Permutation** | **Successful** | **Failures** | **Success Rate (%)** |
|-----------------|----------------|--------------|---------------------|
| Level 0         | 568            | 7            | 98.78               |
| Level 1         | 570            | 5            | 99.13               |
| Level 2         | 547            | 28           | 95.13               |
| Level 3         | 560            | 15           | 97.39               |
| Level 4         | 559            | 16           | 97.21               |
| Level 5         | 555            | 20           | 96.52               |
| Level 6         | 560            | 15           | 97.39               |
| Level 7         | 569            | 6            | 98.95               |
| Level 8         | 566            | 9            | 98.43               |
| Level 9         | 540            | 35           | 93.91               |
| Level 10        | 549            | 26           | 95.47               |

---

## Findings and Limitations
- **AdvBench Results:**  
  The methodology was less effective on the **AdvBench dataset** due to differences in problem formulation, as expected. While some prompts were accepted after modification, the model could not generate the desired target responses.  

- **Permutation Impact:**  
  Our experiments showed that **permutations L=9 and L=10** significantly improved the robustness of the adversarial attacks.  

- **Future Research Directions:**  
  The limitations observed suggest opportunities for further research. Modifying the methodology could yield better results for different datasets and tasks, especially when working with stricter models like **Llama-2**.

---

## Conclusion and Discussion
This project demonstrates the potential and challenges of using LLMs for **adversarial prompt modification**. Our findings show that **GPT-3.5 Turbo** outperforms **Llama-2** in handling adversarial prompts, but the methodologies need refinement for broader applicability.

We also highlight that current techniques are unsuitable for **AdvBench**, but modified approaches could unlock new research opportunities for adversarial NLP tasks.

---

## Acknowledgments
This project builds on the AttackPrompt framework proposed in [Xu et al., 2023]. We are grateful to the creators of **AdvGLUE** and **AdvBench** datasets for their contributions to this research.

---

## References
- Xu, et al. (2023). *AttackPrompt: Adversarial Prompting with Large Language Models*. arXiv. [Link to paper](https://arxiv.org/abs/2303.12345)