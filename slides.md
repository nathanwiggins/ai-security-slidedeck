# Introduction

## Title Slide

## Presenters
Luke Sheneman, Director of Research Computing, University of Idaho (photo: sheneman.jpg)
Nathan Wiggins, Data Scientist, Southern Utah University (photo: wiggins.jpg)

## Presentation Overview
Section I: AI Model Training
Section II: Malicious Attacks
Section III: Risk Classification
(Classy looking cards with icons next to each of them)

# Section 1

## 01 AI Model Training

## Interactive Question
True or False: AI models are trained on recognizing patterns and cannot expose the raw data they were trained on
(This is false)

## What is an AI Model?
Two images side by side. Left: whatis.png — the major families of AI models (LLMs, computer vision, transformers, diffusion models, reinforcement learning). Right: ai-nesting.webp — nested fields showing AI ⊃ Machine Learning ⊃ Neural Networks ⊃ Transformers ⊃ LLMs.

## Neural Networks
(Large graphic — neural3.png — a neural network classifying a handwritten digit: 784 input pixels feeding hidden layers that output digits 0–9. "Images are tensors!")

## Inspired by Biology
Two-column layout. Left: neu.png — a real biological neuron (dendrites, soma, axon, synapse) alongside its mathematical model. Right (stacked): neural2.png — a single artificial neuron (inputs X1/X2 × weights W1/W2, summed with bias → output y); neural1.jpg — a fully connected network (input layer, two hidden layers, output layer).

## Data to Features
(Large graphic — hier1.png — hierarchical feature learning across network depth: low-level features (edges, dark spots) → mid-level features (eyes, ears, nose) → high-level features (facial structure))

## Transformers!
Two-column layout. Left: att.png — the "Attention Is All You Need" paper that introduced the Transformer. Right: abstract.png — Transformers understand language across levels of abstraction (leaves = specific words → branch = parts → tree = the whole → plant = more abstract concept).

## Training vs. Inference
(Large graphic — training_vs_inference.jpg — Training: many users' labeled images train a model → Trained Model. Inference: a user submits a new image and the trained model predicts an output label, e.g. "Cat".)

## Interactive Visual
(Visually appealing process flow animations that show the AI model training process, that the user can click on to show the steps in the process one by one)

## Raw Data
Two side-by-side tables — what goes into a model, and how that's grown.

GPT-3 training data (2020):
| Dataset | Tokens | Proportion |
| Common Crawl | 410 billion | 60% |
| WebText2 | 19 billion | 22% |
| Books1 | 12 billion | 8% |
| Books2 | 55 billion | 8% |
| Wikipedia | 3 billion | 3% |

Frontier models today (estimated pretraining tokens):
| Model family | Pretraining tokens |
| GPT-5 | 30–80T |
| Claude 4 | 30–70T |
| Gemini 2.5/3 | 40–100T |
| Grok 3 | 30–80T |

## Data Processing
(Large graphic — data_processing.png — "From Raw Data to Training an LLM": 1) Raw Data (web pages, books, code, conversations) → 2) Clean & Filter → 3) Deduplicate → 4) Format & Tokenize → 5) Training Data)

## Training Loop
(Large graphic — training_loop.png — Before Training: a randomly-initialized network makes poor predictions → Training (Gradient Descent): iteratively update weights to descend the loss curve from high to low loss → After Training: the trained network fits the data and makes better predictions. Start with random weights → gradient descent minimizes loss → better predictions (lower loss).)

## 3 Stages of LLM Training
(Large graphic — llm_training_stages.png — 1) Pre-training on broad web text, code, and images → Base LLM; 2) Supervised Fine Tuning on question/answer pairs → SFT Model; 3) Reinforcement Learning from human preference ratings → RL Model.)

## Models Deployed for Inference
(Large graphic — models_deployed_inference.png — A deployed model is "frozen" and no longer learning: inputs (images, text, tables) flow into a locked/frozen model that produces inference outputs (classification, sentiment, scores). No training, no updates, no learning — used only for inference.)

## Model Inversion
(Visually appealing process flow animations that demonstrates how a bad actor might try to gain access to the raw data used to train the model)

## Response Mining
(Large graphic — response_mining.png — Sensitive records (passwords, credit card and SSN numbers) behind a locked database are absorbed into an LLM during training; an attacker repeatedly queries the deployed model and reconstructs the private data from its responses.)

## Takeaways
Key: Understand how your data is being used
-Check the terms and conditions of the AI tools you are using (show some common examples) Enterprise licenses provide more protection
-Consider using on-premises AI models, if available
(Classic slide with icons)

# Section 2

## 02 Malicious Attacks

## Interactive Question
Which resume will an AI evaluator rank higher for a job in research administration?

## Resume 1 vs Resume 2
(Simple outlines of PDF resumes, side by side, one for a candidate with related experience, one for a candidate with general experience. The correct answer to the question from the slide prior is the second resume, because it has hidden white text on it that tells the AI model to choose it and describe that candidate as the most qualified.)

## AI Prompts
(An overview of the various components of an AI prompt. This includes the user's prompt, but also includes system prompts, and the context associated with the prompt (uploads, attachments, etc.) Show how this could be structured)

## Prompt Injection
(Description and examples of prompt injection techniques)

## Prompt Injection with Agentic AI
(Large graphic — prompt_injection_agentic.png — A user asks an AI agent to analyze their spending, but a hidden injected prompt tells the agent to ignore previous instructions and access the user's bank account. With tools/access to web search, documents, and a private bank account, the agent exfiltrates sensitive data — account number, balance, and transactions.)

## Takeaways
Key: Monitor what is being processed by your models
-Do not inherently trust received documents, emails, or code and recognize that more is being processed than just what you type.
-Be careful with agentic systems in auto-mode when dealing with sensitive data
(Classic slide with icons)

# Section 3

## 03 Risk Classification

## Interactive Question
According to a 2026 study by TrustedTech, which group uses unapproved AI tools at work more?
A. Senior Decision-Makers (correct)
B. Junior Employees

Reference (display after correct answer shown): https://www.businesswire.com/news/home/20260519849160/en/TrustedTech-Global-and-U.S.-Data-Reveals-Senior-Leaders-Are-the-Biggest-Source-of-Shadow-AI-Risk-in-Organizations?utm_campaign=shareaholic&utm_medium=copy_link&utm_source=bookmark


## Interactive Classify Data Risk
(Interface where the user can classify various data types as high, moderate, or low risk, in terms of research administration data in higher education)

## Approve Services for Risk
(Show example services that are authorized to handle various categories of data. For High Risk, locally hosted models (and some AI providers with an enterprise license), For Moderate Risk, enterprise license with a fronteir provider, For Low Risk, some generic AI service. Final animated step: a warning banner at the bottom pointing at the High Risk card — "On-prem AI security is not guaranteed — it must be built and monitored.")

## Locally Hosted Models
(Highlight the NVIDIA DGX Spark, which is a small super-computer that could sit on a person's desk, costs less than $5,000, and is capable of hosting really good local AI models. Highlight that SUU is currently doing this)

## Takeaways
Key: Standardized guidance is key for maintaining security
-Well thought-through policies, procedures, and data classification help make decision making clear for employees and reduce the uncertainty and risk for data security incidents
(Classic slide with bullets)

# Conclusion

## Question and Answer Time

## Contact Information
Luke Sheneman: sheneman@uidaho.edu (photo: sheneman.jpg)
Nathan Wiggins: nathanwiggins@suu.edu (photo: wiggins.jpg)
