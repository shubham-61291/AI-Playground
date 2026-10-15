# AI-Playground

A curated collection of five practical AI applications spanning document-grounded question answering, conversational NLP, vision-language captioning, speech recognition, and a voice-assistant workflow.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

The repository is organized as independent demonstrations rather than a single integrated product. Each project has its own source files, dependency manifest, documentation, and local MIT license. Some Python files are exports from Google Colab notebooks and currently contain notebook-only syntax; read the individual project instructions before attempting local execution.

## Project index

| Project | Capability | Main implementation | Dependencies | Notes |
|---|---|---|---|---|
| [Supernova Financial RAG Agent](Supernova%20Financial%20RAG%20Agent/README.md) | PDF-grounded question answering | `rag_agent.py` | [requirements.txt](Supernova%20Financial%20RAG%20Agent/requirements.txt) | Colab-exported script; demo code does not implement automated evaluation metrics. |
| [BlenderBot 400M Chatbot](chatbot-blenderbot-400M/README.md) | Text conversation | `basic_ai_using_huggingface.py` | [requirements.txt](chatbot-blenderbot-400M/requirements.txt) | Global history is recorded but not supplied back to the model as conversation context. |
| [BLIP Image Captioning](image-captioning-blip/README.md) | Image captioning and URL image gallery | `image_captioning_using_huggingface.py` | [requirements.txt](image-captioning-blip/requirements.txt) | Colab-specific upload/magic lines and multiple sequential demos need refactoring for local execution. |
| [Whisper Meeting Transcriber](meeting-transcriber-whisper/README.md) | Audio-to-text transcription | `gradiobasedmeetingtranscriber.py` | [requirements.txt](meeting-transcriber-whisper/requirements.txt) | Returns transcript text only; model timestamps are not surfaced in the UI. |
| [Watsonx Voice Assistant](voice-assistant-watsonx/README.md) | Speech-to-text, LLM response, text-to-speech | `server.py`, `worker.py` | [requirements.txt](voice-assistant-watsonx/requirements.txt) | The tracked tree lacks `templates/index.html`; the home page is incomplete until that template is supplied. |

## Demos

The following video links are listed in the existing repository documentation:

- [BlenderBot chatbot demo](https://www.youtube.com/watch?v=3bno8Z1ad38&list=PLlRRgrbOaGcYU__fUcQFO1bBILOkAhCZE)
- [BLIP image captioning demo](https://www.youtube.com/watch?v=VHFnyVZX7z4&list=PLlRRgrbOaGcYU__fUcQFO1bBILOkAhCZE&index=2)
- [Whisper meeting transcription demo](https://www.youtube.com/watch?v=sdGgobRCUFw&list=PLlRRgrbOaGcYU__fUcQFO1bBILOkAhCZE&index=3)
- [Supernova Financial RAG demo](https://www.youtube.com/watch?v=Ms8OtgUXTDA&list=PLlRRgrbOaGcYU__fUcQFO1bBILOkAhCZE&index=4)
- [Watsonx voice assistant demo](https://www.youtube.com/watch?v=-BZwDb9a9pk&list=PLlRRgrbOaGcYU__fUcQFO1bBILOkAhCZE&index=5)

These links are references from the repository README; this documentation refresh does not independently verify that the videos remain publicly available or match the current source.

## Repository-wide setup

Use Python in an isolated virtual environment and install the requirements from the individual project directory. Model weights may be downloaded from Hugging Face at runtime, and speech services/OpenAI API access may require network access and credentials. Installations should be isolated because dependencies are not version-aligned across all five projects.

```bash
git clone https://github.com/shubham-61291/AI-Playground.git
cd AI-Playground
```

Then follow the specific project README. Do not assume that `pip install` at the root will install every project's dependencies; no root `requirements.txt` is present.

## Security, privacy, and reliability notes

- **Credentials:** never hard-code Hugging Face or OpenAI tokens into source files. Use environment variables or a secret manager and keep secrets out of Git.
- **Public interfaces:** Gradio projects using `share=True` can create publicly reachable links. Do not submit confidential documents, audio, or images to a shared demo unless you understand where data goes.
- **Remote URL ingestion:** the BLIP URL-gallery demo downloads content from a user-supplied webpage. It is a demonstration, not a hardened URL-fetching service; validate destinations and apply network, MIME-type, and size restrictions before production use.
- **Voice service:** the Flask app enables permissive CORS, exposes routes without authentication, binds to `0.0.0.0`, and calls external APIs. Do not expose it directly to an untrusted network as configured.
- **Financial answers:** the RAG demo is not a financial, legal, accounting, or compliance authority. Retrieval does not guarantee completeness, grounding, or correctness.
- **Evaluation claims:** saved screenshots are evidence assets, not proof that a benchmark is reproducible. Use the individual README's verification notes.

## Author and license

Authorship in the individual project READMEs is attributed to Shubham Singh. The repository documentation/license package standardizes copyright attribution to **Shubham Kumar Singh** for this refresh.

## License

Licensed under the MIT License. The complete license text is also available in [`./LICENSE`](./LICENSE).

```text
MIT License

Copyright (c) 2026 Shubham Kumar Singh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
