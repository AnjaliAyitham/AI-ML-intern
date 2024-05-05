**Prompt Engineering**
"prompting" refers to the art and science of formulating precise instructions or queries provided to the model to generate desired outputs.
prompting refers to crafting or designing the input given to a language model like me to elicit specific responses or behaviors. 
### **Prompt Engineering**
 It's a collaborative process where users and models work together to achieve the desired outcome.
 ** Adversarial prompting which involves intentionally crafting prompts to exploit weaknesses or biases in a language model, with the goal of generating responses that may be misleading, inappropriate, or showcase the model's limitations. Safeguarding models from providing harmful responses is a challenge that needs to be solved and is an active research area.
### Why Prompting?
Large language models are trained through unsupervised learning on vastdata. During training, the model learns to predict the next word in a sentence based on the context provided by the preceding words. This process allows the model to capture grammar, facts, reasoning abilities, and even some aspects of common sense.Prompting is a crucial aspect of using these models effectively
**Prompting LLM in right way**
1.Contextual Understanding
2.Training Data Patterns
3.Transfer Learning
4.Contextual Prompts for Contextual Responses
5.Mitigating Bias
**Principles of prompting**
Instruction:specify the task or action you want the model to perform. 
Context: Provide external information or additional context-better understand the task-generate more accurate responses. 
Input Data: Include the input or question for which you seek a response.which you want the model to act.
Output Indicator: Define the type or format of the desired output. This guides the model-that aligns with your expectations.
## **Best practices for prompt engineering using the OpenAI API
1.Use the Latest Model 
2.Structure Instructions: Place instructions at the beginning of the prompt and use ### or """ to separate the instruction and context for clarity and effectiveness.
3.Be Specific and Descriptive
4.Specify Output Format with Examples
5.Use Zero-shot, Few-shot, and Fine-tune Approach: Begin with a zero-shot approach, followed by a few-shot approach (providing examples). If neither works, consider fine-tuning the model.
![Alt text](assets/prompt.png)
6.Avoid Fluffy Descriptions
7.Provide Positive Guidance
8.Code Generation Specific
 **Advanced Prompting Techniques**
![Alt text](assets/prompting_11.png)
 ## **Step-by-Step Modular Decomposition**
 breaking down complex problems into smaller, manageable steps, facilitating a structured approach to problem-solving. These methods guide the LLM through a sequence of intermediate steps, allowing it to focus on solving one step at a time rather than tackling the entire problem in a single step. This approach enhances the reasoning abilities of LLMs and is particularly useful for tasks requiring multi-step thinking.
 **Chain-of-Thought (CoT) Prompting:**
  to enhance complex reasoning capabilities through intermediate reasoning steps. This method involves providing a sequence of reasoning steps that guide a large language model (LLM) through a problem, allowing it to focus on solving one step at a time.
  ![Alt text](assets/prompting_1.png)
  1a. Zero-shot/Few-Shot CoT Prompting:
  ![Alt text](assets/prompting_2.png)
  1b. Automatic Chain-of-Thought (Auto-CoT):

Automatic Chain-of-Thought (Auto-CoT) was designed to automate the generation of reasoning chains for demonstrations. Instead of manually crafting examples, Auto-CoT leverages LLMs with a "Let's think step by step" prompt to automatically generate reasoning chains one by one.
![Alt text](assets/prompting_2.png)
The Auto-CoT process involves two main stages:

