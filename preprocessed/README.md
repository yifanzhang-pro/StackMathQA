## Preprocessed Data

**Please refer to https://huggingface.co/datasets/math-ai/StackMathQA for downloading the whole dataset.**

In the `./stackexchange-math` directory and `./stackexchange-math--1q1a` directory, you will find the data structured in two formats:

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