# 🚗 LoRA Driving Instructor

A lightweight, instruction-following language model fine-tuned with LoRA to simulate driving-related natural language behavior — inspired by self-driving systems like Tesla Autopilot. This project fine-tunes DistilGPT2 on a set of navigation-style commands using HuggingFace Transformers and PEFT for efficient, low-resource adaptation.

---

## ✨ Project Highlights

- 🧠 Fine-tuned `DistilGPT2` using **LoRA (Low-Rank Adaptation)** to follow navigation-style instructions
- 💡 Trained on real-world driving prompts (e.g. “Turn left at the light”) using Talk2Car-inspired dataset
- ⚙️ Efficient training with only ~1% of model parameters updated using HuggingFace PEFT
- ⚡ Designed to run in Google Colab or low-end local machines (RAM < 16 GB)
- 📤 Produces structured, context-aware output for planning agents

---

## 📦 Input & Output Examples

**Prompt:**

```
Turn left after the red light and park near the blue building.
```

**Generated Response:**

```
Executing: Turn left after the red light and park near the blue building.
```

---

## 🧠 Model Overview

This project uses:
- `DistilGPT2`: A distilled version of GPT2 with 6 layers (~82M params)
- `LoRA`: Low-rank matrix adapters applied to query/value weights
- `PEFT`: HuggingFace library that injects trainable modules into transformer layers

Training is performed only on the LoRA parameters, making the model faster, lighter, and easier to deploy than traditional full fine-tuning.

---

## 🗂 Project Structure

```
lora-driving-instructor/
├── Dataset/
│   └── train_commands.json         # Talk2Car-style commands
├── LoRA_Driving_Instructor.py      # Main training script
├── README.md                       # Project overview
└── .gitignore
```

---

## 🛠 Tech Stack

| Tool           | Purpose                              |
|----------------|--------------------------------------|
| PyTorch        | Model backend                        |
| HuggingFace    | Transformers, tokenizers, PEFT       |
| PEFT           | Parameter-Efficient Fine-Tuning (LoRA) |
| Datasets       | HuggingFace Dataset loading + split  |
| Colab / macOS  | Training environment                 |

---

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone git@github.com:Hitha99/lora-driving-instructor.git
cd lora-driving-instructor
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install torch transformers peft accelerate datasets bitsandbytes
```

### 3. Train the model (LoRA fine-tuning)

```bash
python LoRA_Driving_Instructor.py
```

### 4. Generate output

```bash
python generate.py
```

---

## 🧪 Sample Results

| Prompt                                       | Model Output                                             |
|---------------------------------------------|----------------------------------------------------------|
| Turn left after the red light               | Executing: Turn left after the red light                 |
| Merge onto the highway and keep right       | Executing: Merge onto the highway and keep right         |
| Stop at the crosswalk and wait for the bus  | Executing: Stop at the crosswalk and wait for the bus    |

---

## 📘 Related Research & Tools

- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)
- [HuggingFace PEFT Library](https://github.com/huggingface/peft)
- [Talk2Car Dataset](https://github.com/Talk2Car/Talk2Car)
- [Tesla AI Day (YouTube)](https://www.youtube.com/watch?v=j0z4FweCy4M)

---

## 👩‍💻 Author

**Hitha Magadi Vijayanand**  
Graduate Student, Computer Science – Texas A&M University  
🔗 [GitHub](https://github.com/Hitha99)  
🔗 [LinkedIn](https://www.linkedin.com/in/hitha-magadi-vijayanand-68143b1b5/)