Question Clustering: Partition questions into clusters based on similarity.
Demonstration Sampling: Select a representative question from each cluster and generate its reasoning chain using Zero-Shot-CoT with simple heuristics.
**Tree-of-Thoughts (ToT) Prompting**
***Coherent Units ("Thoughts"):*** ToT prompts LLMs to consider coherent units of text as intermediate reasoning steps.
***Deliberate Decision-Making***: Enables models to make decisions intentionally and evaluate different reasoning paths.
***Backtracking and Looking Ahead***: Allows models to backtrack or look ahead during the reasoning process, providing flexibility in problem-solving.
![Alt text](assets/prompting_4.png)
***Graph of Thought Prompting***
a novel approach that models thoughts not just as chains but as graphs, capturing the intricacies of non-sequential thinking.
Nodes in the graph symbolize these thought units, and edges depict connections, presenting a more realistic portrayal of the complexities inherent in human cognition. GoT employs Directed Acyclic Graphs (DAGs), allowing the modeling of paths that fork and converge.
![Alt text](assets/prompting_5.png)
## **B. Comprehensive Reasoning and Verification**
--> sophisticated approach where reasoning is not just confined to providing a final answer but involves generating detailed intermediate steps. The distinctive aspect of these techniques is the integration of a self-verification mechanism within the framework.
-->it autonomously verifies their consistency and correctness. If the internal verification yields a false result, the model iteratively refines its responses, ensuring that the generated reasoning aligns with the expected logical coherence. These checks contributes to a more robust and reliable reasoning process
-->Automatic Prompt Engineer
Automatic Prompt Engineer (APE) is a technique that treats instructions as programmable elements and seeks to optimize them by conducting a search across a pool of instruction candidates proposed by an LLM. 
--> APE employs a scoring function to evaluate the effectiveness of candidate instructions. The selected instruction, determined by the highest score, is then utilized as the prompt for the LLM. This automated approach aims to enhance the efficiency of prompt generatio
![Alt text](assets/prompting_6.png)
**Chain of Verification (CoVe)**
The Chain-of-Verification (CoVe) method addresses the challenge of hallucination in large language models by introducing a systematic verification process. It begins with the model drafting an initial response to a user query, potentially containing inaccuracies. CoVe then plans and poses independent verification questions, aiming to fact-check the initial response without bias. The model answers these questions, and based on the verification outcomes, generates a final response.
![Alt text](assets/prompting_7.png)
-->***Self Consistency***
Self Consistency represents a refinement in prompt engineering, specifically targeting the limitations of naive greedy decoding in chain-of-thought prompting. The core concept involves sampling multiple diverse reasoning paths using few-shot CoT and leveraging the generated responses to identify the most consistent answer.
 ![Alt text](assets/Screenshot_2024-01-14_at_3.50.46_PM.png)
 ![Alt text](assets/Screenshot_2024-01-14_at_3.53.32_PM.png)
**How ReAct Works:**
Dynamic Reasoning and Acting
Interaction with External Environments
Improved Task Performance
Enhanced Human Interpretability
***Active Prompting (Aggregation)***
Dynamic Querying
Uncertainty Metric
Selective Annotation
Adaptive Learning
![Alt text](assets/prompting_8.png)
***Automatic Multi-step Reasoning and Tool-use (ART) (External Tools)***
ART emphasizes on task handling with LLMs. This framework integrates Chain-of-Thought prompting and tool usage by employing a frozen LLM. Instead of manually crafting demonstrations, ART selects task-specific examples from a library and enables the model to automatically generate intermediate reasoning steps.
![Alt text](assets/prompting_9.png)
***Chain-of-Knowledge (CoK)***
This framework aims to bolster LLMs by dynamically integrating grounding information from diverse sources, fostering more factual rationales and mitigating the risk of hallucination during generation. CoK operates through three key stages: reasoning preparation, dynamic knowledge adapting, and answer consolidation. It starts by formulating initial rationales and answers while identifying relevant knowledge domains. Subsequently
![Alt text](assets/prompting_10.png)
**Risks**
Prompting comes with various risks, and prompt hacking is a notable concern that exploits vulnerabilities in LLMs. The risks associated with prompting include:
Prompt Injection:
Prompt Leaking:
Jailbreaking:
Bias and Misinformation:
Security Concerns.

### Popular Tools
Here is a collection of well-known tools for prompt engineering. While some function as end-to-end app development frameworks, others are tailored for prompt generation and maintenance or evaluation purposes. 
**PromptAppGPT:**
 A low-code prompt-based rapid app development framework.
PromptBench:
A PyTorch-based Python package for the evaluation of LLMs.
**Prompt Engine:**
An NPM utility library for creating and maintaining prompts for LLMs.
Background
**Prompts AI:**
An advanced GPT-3 playground with a focus on helping users discover GPT-3 capabilities 
**OpenPrompt:**
 A library built upon PyTorch for prompt-learning, adapting LLMs to downstream NLP tasks.
**Promptify**:
Test suite for LLM prompts, perform NLP tasks in a few lines of code, handle out-of-bounds predictions