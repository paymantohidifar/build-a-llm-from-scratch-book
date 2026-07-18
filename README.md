# Build an LLM from Scratch: Personal Study Notes & Reference

Welcome! This repository serves as a centralized hub for my personal study notes, comprehensive architecture breakdowns, and implementations derived from **Sebastian Raschka's** book, *[Build a Large Language Model (from scratch)](https://www.manning.com/books/build-a-large-language-model-from-scratch)*.

## About This Repository

The purpose of this space is to provide a structured, easily accessible technical reference for AI/ML students and practitioners. It is designed to facilitate quick reviews of core concepts, algorithmic code snippets, and custom deep learning modules covered throughout the book, including its complementary main and bonus notebook suites.

* **Environment Orchestration:** I have provided a comprehensive, lean configuration guide to provision deterministic local or cloud runtime environments using `uv` and `pixi`. For setup instructions, please refer to the [Environment Installation Guide](./llms-from-scratch/README.md).
* **Cloud Runtimes:** All main notebooks include direct links to launch the execution context immediately on Google Colab.

> [!IMPORTANT]
> **Supplemental Learning Resource:** These notes and code summaries are designed to supplement your learning. They are **not** a substitute for the source material, assignments, and structural walk-throughs provided in the official publication. To fully grasp the underlying mathematics and engineering choices, I highly recommend purchasing the original book.

---

## Curriculum Breakdown

Click the links below to access detailed notes, code blocks, and execution steps for each book chapter. You can explore the core distribution source module and bonus code [here](./llms-from-scratch/src/).

1.  **[Understanding Large Language Models](./llms-from-scratch/notebooks/ch01/notes.md)**
    * High-level explanations of the fundamental concepts behind large language models (LLMs)
    * Insights into the transformer architecture from which LLMs are derived
    * A plan for building an LLM from scratch
2.  **[Working With Text Data](./llms-from-scratch/notebooks/ch02/01_main-chapter-code/ch02.ipynb)**
    * Preparing text for large language model training
    * Splitting text into word and subword tokens
    * Byte pair encoding as a more advanced way of tokenizing text
    * Sampling training examples with a sliding window approach
    * Converting tokens into vectors that feed into a large language model
3.  **[Coding Attention Mechanisms](./llms-from-scratch/notebooks/ch03/01_main-chapter-code/ch03.ipynb)**
    * The reasons for using attention mechanisms in neural networks
    * A basic self-attention framework, progressing to an enhanced self-attention mechanism
    * A causal attention module that allows LLMs to generate one token at a time
    * Masking randomly selected attention weights with dropout to reduce overfitting
    * Stacking multiple causal attention modules into a multi-head attention module
4.  **[Implementing a GPT Model From Scratch to Generate Text](./llms-from-scratch/notebooks/ch04/01_main-chapter-code/ch04.ipynb)**
    * Coding a GPT-like large language model (LLM) that can be trained to generate human-like text
    * Normalizing layer activations to stabilize neural network training
    * Adding shortcut connections in deep neural networks
    * Implementing transformer blocks to create GPT models of various sizes
    * Computing the number of parameters and storage requirements of GPT models
5.  **[Pretraining on Unlabeled Data](./llms-from-scratch/notebooks/ch05/01_main-chapter-code/ch05.ipynb)**
    * Computing the training and validation set losses to assess the quality of LLM-generated text during training
    * Implementing a training function and pretraining the LLM
    * Saving and loading model weights to continue training an LLM
    * Loading pretrained weights from OpenAI
6.  **[Finetuning For Classification](./llms-from-scratch/notebooks/ch06/01_main-chapter-code/ch06.ipynb)**
    * Introducing different LLM fine-tuning approaches
    * Preparing a dataset for text classification
    * Modifying a pretrained LLM for fine-tuning
    * Fine-tuning an LLM to identify spam messages
    * Evaluating the accuracy of a fine-tuned LLM classifier
    * Using a fine-tuned LLM to classify new data
7.  **[Finetuning to Follow Instructions](./llms-from-scratch/notebooks/ch07/01_main-chapter-code/ch07.ipynb)**
    * The instruction fine-tuning process of LLMs
    * Preparing a dataset for supervised instruction fine-tuning
    * Organizing instruction data in training batches
    * Loading a pretrained LLM and fine-tuning it to follow human instructions
    * Extracting LLM-generated instruction responses for evaluation
    * Evaluating an instruction-fine-tuned LLM


---

## Contribution & Feedback

If you spot a typographical error, discover an incorrect tensor operation, or have an improvement suggestion for the module implementations, contributions are welcome! Please feel free to open a descriptive GitHub issue or submit a structured pull request.

---

## Licensing

This project's primary reference notes and codebase additions are open-source software licensed under the [MIT License](https://www.google.com/search?q=./LICENSE).

The original foundational materials and educational exercises derived from the work of Sebastian Raschka are distributed under the terms of the Apache License, Version 2.0. A copy of this license can be reviewed in [LICENSE-APACHE](https://www.google.com/search?q=./LICENSE-APACHE).

---

## Acknowledgments & Citations

This repository is built entirely upon the excellent technical implementations and architectural principles introduced in *Build a Large Language Model (from scratch)* by Sebastian Raschka.

If you adapt this configuration code, notes, or architectural patterns for your own research or development projects, please cite the original textbook work:

### APA Style

```text
Raschka, S. (2024). Build a Large Language Model (from scratch). Manning Publications. https://www.manning.com/books/build-a-large-language-model-from-scratch

```

### BibTeX

```bibtex
@book{raschka2024build,
  author    = {Raschka, Sebastian},
  title     = {Build A Large Language Model (From Scratch)},
  publisher = {Manning Publications},
  year      = {2024},
  month     = {September},
  isbn      = {978-1633437166},
  url       = {https://www.manning.com/books/build-a-large-language-model-from-scratch}
}

```