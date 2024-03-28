<p align="left">
    <a href="README.md">中文</a>&nbsp ｜ &nbsp<a>English&nbsp </a>
</p>

# <p align="center">Codefuse-ChatBot: Development by Private Knowledge Augmentation</p>

<p align="center">
    <a href="README.md"><img src="https://img.shields.io/badge/文档-中文版-yellow.svg" alt="ZH doc"></a>
    <a href="README_EN.md"><img src="https://img.shields.io/badge/document-英文版-yellow.svg" alt="EN doc"></a>
    <img src="https://img.shields.io/github/license/codefuse-ai/codefuse-chatbot" alt="License">
    <a href="https://github.com/codefuse-ai/codefuse-chatbot/issues">
      <img alt="Open Issues" src="https://img.shields.io/github/issues-raw/codefuse-ai/codefuse-chatbot" />
    </a>
    <br><br>
</p>
This project is an open-source AI intelligent assistant, specifically designed for the entire lifecycle of software development, covering design, coding, testing, deployment, and operations. Through knowledge retrieval, tool utilization, and sandbox execution, Codefuse-ChatBot can not only answer professional questions you encounter during the development process but also coordinate multiple independent, dispersed platforms through a conversational interface.


## 🔔 Updates
- [2024.01.29] A configurational multi-agent framework, CoAgent, has been open-sourced. For more details, please refer to [coagent](sources/readme_docs/coagent/coagent-en.md)
- [2023.12.26] Opening the capability to integrate with open-source private large models and large model interfaces based on FastChat
- [2023.12.01] Release of Multi-Agent and codebase retrieval functionalities.
- [2023.11.15] Addition of Q&A enhancement mode based on the local codebase.
- [2023.09.15] Launch of sandbox functionality for local/isolated environments, enabling knowledge retrieval from specified URLs using web crawlers.

