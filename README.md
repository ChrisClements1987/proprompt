# Agentic Prompt Optimiser

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A simple Python prototype for refining AI prompts using a multi-agent (Creator, Critic, Refiner) pipeline. This app demonstrates how to use multiple AI agents collaboratively to turn a simple idea into a high-quality, robust prompt.

## 🔭 Product Vision

The quality of an AI's output is directly tied to the quality of its prompt. Standard "one-shot" prompting is often a gamble, relying on the user's ability to be an expert prompt engineer.

The vision of this project is to **automate prompt engineering** itself. Instead of a single user-to-AI request, we create a small, autonomous "team" of AI agents that collaborate. By introducing a **Creator**, a **Critic**, and a **Refiner**, we simulate a professional writing and review process. This produces a final prompt that is more specific, less ambiguous, and significantly more likely to generate a high-quality result from the target AI.

This prototype serves as the foundation for more complex, self-optimising AI systems.

## 🤖 How It Works

The application runs a three-step pipeline. The output of one agent becomes the input for the next.

**User Goal 💡 ➔ [Creator Agent] ✍️ ➔ [Critic Agent] 🧐 ➔ [Refiner Agent] 🛠️ ➔ Final Prompt ✨**

1.  **Creator Agent:** Takes the user's basic, high-level goal (e.g., "a logo for my cyber company") and brainstorms a detailed, creative first-draft prompt.
2.  **Critic Agent:** Receives the draft prompt. Its sole job is to be ruthless and find every possible flaw, ambiguity, or missing detail. It produces a bulleted list of critiques. (This prototype is designed to use Anthropic's Claude 3.5 Sonnet for this step, leveraging its strong reasoning).
3.  **Refiner Agent:** Receives both the original `draft_prompt` and the `critique`. Its job is to synthesise both, addressing every point of criticism and rewriting the prompt from scratch to be a perfect, final product.

## 🚀 Getting Started

Follow these instructions to get the project running on your local machine.

### Prerequisites

* Python (3.8 or newer)
* `pip` (Python package installer)
* An **OpenAI** API key
* An **Anthropic** API key

### 1. Installation

First, clone this repository to your local machine:

```bash
git clone [https://github.com/your-username/agentic-prompt-optimiser.git](https://github.com/your-username/agentic-prompt-optimiser.git)
cd agentic-prompt-optimiser
````

Next, it's highly recommended to create a virtual environment to manage dependencies:

```bash
# For Windows
python -m venv venv
.\venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

Now, install the required Python libraries from `requirements.txt`:

```bash
# Make sure you have a requirements.txt file with 'openai' and 'anthropic'
pip install -r requirements.txt
```

### 2\. Configuration

This script relies on environment variables to securely access your API keys. **Do not hardcode your keys in the script.**

Set the variables in your terminal session:

```bash
# For Windows (PowerShell)
$Env:OPENAI_API_KEY = 'sk-your-openai-key-here'
$Env:ANTHROPIC_API_KEY = 'sk-ant-your-anthropic-key-here'

# For Windows (CMD)
set OPENAI_API_KEY=sk-your-openai-key-here
set ANTHROPIC_API_KEY=sk-ant-your-anthropic-key-here

# For macOS/Linux
export OPENAI_API_KEY='sk-your-openai-key-here'
export ANTHROPIC_API_KEY='sk-ant-your-anthropic-key-here'
```

### 3\. Running the App

With your environment set up, you can now run the main script:

```bash
python main.py
```

To change the initial prompt, edit the `user_goal` variable at the bottom of the `main.py` file:

```python
# In main.py
...
# --- Run the prototype ---
user_goal = "I need a prompt for a new logo for my cybersecurity company"
final_result = run_refinement_pipeline(user_goal)
```

## 📁 Repository Structure

The project uses a minimal and standard structure for a small Python application.

```
.
├── .gitignore         # Tells Git which files to ignore
├── main.py            # The main application script
├── requirements.txt   # Lists Python dependencies (openai, anthropic)
└── README.md          # This file
```

## 🌿 Version Control

This project uses a basic Git workflow:

  * The `main` branch is the primary, stable branch.
  * All development, new features, or bug fixes should be done on separate **feature branches** (e.g., `feat/add-groq-api`).
  * Once a feature is complete, submit a **Pull Request** to merge it into `main`.

## 🤝 Contributing

Contributions are welcome\! This is a prototype, so there are many ways to improve it.

Please follow these steps to contribute:

1.  **Fork** the repository to your own GitHub account.
2.  **Clone** your fork to your local machine.
3.  Create a new **feature branch**: `git checkout -b feat/your-new-feature`
4.  Make your changes and **commit** them with clear messages.
5.  **Push** your branch to your fork: `git push origin feat/your-new-feature`
6.  Open a **Pull Request** from your branch to this repository's `main` branch.

If you find a bug or have an idea, please [open an issue](https://www.google.com/search?q=https://github.com/your-username/agentic-prompt-optimiser/issues) first to discuss it.

## 📄 Licensing

This project is licensed under the MIT License. This is a permissive license that allows for wide reuse. See the `LICENSE.txt` file (you will need to create this file) for full details.

```