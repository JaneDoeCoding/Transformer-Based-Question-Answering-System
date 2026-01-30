# Transformer-Based-Question-Answering-System
1.Project Overview

This project aims to build a question answering system using Transformer models. The system can:

•	Extract answers from a given text passage (Extractive QA)

•	Generate explanatory responses based on the extracted answers (Generative QA)

The project demonstrates how Transformers handle context understanding, attention mechanisms, information extraction, and text generation. It also includes a fully interactive QA system.

2.Background

Transformer is currently one of the most advanced model architectures in NLP. It can process long texts and capture long-range dependencies.

This project is a hands-on way to learn how Transformers work for both extractive and generative QA tasks, while also exploring fine-tuning, interpretability, and deployment.

3.Project Goals

•	Fine-tune Transformer models for both extractive and generative QA

•	Compare different Transformer models (BERT vs GPT-style) on these tasks

•	Visualize attention to understand how the models work internally

•	Build an interactive demo system (using Gradio)

4.Dataset

SQuAD 2.0 dataset (available from Hugging Face Datasets)

	datasets.load_dataset("squad_v2")


Dataset highlights:

•	Over 100,000 question-answer pairs from Wikipedia

•	Includes unanswerable questions, making it closer to real-world QA scenarios

•	Training set: ~87,000 examples, Validation set: ~11,000 examples

5.Technical Approach

5.1 Data Preparation

•	Load SQuAD 2.0 and explore the dataset:

	Print sample questions, passages, and answers

  Compute the ratio of answerable vs unanswerable questions

 Calculate the average passage length

•	Preprocessing:

	Tokenize questions and passages using Transformer tokenizers (BERT / GPT-2)

	Truncate or pad sequences to handle variable lengths

	Properly mark unanswerable questions

•	Visualization:

	Histogram of passage lengthsand Word cloud of questions


5.2 Extractive QA

•	Fine-tune DistilBERT for extractive question answering

•	Task:

	Predict the start and end positions of answers in passages
  
	Handle unanswerable questions
  
•	Training:

	Use Hugging Face Trainer API
  
	Train for 3–5 epochs
  
	Plot training and validation loss curves

5.3 Response Generation

•	Fine-tune DistilGPT2 for generative QA

•	Data preparation:

      Create prompt-response pairs:
            
      Prompt: question + passage + extracted answer
            
      Response: explanatory text

•	Training:

	Use causal language modeling objective for 3–5 epochs

•	Evaluation:

	Generate 5 sample explanations and analyze them qualitatively (clarity, accuracy)

	Compute perplexity on held-out data


5.4 Advanced Exploration

•	Visualize BERT attention heads (using bertviz or similar libraries)

•	Compare zero-shot vs fine-tuned performance on a subset of the validation set

•	Experiments:

  	LoRA parameter-efficient fine-tuning


5.5 Interactive Demo

•	Build an interactive interface using Gradio

•	Input: passage + question

•	Output: Extracted answer and Generated explanation

•	Provide both a deployable link

6.Technical Guidelines

•	Use Hugging Face Transformers and PyTorch

•	Set a fixed random seed for reproducibility: torch.manual_seed(42)

7.Analysis & Reflection

•	Compare model performance in a table: Perplexity / Eval Loss / Trainable Parameters

•	Discuss Transformer advantages over RNN/CNN: parallelization, long-range dependencies

•	Challenges encountered: handling long passages, unanswerable questions

•	Reflections:

  	Learned practical applications of Transformers
  
  	Gained experience in both extractive and generative tasks
  
  	Developed a deeper understanding of NLP system design