## 📜 Contents
- [🤝 Introduction](#-introduction)
- [🧭 Technical Route](#-technical-route)
- [🌐 Model Integration](#-model-integration)
- [🚀 Quick Start](#-quick-start)
- [🤗 Acknowledgements](#-acknowledgements)

## 🤝 Introduction

💡 The aim of this project is to construct an AI intelligent assistant for the entire lifecycle of software development, covering design, coding, testing, deployment, and operations, through Retrieval Augmented Generation (RAG), Tool Learning, and sandbox environments. It transitions gradually from the traditional development and operations mode of querying information from various sources and operating on standalone, disparate platforms to an intelligent development and operations mode based on large-model Q&A, changing people's development and operations habits.

- **🧠 Intelligent Scheduling Core:** Constructed a well-integrated scheduling core system that supports multi-mode one-click configuration, simplifying the operational process. [coagent](sources/readme_docs/coagent/coagent-en.md)
- **💻 Comprehensive Code Repository Analysis:** Achieved in-depth understanding at the repository level and coding and generation at the project file level, enhancing development efficiency.
- **📄 Enhanced Document Analysis:** Integrated document knowledge bases with knowledge graphs, providing deeper support for document analysis through enhanced retrieval and reasoning.
- **🔧 Industry-Specific Knowledge:** Tailored a specialized knowledge base for the DevOps domain, supporting the self-service one-click construction of industry-specific knowledge bases for convenience and practicality.
- **🤖 Compatible Models for Specific Verticals:** Designed small models specifically for the DevOps field, ensuring compatibility with related DevOps platforms and promoting the integration of the technological ecosystem.

🌍 Relying on open-source LLM and Embedding models, this project can achieve offline private deployments based on open-source models. Additionally, this project also supports the use of the OpenAI API.[Access Demo](sources/readme_docs/fastchat-en.md)

👥 The core development team has been long-term focused on research in the AIOps + NLP domain. We initiated the CodefuseGPT project, hoping that everyone could contribute high-quality development and operations documents widely, jointly perfecting this solution to achieve the goal of "Making Development Seamless for Everyone."


<div align=center>
  <img src="sources/docs_imgs/objective_v4.png" alt="Image" width="600" height="333">
</div>

🌍 Relying on open-source LLM and Embedding models, this project can achieve offline private deployments based on open-source models. Additionally, this project also supports the use of the OpenAI API.

👥 The core development team has been long-term focused on research in the AIOps + NLP domain. We initiated the DevOpsGPT project, hoping that everyone could contribute high-quality development and operations documents widely, jointly perfecting this solution to achieve the goal of "Making Development Seamless for Everyone."

## 🧭 Technical Route
<div align=center>
  <img src="sources/docs_imgs/devops-chatbot-module-v2.png" alt="Image" width="600" height="503">
</div>

- 🧠 **Multi-Agent Schedule Core:** Easily configurable to create interactive intelligent agents.
- 🕷️ **Multi Source Web Crawl:** Offers the capability to crawl specified URLs for collecting the required information.
- 🗂️ **Data Processor:** Effortlessly handles document loading, data cleansing, and text segmentation, integrating data from different sources.
- 🔤 **Text Embedding & Index:**：Users can easily upload files for document retrieval, optimizing the document analysis process.
- 🗄️ **Vector Database & Graph Database:** Provides flexible and powerful data management solutions.
- 📝 **Prompt Control & Management:**：Precisely defines the contextual environment for intelligent agents.
- 🚧 **SandBox:**：Safely executes code compilation and actions.
- 💬 **LLM:**：Supports various open-source models and LLM interfaces.
- 🛠️ **API Management:：** Enables rapid integration of open-source components and operational platforms.

For implementation details, see: [Technical Route Details](sources/readme_docs/roadmap-en.md)


## 🌐 Model Integration

If you need to integrate a specific model, please inform us of your requirements by submitting an issue.

|      model_name    | model_size | gpu_memory | quantize | HFhub | ModelScope |
| ------------------ | ---------- | ---------- | -------- | ----- | ---------- |
|        chatgpt     |    -       |    -       |     -    | -     | -          |
| codellama-34b-int4 |     34b    |    20g     |    int4  | coming soon| [link](https://modelscope.cn/models/codefuse-ai/CodeFuse-CodeLlama-34B-4bits/summary) |



## 🚀 Quick Start
### coagent-py
More Detail see：[coagent](sources/readme_docs/coagent/coagent-en.md)
```
pip install coagent
```

### ChatBot-UI
Please install the Nvidia driver yourself; this project has been tested on Python 3.9.18, CUDA 11.7, Windows, and X86 architecture macOS systems.

1. Preparation of Python environment

- It is recommended to use conda to manage the python environment (optional)
```bash
# Prepare conda environment
conda create --name Codefusegpt python=3.9
conda activate Codefusegpt
```

- Install related dependencies
```bash
cd Codefuse-ChatBot
# python=3.9，use notebook-latest，python=3.8 use notebook==6.5.5
pip install -r requirements.txt
```

2. Preparation of Sandbox Environment
- Windows Docker installation:
[Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows-install/) supports 64-bit versions of Windows 10 Pro, with Hyper-V enabled (not required for versions v1903 and above), or 64-bit versions of Windows 10 Home v1903 and above.
  
  - [Comprehensive Detailed Windows 10 Docker Installation Tutorial](https://zhuanlan.zhihu.com/p/441965046)
  - [Docker: From Beginner to Practitioner](https://yeasy.gitbook.io/docker_practice/install/windows)
  - [Handling Docker Desktop requires the Server service to be enabled](https://blog.csdn.net/sunhy_csdn/article/details/106526991)
  - [Install wsl or wait for error prompt](https://learn.microsoft.com/en-us/windows/wsl/install)

- Linux Docker Installation:
Linux installation is relatively simple, please search Baidu/Google for installation instructions.

- Mac Docker Installation
  - [Docker: From Beginner to Practitioner](https://yeasy.gitbook.io/docker_practice/install/mac)

```bash
# Build images for the sandbox environment, see above for notebook version issues
bash docker_build.sh
```

3. Model Download (Optional)

If you need to use open-source LLM and Embed

ding models, you can download them from HuggingFace.
Here, we use THUDM/chatglm2-6b and text2vec-base-chinese as examples:

```
# install git-lfs
git lfs install

# install LLM-model
git lfs clone https://huggingface.co/THUDM/chatglm2-6b

# install Embedding-model
git lfs clone https://huggingface.co/shibing624/text2vec-base-chinese
```


4. Start the Service
```bash
# After configuring server_config.py, you can start with just one click.
cd examples
bash start.sh
# you can config your llm model and embedding model
```
<div align=center>
  <img src="sources/docs_imgs/webui_config.png" alt="图片">
</div>

Or `python start.py` by [old version to start](sources/readme_docs/start-en.md)
More details about accessing LLM Moldes[More Details...](sources/readme_docs/fastchat.md)
<br>

## Contribution
Thank you for your interest in the Codefuse project. We warmly welcome any suggestions, opinions (including criticisms), comments, and contributions to the Codefuse project.

Your suggestions, opinions, and comments on Codefuse can be directly submitted through GitHub Issues.

There are many ways to participate in the Codefuse project and contribute to it: code implementation, test writing, process tool improvement, documentation enhancement, and more. We welcome any contributions and will add you to our list of contributors. See [contribution guide](sources/readme_docs/contribution/contribute_guide_en.md)

## 🤗 Acknowledgements

This project is based on [langchain-chatchat](https://github.com/chatchat-space/Langchain-Chatchat) and [codebox-api](https://github.com/shroominic/codebox-api). We deeply appreciate their contributions to open source!