# Evaluate the bias, trustworthiness and fairness of open source LLMs (theme – users susceptible to phishing or phishing victims)
This repository contains the experiment codes to evaluate the toxicity, bias/stereotypes, factuality, privacy/security, fairness, and ethical reasoning of open source LLMs (theme – users susceptible to phishing or phishing victims).

## 📖 Project Overview

These experiment codes follow the evaluation strategies from the DECODINGTRUST framework, quantitatively evaluating and analysing the responses of an open-source LLM from six dimensions (toxicity, bias/stereotypes, factuality, privacy/security, fairness, and ethical reasoning). 

## 🛠 LLM & Dataset

1. Test Open-source LLM: Microsoft/Phi-2 is selected (https://huggingface.co/microsoft/phi-2), which is a language model with approximately 2.7B parameters, demonstrating strong performance on common language understanding, reasoning, and logic tasks. The LLM has not undergone instruction fine-tuning or human feedback reinforcement, making it convenient for researchers to explore LLM behaviour, stereotype bias, and security issues (Microsoft 2023). Additionally, Phi-2 is released on Hugging Face under the MIT Open Source License, allowing its use in research, education, and even commercial projects.
2. Test dataset: The phishing messages, relate to sensitive issues faced by vulnerable groups, are selected from the SMS Spam Collection dataset on Hugging Face, based on the personality traits of victims who participated in the phishing attacks.

## 🔍 Evaluation methods

### 1. Evaluation on Toxicity

Let the LLM respond of 102 manually selected phishing messages according to the benign prompt and the adversarial prompt. Then check every response and get toxicity scores by using Detoxify library, and calculate the Expected Maximum Toxicity (EMT) and Toxicity Probability (TP) to evaluate the toxicity of the LLM's responses.

### 2. Evaluation on Bias/Stereotypes

Manually select 50 phishing messages and have the LLM determine whether these messages contain the stereotypes that "Poor people are easily deceived" and "Rich people are easily deceived". For each stereotype, design two types of prompts: “benign" and “adversarial". Then examine the LLM's responses to verify whether they contain stereotypes, and count the number of responses containing stereotypes to assess the degree of stereotype presence of the LLM's responses.

### 3. Evaluation on Factuality

Manually select 50 fake phishing messages and design two types of prompts: "benign" and "adversarial". Let the LLM determine whether message is real. Then count the number of correct judgments in the LLM responses to assess the degree of factuality presence of the LLM's responses.

### 4. Evaluation on Privacy/Security

Provide the LLM with 50 manually selected phishing messages, along with a mock name and email address. Then examine the LLM's responses under two types of prompts: "benign" and "adversarial" to determine if the model contains sensitive information such as the mock name and email address with Presidio, which is an open-source library from Microsoft for detecting privacy-sensitive information (PII).

### 5. Evaluation on Privacy/Security

The LLM is required to determine whether a man, a woman, or anyone will reply to 50 gender-neutral phishing messages manually selected under two types of prompts: "benign" and "adversarial". Based on the responses, the LLM should be assessed for gender-related fairness issues.

### 6. Evaluation on Privacy/Security

Give the LLM 50 unethical phishing messages manually selected and force the LLM judge which messages are unethical according to two designed prompts "benign" and "adversarial". Then examine the LLM's ethical reasoning by the number of correct judgments.

## 📈 Summary of Results

This experiment demonstrates that following the DECODINGTRUST framework for LLM response testing and result evaluation can quantitatively assess the bias, trustworthiness, and fairness of open-source LLM, as shown in the data in the table below and the result analysis of the six dimensions of the DECODINGTRUST framework on the previous slides, and designing appropriate prompts is crucial for evaluating LLM performance.
The experiment also showed that the LLM needs carefully deal with adversarial prompts from user inputs, so that the LLM can learn to handle such prompts safely.


## 🚀 Getting Started

### Prerequisites

* Python 3.10.11+
* GPU (Recommended for inference)

### Installation

```bash
pip install transformers accelerate torch datasets pandas detoxify presidio-analyzer

```

### How to Run

1. Clone the repository:
```bash
git clone https://github.com/your-username/assignment2.git

```


2. Open the Jupyter Notebook:
```bash
jupyter notebook assignment2_0_prepare_dataset.ipynb
jupyter notebook assignment2_1_toxicity.ipynb
jupyter notebook assignment2_2_stereotype.ipynb
jupyter notebook assignment2_3_factuality.ipynb
jupyter notebook assignment2_4_private.ipynb
jupyter notebook assignment2_5_fairness.ipynb
jupyter notebook assignment2_6_ethics.ipynb

```


## 📚 References

Versha, V. (2025). Large language models market size, share & growth [2031]. Kings Research. https://www.kingsresearch.com/large-language-models-market-1661
Bommasani, R., Hudson, D. A., Adeli, E., Altman, R., Arora, S., von Arx, S., ... & Liang, P. (2021). On the opportunities and risks of foundation models. arXiv preprint arXiv:2108.07258.
Wang, B., Chen, W., Pei, H., Xie, C., Kang, M., Zhang, C., ... & Li, B. (2023). DecodingTrust: A Comprehensive Assessment of Trustworthiness in {GPT} Models.
Microsoft. (2023). PHI-2 [Large language model]. Hugging Face. https://huggingface.co/microsoft/phi-2?utm_source=chatgpt.com
Weidinger, L., Uesato, J., Rauh, M., Griffin, C., Huang, P. S., Mellor, J., ... & Gabriel, I. (2022). Taxonomy of risks posed by language models. In Proceedings of the 2022 ACM conference on fairness, accountability, and transparency (pp. 214-229).
Chui, M., Yee, L., Hall, B., & Singla, A. (2023). The state of AI in 2023: Generative AI’s breakout year.
Wiemann, R., Terei, N., & Raatz, A. (2024). Large Language Model for Intuitive Control of Robots in Micro-Assembly. 2024 IEEE 20th International Conference on Automation Science and Engineering (CASE), 3957-3962.

---

### Project Structure
* `assignment2_0_prepare_dataset.ipynb`:  Download the SMS Spam Collection dataset on Hugging Face.
* `assignment2_1_toxicity.ipynb`: The notebook containing evaluation on Toxicity and result visualization.
* `assignment2_2_stereotype.ipynb`: Evaluation on Bias/Stereotypes and result visualization.
* `assignment2_3_factuality.ipynb`: Evaluation on Factuality and result visualization.
* `assignment2_4_private.ipynb`: Evaluation on Privacy/Security and result visualization.
* `assignment2_5_fairness.ipynb`: Evaluation on Fairness and result visualization.
* `assignment2_6_ethics.ipynb`: Evaluation on Ethical Reasoning and result visualization.
* `README.md`: Project documentation.
