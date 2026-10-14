# MineAI

**A lightweight, client-side AI assistant for Minecraft Java Edition, powered by Ollama.**

MineAI brings local AI directly into Minecraft, allowing you to ask questions and receive AI-generated answers through the in-game chat. Choose from your installed Ollama models and interact with your preferred model without leaving the game.

You can also download the **custom MineAI AI model directly from this page**, configured specifically for MineAI. Alternatively, you can use any compatible model installed in Ollama.

Designed to work client-side, MineAI does not require installation on the Minecraft server, making it compatible with vanilla multiplayer servers.

## Features

- **In-game AI chat** — Ask questions directly from Minecraft using `/ai <question>`.
- **Local model support** — Connect to Ollama and use models installed on your machine.
- **Custom MineAI model** — Download the dedicated MineAI model from this page for a model configuration tailored to the project.
- **Model management** — List available models, view their sizes and details, select models, and unload them from memory.
- **Command autocomplete** — Get suggestions for installed model names when selecting a model.
- **Clear chat feedback** — Receive color-coded status messages, progress updates, and error notifications.
- **Client-side design** — No server-side installation required.

## Commands

| Command | Description |
|---|---|
| `/ai <question>` | Ask the selected AI model a question. |
| `/ai list` | List installed Ollama models and their details. |
| `/ai select <model>` | Load and select a model. |
| `/ai status` | Display the currently selected model. |
| `/ai unload` | Unload the selected model from memory. |

## Requirements

- Minecraft Java Edition
- Fabric Loader
- Fabric API
- [Ollama](https://ollama.com/)
- At least one compatible model installed in Ollama

## Getting Started

### 1. Install Ollama

Download and install Ollama from the [official website](https://ollama.com/), then start it on your computer.

### 2. Download an AI Model

You have two options:

**Option A — Use the custom MineAI model**

Download the custom MineAI model provided on this page, in the section where the model description and download are available. Follow the accompanying instructions to install and run it through Ollama.

**Option B — Use another compatible model**

For example, download Gemma 3 1B by running:

```bash
ollama pull gemma3:1b
```

### 3. Install MineAI

Install MineAI in your Fabric Minecraft instance, along with its required dependencies.

### 4. List Available Models

Launch Minecraft and run:

```text
/ai list
```

### 5. Select a Model

Select the custom MineAI model or another installed model by using its exact Ollama model name:

```text
/ai select gemma3:1b
```

Replace `gemma3:1b` with the name of your chosen model.

### 6. Start Asking Questions

Open the Minecraft chat and enter a question:

```text
/ai How do I find diamonds efficiently?
```

MineAI will send your question to the selected model and display its response in the game chat.

## Local AI

MineAI communicates with your local Ollama instance at `http://localhost:11434`. Model inference runs through Ollama on your computer, so performance depends on your hardware and the model you choose.

The custom MineAI model is configured for use with the project, but its capabilities and response quality still depend on the underlying language model.

MineAI does not automatically provide Internet access or real-time information. The accuracy and quality of responses depend on the selected model, and current information requires an actual search or external data integration.
