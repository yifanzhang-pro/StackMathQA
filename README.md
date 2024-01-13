# StackMathQA
StackMathQA is a meticulously curated collection of **2 million** mathematical questions and answers, sourced from various Stack Exchange sites. This repository is designed to serve as a comprehensive resource for researchers, educators, and enthusiasts in the field of mathematics and AI research.

**Please refer to https://huggingface.co/datasets/math-ai/StackMathQA for downloading the whole dataset.**

## Configs

```YAML
configs:
- config_name: stackmathqa1600k
  data_files: data/stackmathqa1600k/all.jsonl
  default: true
- config_name: stackmathqa800k
  data_files: data/stackmathqa800k/all.jsonl
- config_name: stackmathqa400k
  data_files: data/stackmathqa400k/all.jsonl
- config_name: stackmathqa200k
  data_files: data/stackmathqa200k/all.jsonl
- config_name: stackmathqa100k
  data_files: data/stackmathqa100k/all.jsonl
- config_name: stackmathqafull-1q1a
  data_files: preprocessed/stackexchange-math--1q1a/*.jsonl
- config_name: stackmathqafull-qalist
  data_files: preprocessed/stackexchange-math/*.jsonl
```

## Preprocessed Data
In the `./preprocessed/stackexchange-math` directory and `./preprocessed/stackexchange-math--1q1a` directory, you will find the data structured in two formats:

1. **Question and List of Answers Format**:
   Each entry is structured as {"Q": "question", "A_List": ["answer1", "answer2", ...]}.
   - `math.stackexchange.com.jsonl`: 827,439 lines
   - `mathoverflow.net.jsonl`: 90,645 lines
   - `stats.stackexchange.com.jsonl`: 103,024 lines
   - `physics.stackexchange.com.jsonl`: 117,318 lines
   - In total: **1,138,426** questions

```YAML
dataset_info:
  features:
    - name: Q
      dtype: string
      description: "The mathematical question in LaTeX encoded format."
    - name: A_list
      dtype: sequence
      description: "The list of answers to the mathematical question, also in LaTeX encoded."
    - name: meta
      dtype: dict
      description: "A collection of metadata for each question and its corresponding answer list."
```

2. **Question and Single Answer Format**:
   Each line contains a question and one corresponding answer, structured as {"Q": "question", "A": "answer"}. Multiple answers for the same question are separated into different lines.
   - `math.stackexchange.com.jsonl`: 1,407,739 lines
   - `mathoverflow.net.jsonl`: 166,592 lines
   - `stats.stackexchange.com.jsonl`: 156,143 lines
   - `physics.stackexchange.com.jsonl`: 226,532 lines
   - In total: **1,957,006** answers
  
```YAML
dataset_info:
  features:
    - name: Q
      dtype: string
      description: "The mathematical question in LaTeX encoded format."
    - name: A
      dtype: string
      description: "The answer to the mathematical question, also in LaTeX encoded."
    - name: meta
      dtype: dict
      description: "A collection of metadata for each question-answer pair."
```
  
## Selected Data
The dataset has been carefully curated using importance sampling. We offer selected subsets of the dataset (`./preprocessed/stackexchange-math--1q1a`) with different sizes to cater to varied needs:

```YAML
dataset_info:
  features:
    - name: Q
      dtype: string
      description: "The mathematical question in LaTeX encoded format."
    - name: A
      dtype: string
      description: "The answer to the mathematical question, also in LaTeX encoded."
    - name: meta
      dtype: dict
      description: "A collection of metadata for each question-answer pair."
```

### StackMathQA1600K
- Location: `./data/stackmathqa1600k`
- Contents:
  - `all.jsonl`: Containing 1.6 million entries.
  - `meta.json`: Metadata and additional information.

```bash
Source: Stack Exchange (Math), Count: 1244887
Source: MathOverflow, Count: 110041
Source: Stack Exchange (Stats), Count: 99878
Source: Stack Exchange (Physics), Count: 145194
```

Similar structures are available for StackMathQA800K, StackMathQA400K, StackMathQA200K, and StackMathQA100K subsets.

### StackMathQA800K
- Location: `./data/stackmathqa800k`
- Contents:
  - `all.jsonl`: Containing 800k entries.
  - `meta.json`: Metadata and additional information.
 
```bash
Source: Stack Exchange (Math), Count: 738850
Source: MathOverflow, Count: 24276
Source: Stack Exchange (Stats), Count: 15046
Source: Stack Exchange (Physics), Count: 21828
```

### StackMathQA400K

- Location: `./data/stackmathqa400k`
- Contents:
  - `all.jsonl`: Containing 400k entries.
  - `meta.json`: Metadata and additional information.
  
```bash
Source: Stack Exchange (Math), Count: 392940
Source: MathOverflow, Count: 3963
Source: Stack Exchange (Stats), Count: 1637
Source: Stack Exchange (Physics), Count: 1460
```
 
### StackMathQA200K

- Location: `./data/stackmathqa200k`
- Contents:
  - `all.jsonl`: Containing 200k entries.
  - `meta.json`: Metadata and additional information.

```bash
Source: Stack Exchange (Math), Count: 197792
Source: MathOverflow, Count: 1367
Source: Stack Exchange (Stats), Count: 423
Source: Stack Exchange (Physics), Count: 418
```

### StackMathQA100K

- Location: `./data/stackmathqa100k`
- Contents:
  - `all.jsonl`: Containing 100k entries.
  - `meta.json`: Metadata and additional information.

```bash
Source: Stack Exchange (Math), Count: 99013
Source: MathOverflow, Count: 626
Source: Stack Exchange (Stats), Count: 182
Source: Stack Exchange (Physics), Count: 179
```

## Citation
We appreciate your use of StackMathQA in your work. If you find this repository helpful, please consider citing it and star this repo. Feel free to contact zhangyif21@tsinghua.edu.cn or open an issue if you have any questions.

```bibtex
@misc{stackmathqa2024,
      title={StackMathQA: A Curated Collection of 2 Million Mathematical Questions and Answers Sourced from Stack Exchange}, 
      author={Zhang, Yifan},
      year={2024},
}
```
