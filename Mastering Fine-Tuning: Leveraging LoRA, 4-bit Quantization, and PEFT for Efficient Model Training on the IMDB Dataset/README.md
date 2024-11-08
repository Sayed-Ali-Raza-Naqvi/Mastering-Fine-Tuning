# Mastering Fine-Tuning: Leveraging LoRA, 4-bit Quantization, and PEFT for Efficient Model Training on the IMDB Dataset

## Overview
This project demonstrates how to fine-tune a pre-trained language model using advanced techniques like Low-Rank Adaptation (LoRA), 4-bit quantization, and Parameter-Efficient Fine-Tuning (PEFT) to efficiently train on the IMDB movie reviews dataset. By utilizing these techniques, we achieve efficient fine-tuning with reduced computational resources, enabling effective model adaptation even on limited hardware setups.

## Project Highlights
### 1. Pre-trained Model Utilized
- The script uses the pre-trained model unsloth/mistral-7b-bnb-4bit from the unsloth library.
- The model is loaded in 4-bit precision, which significantly reduces memory usage while maintaining performance.

### 2. Dataset
- The IMDB dataset is used, focusing on its train split for fine-tuning.
- The dataset contains thousands of movie reviews, useful for sentiment analysis tasks.

### 3. Techniques Used
- LoRA (Low-Rank Adaptation): Fine-tunes the model by injecting small, trainable matrices into specific layers, reducing the number of trainable parameters.
- 4-bit Quantization: Reduces model size, leading to faster inference and lower VRAM usage.
- PEFT (Parameter-Efficient Fine-Tuning): Allows efficient adaptation of large language models by fine-tuning only a subset of parameters.

### 4. Training Configuration
- Utilizes the SFTTrainer from the trl library for supervised fine-tuning.
- Mixed precision training is enabled (FP16/BF16) for efficient computation.
- Fine-tuning is done using a limited number of training steps with gradient accumulation to simulate larger batch sizes.

### 5. Inference and Model Saving
- The fine-tuned model is evaluated on a sample review to generate predictions.
- The final model is saved locally for future use and can be optionally uploaded to the Hugging Face Hub.
