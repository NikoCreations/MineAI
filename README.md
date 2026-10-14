# MineAI

**A lightweight, client-side AI assistant for Minecraft Java Edition, powered by Ollama.**

MineAI brings local AI directly into Minecraft, allowing you to ask questions and receive AI-generated answers through the in-game chat. Choose from your installed Ollama models and interact with your preferred model without leaving the game.

Designed to work client-side, MineAI does not require installation on the Minecraft server, making it compatible with vanilla multiplayer servers.

## Features

- **In-game AI chat** — Ask questions directly from Minecraft using `/ai <question>`.
- **Local model support** — Connect to Ollama and use models installed on your machine.
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

1. Install Ollama and start it on your computer.
2. Download a compatible model, for example:

   ```bash
   ollama pull gemma3:1b
   ```

3. Install MineAI in your Fabric Minecraft instance.
4. Launch Minecraft and run:

   ```text
   /ai list
   ```

5. Select a model:

   ```text
   /ai select gemma3:1b
   ```

6. Start asking questions:

   ```text
   /ai How do I find diamonds efficiently?
   ```

## Local AI

MineAI sends prompts to your local Ollama instance at `http://localhost:11434`. Model inference runs through Ollama on your computer, so performance depends on your hardware and the model you choose.

MineAI does not automatically provide internet access or real-time information. The accuracy and quality of responses depend on the selected model.

## Project Status

MineAI is a work in progress. Features, compatibility, and performance may change as development continues.

## License

MineAI is **All Rights Reserved (ARR)**. All rights are reserved by the copyright holder. No permission is granted to copy, modify, redistribute, or reuse this project without explicit authorization, except where permitted by applicable law.
