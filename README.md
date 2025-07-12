<p align="center">
    <a href="https://arxiv.org/pdf/2506.16395">
        <img alt="Static Badge" src="https://img.shields.io/badge/Paper-Arxiv-red">
    </a>
    <a href="https://huggingface.co/datasets/KbsdJames/Omni-MATH">
        <img alt="Static Badge" src="https://img.shields.io/badge/HFDataset-OmniMATH-yellow">
    </a>
    <a href="https://huggingface.co/KbsdJames/Omni-Judge">
        <img alt="Static Badge" src="https://img.shields.io/badge/OmniJudge-OmniMATH-yellow">
    </a>
    <a href="https://huggingface.co/KbsdJames/Omni-Judge">
        <img alt="Static Badge" src="https://img.shields.io/badge/Github-Rule_based_Eval-black">
    </a>
    <a href="https://omni-math.github.io/">
        <img alt="Static Badge" src="https://img.shields.io/badge/ProjectPage-Online-blue">
    </a>
    <a href="https://www.qbitai.com/2024/09/193751.html">
        <img alt="Static Badge" src="https://img.shields.io/badge/Report-Qbitai-green">
    </a>
</p>

## 🔥News

- *2025-7*: We have open-sourced our evaluation code and are continually improving it.

- *2025-6*: We have released the OJBench dataset and our paper.

*OJBench is a comprehensive and challenging benchmark specifically designed to assess LLMs’ code-reasoning capabilities at the competition level. Our dataset focuses exclusively on human programming contests and comprises 232 rigorously-selected competition problems sourced from China’s National Olympiad in Informatics (NOI) and the International Collegiate Programming Contest (ICPC). These problems are meticulously classified into three difficulty tiers—Easy, Medium, and Hard—derived from contestant voting and real-world submission statistics, and span across bilingual evaluation in both Python and C++.We evaluate numerous models on OJBench, covering open-source/closed-source, reasoning/non-reasoning, 7 B–671 B models.*

## Key Findings: Performance of State-of-the-Art Models

> ⚠️ **State-of-the-Art Models Struggle**  
> Even advanced reasoning-oriented models, such as o4-mini and Gemini-2.5-pro-exp, struggle with highly challenging competition-level problems.

> 📈 **Reasoning Models Outperform**  
> Reasoning-oriented models significantly outperformed non-reasoning-oriented models in competitive coding tasks.

> 🔄 **Open-Source vs Closed-Source Gap**  
> Open-source models were observed to still lag behind closed-source models in terms of code reasoning ability.

> ⚡ **C++ Performance Advantage**  
> For most long-chain-of-thought (CoT) models, using C++ resulted in better performance compared to Python.

> 🛠️ **Feedback Utilization**  
> Models are capable of leveraging feedback from the code execution environment to refine their erroneous solutions.

> 📄 **For More Details**  
> Please refer to the full paper for experimental design, evaluation metrics, and comprehensive analysis.

------

## Prerequisites

Ensure you have Python 3.10+ installed, along with Git.

---

## 1. Install DMOJ

Clone the DMOJ repository, check out the specific commit, and install it:

```bash
# Clone the repository
git clone https://github.com/DMOJ/judge-server.git
cd judge-server

# Pin to a known stable version
git checkout f098cd3a49a60186d1fadde5132329ec5f4f2213

# Install into the current Python environment
pip install .
```

---

## 2. Install OJBench

Clone the OJBench library and install it in editable mode:

```bash
# Clone the OJBench repository
git clone git@github.com:He-Ren/OJBench.git
cd OJBench

# Install into the current Python environment
pip install .
```

---

## 3. Download Test Data

Test inputs are hosted on Hugging Face under `He-Ren/OJBench_testdata`. You can clone with Git LFS. Ensure Git LFS is installed (`git lfs install`), then run:

  ```bash
  git clone https://huggingface.co/He-Ren/OJBench_testdata
  ```

---

## 4. Usage / Testing

### Initialization

Use the `init` function to set up the judging environment. Provide one or more problem directories (for example, `data/NOI` and `data/ICPC`).

### Running Judging on JSONL Input

To evaluate submissions in batch, call `judge_jsonl_data`
