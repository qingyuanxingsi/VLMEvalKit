![LOGO](https://github-production-user-asset-6210df.s3.amazonaws.com/34324155/295443340-a300f073-4995-48a5-af94-495141606cf7.jpg)
<div align="center"><b>A Toolkit for Evaluating Large Vision-Language Models. </b></div>
<div align="center"><br>
<a href="https://opencompass.org.cn/leaderboard-multimodal">🏆 Learderboard </a> •
<a href="#-datasets-models-and-evaluation-results">📊Datasets & Models </a> •
<a href="#%EF%B8%8F-quickstart">🏗️Quickstart </a> •
<a href="#%EF%B8%8F-custom-benchmark-or-vlm">🛠️Support New </a> •
<a href="#-the-goal-of-vlmevalkit">🎯Goal </a> •
<a href="#%EF%B8%8F-citation">🖊️Citation </a>
<br><br>
</div>

**VLMEvalKit** (the python package name is **vlmeval**) is an **open-source evaluation toolkit** of **large vision-language models (LVLMs)**. It enables **one-command evaluation** of LVLMs on various benchmarks, without the heavy workload of data preparation under multiple repositories. In VLMEvalKit, we adopt **generation-based evaluation** for all LVLMs (obtain the answer via `generate` / `chat`  interface), and provide the evaluation results obtained with both **exact matching** and **LLM(ChatGPT)-based answer extraction**. 

## 🆕 News

- **[2024-01-11]** We have supported [**Monkey**](https://github.com/Yuliang-Liu/Monkey). 🔥🔥🔥
- **[2024-01-09]** The performance numbers on our official multi-modal leaderboards can be downloaded in json files: [**MMBench Leaderboard**](http://opencompass.openxlab.space/utils/MMBench.json), [**OpenCompass Multi-Modal Leaderboard**](http://opencompass.openxlab.space/utils/MMLB.json). We also add a [notebook](scripts/visualize.ipynb) to visualize these results.🔥🔥🔥
- **[2024-01-03]** We support **ScienceQA (Img)** (Dataset Name: ScienceQA_[VAL/TEST], [**eval results**](results/ScienceQA.md)), **HallusionBench** (Dataset Name: HallusionBench, [**eval results**](/results/HallusionBench.md)), and **MathVista** (Dataset Name: MathVista_MINI, [**eval results**](/results/MathVista.md)).  🔥🔥🔥
- **[2023-12-31]** We release the [**preliminary results**](/results/VQA.md) of three VQA datasets (**OCRVQA**, **TextVQA**, **ChatVQA**). The results are obtained by exact matching and may not faithfully reflect the real performance of VLMs on the corresponding task.
- **[2023-12-29]** We release the evaluation results of [**COCO Caption**](results/Caption.md). 🔥🔥🔥

## 📊 Datasets, Models, and Evaluation Results

**The performance numbers on our official multi-modal leaderboards can be downloaded from here !**

[**MMBench Leaderboard**](https://mmbench.opencompass.org.cn/leaderboard): http://opencompass.openxlab.space/utils/MMBench.json

[**OpenCompass Multi-Modal Leaderboard**](https://opencompass.org.cn/leaderboard-multimodal): http://opencompass.openxlab.space/utils/MMLB.json

**Supported Dataset**

| Dataset                                                      | Dataset Names (for run.py)                             | Inference | Evaluation | Results                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------ | --------- | ---------- | ------------------------------------------------------------ |
| [**MMBench Series**](https://github.com/open-compass/mmbench/): <br>MMBench, MMBench-CN, CCBench | MMBench-DEV-[EN/CN]<br>MMBench-TEST-[EN/CN]<br>CCBench | ✅         | ✅          | [**MMBench Series**](https://mmbench.opencompass.org.cn/leaderboard) |
| [**MME**](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Evaluation) | MME                                                    | ✅         | ✅          | [**MME**](results/MME.md)                                    |
| [**SEEDBench_IMG**](https://github.com/AILab-CVC/SEED-Bench) | SEEDBench_IMG                                          | ✅         | ✅          | [**SEEDBench_IMG**](results/SEEDBench_IMG.md)                |
| [**MM-Vet**](https://github.com/yuweihao/MM-Vet)             | MMVet                                                  | ✅         | ✅          | [**MM-Vet**](results/MMVet.md)                               |
| [**MMMU**](https://mmmu-benchmark.github.io)                 | MMMU_DEV_VAL                                           | ✅         | ✅          | [**MMMU**](results/MMMU.md)                                  |
| [**MathVista**](https://mathvista.github.io)                 | MathVista_MINI                                         | ✅         | ✅          | [**MathVista**](/results/MathVista.md)                       |
| [**ScienceQA_IMG**](https://scienceqa.github.io)             | ScienceQA_[VAL/TEST]                                   | ✅         | ✅          | [**ScienceQA**](/results/ScienceQA.md)                       |
| [**COCO Caption**](https://cocodataset.org)                  | COCO_VAL                                               | ✅         | ✅          | [**Caption**](results/Caption.md)                            |
| [**HallusionBench**](https://github.com/tianyi-lab/HallusionBench) | HallusionBench                                         | ✅         | ✅          | [**HallusionBench**](/results/HallusionBench.md)             |
| [**OCRVQA**](https://ocr-vqa.github.io)                      | OCRVQA_[TESTCORE/TEST]                                 | ✅         | ✅          | [**VQA**](/results/VQA.md)                                   |
| [**TextVQA**](https://textvqa.org)                           | TextVQA_VAL                                            | ✅         | ✅          | [**VQA**](/results/VQA.md)                                   |
| [**ChartQA**](https://github.com/vis-nlp/ChartQA)            | ChartQA_VALTEST_HUMAN                                  | ✅         | ✅          | [**VQA**](/results/VQA.md)                                   |
| [**Core-MM**](https://github.com/core-mm/core-mm)            | CORE_MM                                                | ✅         |            |                                                              |

**Supported API Models**

| [**GPT-4-Vision-Preview**](https://platform.openai.com/docs/guides/vision)🎞️🚅 | [**GeminiProVision**](https://platform.openai.com/docs/guides/vision)🎞️🚅 | [**QwenVLPlus**](https://help.aliyun.com/zh/dashscope/developer-reference/vl-plus-quick-start)🎞️🚅 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |

**Supported PyTorch / HF Models**

| [**IDEFICS-[9B/80B]-Instruct**](https://huggingface.co/HuggingFaceM4/idefics-9b-instruct)🎞️🚅 | [**InstructBLIP-[7B/13B]**](https://github.com/salesforce/LAVIS/blob/main/projects/instructblip/README.md) | [**LLaVA-[v1-7B/v1.5-7B/v1.5-13B]**](https://github.com/haotian-liu/LLaVA) | [**MiniGPT-4-[v1-7B/v1-13B/v2-7B]**](https://github.com/Vision-CAIR/MiniGPT-4) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [**mPLUG-Owl2**](https://github.com/X-PLUG/mPLUG-Owl/tree/main/mPLUG-Owl2)🎞️ | [**OpenFlamingo-v2**](https://github.com/mlfoundations/open_flamingo)🎞️ | [**PandaGPT-13B**](https://github.com/yxuansu/PandaGPT)      | [**Qwen-VL**](https://huggingface.co/Qwen/Qwen-VL)🎞️🚅, [**Qwen-VL-Chat**](https://huggingface.co/Qwen/Qwen-VL-Chat)🎞️**🚅** |
| [**VisualGLM-6B**](https://huggingface.co/THUDM/visualglm-6b)🚅 | [**InternLM-XComposer-7B**](https://huggingface.co/internlm/internlm-xcomposer-7b)🚅🎞️ | [**ShareGPT4V-7B**](https://sharegpt4v.github.io)🚅           | [**TransCore-M**](https://github.com/PCIResearch/TransCore-M) |
| [**LLaVA (XTuner)**](https://huggingface.co/xtuner/llava-internlm-7b)🚅 | [**CogVLM-17B-Chat**](https://huggingface.co/THUDM/cogvlm-chat-hf)🚅 | [**SharedCaptioner**](https://huggingface.co/spaces/Lin-Chen/Share-Captioner)🚅 | [**CogVLM-Grounding-Generalist**](https://huggingface.co/THUDM/cogvlm-grounding-generalist-hf)🚅 |
| [**Monkey**](https://github.com/Yuliang-Liu/Monkey)🚅 | | | |

🎞️: Support multiple images as inputs, via the `multi_generate / interleave_generate` interface. 

🚅: Model can be used without any additional configuration / operation. 

```python
# Demo
from vlmeval.config import supported_VLM
model = supported_VLM['idefics_9b_instruct']()
# Forward Single Image
ret = model.generate('assets/apple.jpg', 'What is in this image?')
print(ret)  # The image features a red apple with a leaf on it.
# Forward Multiple Images
ret = model.multi_generate(['assets/apple.jpg', 'assets/apple.jpg'], 'How many apples are there in the provided images? ')
print(ret)  # There are two apples in the provided images.
```

## 🏗️ QuickStart

Before running the evaluation script, you need to **configure** the VLMs and set the model_paths properly. 

After that, you can use a single script `run.py` to inference and evaluate multiple VLMs and benchmarks at a same time. 

### Step0. Installation

```bash
git clone https://github.com/open-compass/VLMEvalKit.git
cd VLMEvalKit
pip install -e .
```

### Step1. Configuration

**VLM Configuration**: All VLMs are configured in `vlmeval/config.py`, for some VLMs, you need to configure the code root (MiniGPT-4, PandaGPT, etc.) or the model_weight root (LLaVA-v1-7B, etc.) before conducting the evaluation. During evaluation, you should use the model name specified in `supported_VLM` in `vlmeval/config.py` to select the VLM. For MiniGPT-4 and InstructBLIP, you also need to modify the config files in `vlmeval/vlm/misc` to configure LLM path and ckpt path.

Following VLMs require the configuration step:

**Code Preparation & Installation**: InstructBLIP ([LAVIS](https://github.com/salesforce/LAVIS)), LLaVA ([LLaVA](https://github.com/haotian-liu/LLaVA)), MiniGPT-4 ([MiniGPT-4](https://github.com/Vision-CAIR/MiniGPT-4)), mPLUG-Owl2 ([mPLUG-Owl2](https://github.com/X-PLUG/mPLUG-Owl/tree/main/mPLUG-Owl2)), OpenFlamingo-v2 ([OpenFlamingo](https://github.com/mlfoundations/open_flamingo)), PandaGPT-13B ([PandaGPT](https://github.com/yxuansu/PandaGPT)), TransCore-M ([TransCore-M](https://github.com/PCIResearch/TransCore-M)). 

**Manual Weight Preparation & Configuration**: InstructBLIP, LLaVA-v1-7B, MiniGPT-4, PandaGPT-13B

### Step2. Evaluation 

We use `run.py` for evaluation. To use the script, you can use `$VLMEvalKit/run.py` or create a soft-link of the script (to use the script anywhere):

**Arguments**

- `--data (list[str])`: Set the dataset names that are supported in VLMEvalKit (defined in `vlmeval/utils/data_util.py`). 
  - including: `MME, SEEDBench_IMG, MMBench_DEV_EN, MMBench_TEST_EN, MMBench_DEV_CN, MMBench_TEST_CN, CCBench, Core_MM, MMVet`
- `--model (list[str])`: Set the VLM names that are supported in VLMEvalKit (defined in `supported_VLM` in `vlmeval/config.py`). 
- `--mode (str, default to 'all', choices are ['all', 'infer'])`: When `mode` set to "all", will perform both inference and evaluation; when set to "infer", will only perform the inference.
- `--nproc (int, default to 4)`: The number of threads for OpenAI API calling.
- `--verbose (bool, store_true)`

**Command**

You can run the script with `python` or `torchrun`:

```bash
# When running with `python`, only one VLM instance is instantiated, and it might use multiple GPUs (depending on its default behavior). 
# That is recommended for evaluating very large VLMs (like IDEFICS-80B-Instruct).

# IDEFICS-80B-Instruct on MMBench_DEV_EN, MME, and SEEDBench_IMG, Inference and Evalution
python run.py --data MMBench_DEV_EN MME SEEDBench_IMG --model idefics_80b_instruct --verbose 
# IDEFICS-80B-Instruct on MMBench_DEV_EN, MME, and SEEDBench_IMG, Inference only
python run.py --data MMBench_DEV_EN MME SEEDBench_IMG --model idefics_80b_instruct --verbose --mode infer

# When running with `torchrun`, one VLM instance is instantiated on each GPU. It can speed up the inference. 
# However, that is only suitable for VLMs that consume small amounts of GPU memory. 

# IDEFICS-9B-Instruct, Qwen-VL-Chat, mPLUG-Owl2 on MMBench_DEV_EN, MME, and SEEDBench_IMG. On a node with 8 GPU. Inference and Evaluation.
torchrun --nproc-per-node=8 run.py --data MMBench_DEV_EN MME SEEDBench_IMG --model idefics_80b_instruct qwen_chat mPLUG-Owl2 --verbose
# Qwen-VL-Chat on MME. On a node with 2 GPU. Inference and Evaluation. 
torchrun --nproc-per-node=2 run.py --data MME --model qwen_chat --verbose
```

The evaluation results will be printed as logs, besides. **Result Files** will also be generated in the directory `$YOUR_WORKING_DIRECTORY/{model_name}`. Files ending with `.csv` contain the evaluated metrics. 

## 🛠️ Custom Benchmark or VLM

To implement a custom benchmark or VLM in VLMEvalKit, please refer to [Custom_Benchmark_and_Model](/Custom_Benchmark_and_Model.md).

## 🎯 The Goal of VLMEvalKit

**The codebase is designed to:**

1. Provide an **easy-to-use**, **opensource evaluation toolkit** to make it convenient for researchers & developers to evaluate existing LVLMs and make evaluation results **easy to reproduce**.
2. Make it easy for VLM developers to evaluate their own models. To evaluate the VLM on multiple supported benchmarks, one just need to **implement a single `generate` function**, all other workloads (data downloading, data preprocessing, prediction inference, metric calculation) are handled by the codebase. 

**The codebase is not designed to:**

1. Reproduce the exact accuracy number reported in the original papers of all **3rd party benchmarks**. The reason can be two-fold:
   1. VLMEvalKit **mainly** uses **generation-based evaluation** for all VLMs (and optionally with **LLM-based answer extraction**). Meanwhile, some benchmarks may use different metrics (SEEDBench uses PPL-based evaluation, *eg.*). For these benchmarks, we will compare both scores in the corresponding README file. We encourage developers to support other different evaluation paradigms in the codebase. 
   2. By default, we use the same prompt template for all VLMs to evaluate on a benchmark. Meanwhile, **some VLMs may have their specific prompt templates** (some may not covered by the codebase at this time). We encourage VLM developers to implement their own prompt template in VLMEvalKit, if that is not covered currently. That will help to improve the reproducibility. 

## 🖊️ Citation

If you use VLMEvalKit in your research or wish to refer to the published OpenSource evaluation results, please use the following BibTeX entry and the BibTex entry corresponding to the specific VLM / benchmark you used.

```bib
@misc{2023opencompass,
    title={OpenCompass: A Universal Evaluation Platform for Foundation Models},
    author={OpenCompass Contributors},
    howpublished = {\url{https://github.com/open-compass/opencompass}},
    year={2023}
}
```

## 💻 Other Projects in OpenCompass

- [opencompass](https://github.com/open-compass/opencompass/): An LLM evaluation platform, supporting a wide range of models (LLaMA, LLaMa2, ChatGLM2, ChatGPT, Claude, etc) over 50+ datasets.
- [MMBench](https://github.com/open-compass/MMBench/): Official Repo of "MMBench: Is Your Multi-modal Model an All-around Player?"
- [BotChat](https://github.com/open-compass/BotChat/): Evaluating LLMs' multi-round chatting capability.
- [LawBench](https://github.com/open-compass/LawBench): Benchmarking Legal Knowledge of Large Language Models. 
