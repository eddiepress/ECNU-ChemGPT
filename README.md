# ECNU-ChemGP

<div align="center">

![ChemGPT Logo](https://img.shields.io/badge/ChemGPT-Open%20Source-blue.svg)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow.svg)](https://huggingface.co/ALmonster)

**An Open-Source Chemistry-Focused Language Model Suite**

[🤗 ChemGPT2-QA-72B](https://huggingface.co/ALmonster/ChemGPT2-QA-72B) • [🧠 Braingpt1-Chem](https://huggingface.co/ALmonster/Braingpt1-Chem) • [📖 Documentation](#documentation)

</div>

## 🚀 Overview

ECNU-ChemGPT is a comprehensive open-source project that provides state-of-the-art language models and tools specifically designed for chemistry applications. Our suite includes three main components: **ChemGPT-QA**, **ChemGPT-web**, and **ChemGPT-retro**, each targeting different aspects of chemical research and applications.

## 📦 Project Components

### 🎯 ChemGPT-QA
**Training and Inference Framework**

Contains the complete codebase for training and inference operations of our chemistry-focused language models. This component includes:
- Model training scripts and configurations
- Inference engines for chemistry Q&A tasks
- Evaluation benchmarks and metrics
- Data preprocessing pipelines

**Model:** [ChemGPT2-QA-72B](https://huggingface.co/ALmonster/ChemGPT2-QA-72B) - Fine-tuned on Qwen2-72B-Instruct

### 🌐 ChemGPT-web
**Integrated Web Platform**

A comprehensive web application that leverages Braingpt to integrate multiple chemistry tools and functionalities:
- Interactive web interface for chemistry queries
- Multi-tool integration powered by Braingpt
- User-friendly dashboard for chemical analysis
- API endpoints for external integrations

**Model:** [Braingpt1-Chem](https://huggingface.co/ALmonster/Braingpt1-Chem) - Specialized brain-inspired architecture

### ⚗️ ChemGPT-retro
**Chemical Retrosynthesis**

Specialized codebase focused on chemical retrosynthesis prediction and analysis:
- Retrosynthetic pathway prediction algorithms
- Synthetic route optimization
- Chemical reaction mechanism analysis
- Integration with chemical databases

## 🏆 Performance

Our ChemGPT2-QA-72B model demonstrates exceptional performance on chemistry evaluation benchmarks:

| Model | College Chemistry | High School Chemistry | Middle School Chemistry | Average |
|-------|------------------|---------------------|------------------------|---------|
| GPT-3.5 | 39.7% | 52.9% | 71.4% | 54.7% |
| GPT-4 | 59.4% | 55.8% | 81.1% | 65.4% |
| **ChemGPT2-QA-72B** | **71.0%** | **93.6%** | **99.5%** | **88.0%** |

## 🛠️ Quick Start

### Installation

```bash
git clone https://github.com/your-org/ECNU-ChemGPT.git
cd ECNU-ChemGPT
pip install -r requirements.txt
```

### Using ChemGPT-QA

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

# Load the model
model = AutoModelForCausalLM.from_pretrained(
    "ALmonster/ChemGPT2-QA-72B",
    torch_dtype="auto",
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained("ALmonster/ChemGPT2-QA-72B")

# Ask a chemistry question
prompt = "Explain the mechanism of nucleophilic substitution reactions."
messages = [
    {"role": "system", "content": "You are a helpful chemistry assistant."},
    {"role": "user", "content": prompt}
]

text = tokenizer.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
model_inputs = tokenizer([text], return_tensors="pt")
generated_ids = model.generate(model_inputs.input_ids, max_new_tokens=512)
response = tokenizer.batch_decode(generated_ids, skip_special_tokens=True)[0]
print(response)
```

## 🔗 Model Weights

| Component | Model | Hugging Face Link |
|-----------|-------|------------------|
| ChemGPT-QA | ChemGPT2-QA-72B | [🤗 ALmonster/ChemGPT2-QA-72B](https://huggingface.co/ALmonster/ChemGPT2-QA-72B) |
| ChemGPT-web | Braingpt1-Chem | [🤗 ALmonster/Braingpt1-Chem](https://huggingface.co/ALmonster/Braingpt1-Chem) |
| ChemGPT-Retro | ChemGPT2-RETRO-770M | [🤗 jerryfusion/ChemGPT2-RETRO-770M](https://huggingface.co/jerryfusion/ChemGPT2-RETRO-770M) |


## 📚 Documentation

- [Installation Guide](docs/installation.md)
- [Training Tutorial](docs/training.md)
- [API Reference](docs/api.md)
- [Examples](examples/)

## 🤝 Contributing

We welcome contributions from the community! Please check our [Contributing Guidelines](CONTRIBUTING.md) for more information.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built upon the excellent work of [Qwen2](https://github.com/QwenLM/Qwen2)
- Thanks to the open-source community for continuous support
- Special thanks to all contributors and collaborators

## 📞 Contact

- **Project Lead:** [Your Name]
- **Email:** [your.email@university.edu]
- **Institution:** East China Normal University (ECNU)

---

<div align="center">

**⭐ If you find this project helpful, please consider giving it a star! ⭐**

</div>
