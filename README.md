<div align="center">

# StackMathQA

[![Technical Report](https://img.shields.io/badge/Technical-Report-blue)](https://stackmathqa.github.io/StackMathQA.pdf)
[![Website](https://img.shields.io/badge/Project-Website-green)](https://stackmathqa.github.io)
[![StackMathQA](https://img.shields.io/badge/Huggingface-Datasets-blue)](https://huggingface.co/datasets/math-ai/StackMathQA)


StackMathQA: A Curated Collection of 2 Million Mathematical Questions and Answers Sourced from Stack Exchange

</div>

**StackMathQA** is a large-scale dataset featuring nearly **2 million** mathematical question-and-answer pairs, meticulously sourced from the Stack Exchange network. It is designed to be a comprehensive resource for training and evaluating large language models (LLMs) on complex reasoning tasks.

-----

## Key Features

  * **Massive Scale**: Contains approximately 2 million Q\&A pairs, providing extensive data for pre-training and fine-tuning.
  * **High-Quality Sources**: Aggregates expert and enthusiast content from premier Q\&A sites:
      * Mathematics Stack Exchange
      * MathOverflow
      * Statistics Stack Exchange (Cross Validated)
      * Physics Stack Exchange
  * **Curated Subsets**: In addition to the full dataset, we provide smaller, high-quality subsets created using **importance resampling** to ensure they are rich with valuable and informative content.
  * **Flexible Formats**: Data is available in two convenient formats: one-question-to-many-answers (`qalist`) and one-question-to-one-answer (`1q1a`).

-----

## How to Use

You can easily load any configuration of StackMathQA directly from the Hugging Face Hub.

```python
from datasets import load_dataset

# Load the default (1.6M) configuration
dataset = load_dataset("math-ai/StackMathQA", "stackmathqa1600k")

# To load a different subset, specify its name
# dataset_100k = load_dataset("math-ai/StackMathQA", "stackmathqa100k")

print(dataset['train'][0])
```

\<details\>
\<summary\>\<b\>View All Configurations\</b\>\</summary\>

  * `stackmathqa1600k` (Default): 1.6 million Q\&A pairs.
  * `stackmathqa800k`: 800,000 Q\&A pairs.
  * `stackmathqa400k`: 400,000 Q\&A pairs.
  * `stackmathqa200k`: 200,000 Q\&A pairs.
  * `stackmathqa100k`: 100,000 Q\&A pairs.
  * `stackmathqafull-1q1a`: The complete dataset of 1.9M+ pairs in a one-to-one format.
  * `stackmathqafull-qalist`: The complete dataset of 1.1M+ questions with answers grouped in a list.

\</details\>

-----

## Dataset Structure

Each data entry in the `1q1a` and curated configurations contains the following fields:

  * **`Q`** (`string`): The mathematical question, with LaTeX-encoded formulas.
  * **`A`** (`string`): The corresponding answer, also with LaTeX-encoded formulas.
  * **`meta`** (`dict`): A dictionary containing metadata, such as the source URL, question ID, answer score, and other relevant information.

For the `qalist` configuration, the `A` field is replaced by **`A_list`** (`sequence`), which is a list of all answers for the given question.

-----

## Citation

If you use StackMathQA in your research, please cite our technical report. We appreciate your support!

```bibtex
@techreport{zhang2024stackmathqa,
      title={{StackMathQA: A Curated Collection of 2 Million Mathematical Questions and Answers Sourced from Stack Exchange}},
      author={Zhang, Yifan},
      year={2024},
      institution={ASI Research},
      howpublished={\url{https://stackmathqa.github.io/StackMathQA.pdf}},
}
```
