FOSSEE Semester Long Internship - Autumn 2025: Python Screening Task 3 Submission

This repository contains my submission for Python Screening Task 3: Evaluating Open Source Models for Student Competence Analysis, part of the FOSSEE Semester Long Internship - Autumn 2025.

Research Plan

To evaluate open source AI models for student competence analysis in Python learning, I will begin by exploring repositories like Hugging Face and GitHub to identify models tailored for code understanding, such as large language models (LLMs) fine-tuned on programming datasets. My focus will be on models with permissive licenses, strong community support, and high performance on benchmarks like HumanEval. A promising candidate is DeepSeek-Coder V2, specifically the Lite-Instruct variant, due to its code-specific pretraining. The evaluation process will involve downloading the model using Hugging Face’s Transformers library and testing it with sample Python code from educational contexts, such as scripts with common errors (e.g., incorrect loop boundaries or variable misuse). This will be conducted on a local machine or via free inference endpoints to ensure accessibility and minimize costs. The goal is to assess the model’s ability to identify misconceptions and generate prompts that encourage self-correction without revealing solutions.

Testing will involve feeding the model diverse Python code samples with embedded errors and prompting it to analyze them (e.g., "Describe potential gaps in understanding in this code"). Outputs will be evaluated based on relevance, depth of insight, and pedagogical value, using qualitative review by comparing responses to ideal educational feedback. Metrics like semantic similarity to expected outputs may also be applied if feasible. My approach prioritizes practicality, selecting models like DeepSeek-Coder V2 Lite for their balance of performance and resource efficiency, as larger models may be accurate but require costly hardware. This decision reflects the need for scalable tools in educational settings, where interpretability and low deployment barriers are critical.

Reasoning

What makes a model suitable for high-level competence analysis?
A suitable model excels in parsing Python code and generating natural language insights that pinpoint conceptual gaps, such as misunderstanding recursion or data structures. It should produce nuanced, non-solution-revealing prompts, be open source for ethical customization, and support fine-tuning for educational use. Models with strong code reasoning, like DeepSeek-Coder V2, are ideal due to their performance on programming tasks.

How would you test whether a model generates meaningful prompts?
I would test the model with varied Python code samples containing common student errors, using prompts like "Suggest questions to probe the student’s understanding without correcting the code." Outputs would be scored for relevance, encouragement of critical thinking, and alignment with teaching goals, potentially supplemented by expert review or similarity metrics to benchmark educational feedback.

What trade-offs might exist between accuracy, interpretability, and cost?
Larger models offer higher accuracy but are less interpretable and require expensive compute resources (e.g., GPUs). Smaller models, like DeepSeek-Coder V2 Lite, are more interpretable and affordable but may lack depth in nuanced analysis. In education, prioritizing interpretability and low cost often outweighs marginal accuracy gains to ensure accessibility.

Why did you choose the model you evaluated, and what are its strengths or limitations?
DeepSeek-Coder V2 (Lite-Instruct) was chosen for its open source MIT license, high HumanEval scores, and support for 338 languages with a 128K token context, ideal for analyzing complex Python code. Strengths include robust code reasoning and adaptability for educational prompting. Limitations include GPU requirements for full inference, potential for occasional inaccuracies in subtle feedback, and the need for careful prompt design to avoid solution leakage.

Setup Instructions
To replicate the evaluation environment for DeepSeek-Coder V2:


Install dependencies:
pip install transformers torch

Download the model:
from transformers import AutoModelForCausalLM
model = AutoModelForCausalLM.from_pretrained('deepseek-ai/DeepSeek-Coder-V2-Lite-Instruct')



Ensure a Python environment (version 3.8 or higher) with sufficient memory (at least 8GB RAM for the Lite model; GPU recommended for faster inference).
Test with sample Python code snippets, using prompts like: "Analyze this code for potential misconceptions without providing the correct solution."
For full details, refer to the Hugging Face model card: DeepSeek-Coder V2.

References
DeepSeek-Coder V2 on Hugging Face: https://huggingface.co/deepseek-ai/DeepSeek-Coder-V2-Lite-Instruct
HumanEval benchmark: https://github.com/openai/human-eval



FOSSEE Official Website: https://fossee.in/
