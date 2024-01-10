# StackMathQA
StackMathQA is a meticulously curated collection of **2 million** mathematical questions and answers, sourced from various Stack Exchange sites. This repository is designed to serve as a comprehensive resource for researchers, educators, and enthusiasts in the field of mathematics and data science.

**Please refer to https://huggingface.co/datasets/math-ai/StackMathQA for downloading the whole dataset.**

## Preprocessed Data
In the `./preprocessed/stackexchange-math` directory and `./preprocessed/stackexchange-math--1q1a` directory, you will find the data structured in two formats:

1. **Question and List of Answers Format**:
   Each entry is structured as {"Q": "question", "A_List": ["answer1", "answer2", ...]}.
   - `math.stackexchange.com.jsonl`: 827,439 lines
   - `mathoverflow.net.jsonl`: 90,645 lines
   - `stats.stackexchange.com.jsonl`: 103,024 lines
   - `physics.stackexchange.com.jsonl`: 117,318 lines
   - In total: **1,138,426** questions

2. **Question and Single Answer Format**:
   Each line contains a question and one corresponding answer, structured as {"Q": "question", "A": "answer"}. Multiple answers for the same question are separated into different lines.
   - `math.stackexchange.com.jsonl`: 1,407,739 lines
   - `mathoverflow.net.jsonl`: 166,592 lines
   - `stats.stackexchange.com.jsonl`: 156,143 lines
   - `physics.stackexchange.com.jsonl`: 226,532 lines
   - In total: **1,957,006** answers
  
## Selected Data
The dataset has been carefully curated using importance sampling. We offer selected subsets of the dataset (`./preprocessed/stackexchange-math--1q1a`) with different sizes to cater to varied needs:

### StackMathQA1600K
- Location: `./data/stackmathqa1600k`
- Contents:
  - `all.jsonl`: Containing 1.6 million entries.
  - `meta.json`: Metadata and additional information.

### StackMathQA800K
- Location: `./data/stackmathqa800k`
- Contents:
  - `all.jsonl`: Containing 800k entries.
  - `meta.json`: Metadata and additional information.

Similar structures are available for StackMathQA400K, StackMathQA200K, and StackMathQA100K subsets.

## Citation
We appreciate your use of StackMathQA in your work. If you find this repository helpful, please consider citing it and star this repo. Feel free to contact zhangyif21@tsinghua.edu.cn or open an issue if you have any questions.

```bibtex
@misc{stackmathqa2024,
      title={StackMathQA: A Curated Collection of 2 Million High-Quality Mathematical Questions and Answers Sourced from Stack Exchange}, 
      author={Yifan Zhang, et al.},
      year={2024},
}
```
