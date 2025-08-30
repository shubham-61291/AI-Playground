Chatbot – BlenderBot 400M
Overview

This project demonstrates a simple AI chatbot built using Hugging Face’s facebook/blenderbot-400M-distill model and a Gradio interface.
It is part of the AI-Playground repository, which collects practical implementations of AI applications.

Key Features

Pretrained BlenderBot-400M Distill model from Hugging Face.

Interactive web-based interface using Gradio.

Generates responses using:

Top-k sampling

Top-p (nucleus) sampling

Repetition penalty

Lightweight and suitable for demos.

Performance

Responds to general knowledge and casual conversation queries.

Generates up to 50 new tokens per reply.

Provides human-readable outputs without special tokens.

Technical Details

Frameworks: PyTorch, Hugging Face Transformers, Gradio

Model: facebook/blenderbot-400M-distill

Interface: Gradio Web App

Hardware:

Runs on CPU (demo speed).

Faster responses with GPU.

Usage
Installation
pip install -r requirements.txt

Running the Chatbot
python basic_ai_using_huggingface.py


Gradio will generate a local and shareable link in the terminal.
Open it in your browser and start chatting 🚀

Requirements

Python 3.7+

Transformers 4.30.2

Torch

Gradio

Demo
## Demo  
![Chatbot Demo](basic_AI_using_huggingface_image.png)


Future Enhancements

Add persistent chat history in UI.

Deploy on Hugging Face Spaces.

Explore larger models (GPT-2, T5, etc.).

Author

Shubham Singh

License

MIT License
