# MineAI Custom Model — Installation Guide

This guide explains how to install the custom MineAI model using Ollama on **Windows, macOS, and Linux**.

The custom model is created locally from a `Modelfile`. You do not need to download a separate model weights file if you follow this guide: Ollama downloads the required base model and applies the MineAI configuration.

## Requirements

- [Ollama](https://ollama.com/download)
- A compatible base model specified in the `Modelfile`
- Enough disk space and memory for the model
- An Internet connection for the initial download
- Minecraft Java Edition with Fabric and MineAI installed, if you intend to use the model in-game

## 1. Download the MineAI Modelfile

Download the `Modelfile` provided with the MineAI custom model.

Create a folder named `MineAI-Model` on your computer and place the file inside it.

**Important:** The file must be named exactly `Modelfile`, with no file extension such as `.txt`.

Check the `FROM` instruction inside the file to identify the required base model. The commands below use `gemma3:1b` as an example. If your `Modelfile` specifies a different model, replace `gemma3:1b` with that model's exact name.

## 2. Install Ollama

Download Ollama for your operating system from the official website:

https://ollama.com/download

### Windows

1. Download the Windows installer from the Ollama website.
2. Run the installer and follow the installation instructions.
3. Open **PowerShell** or **Windows Terminal**.
4. Verify that Ollama is installed:

```powershell
ollama --version
```

If the command is not recognized, finish the installation and reopen the terminal.

### macOS

1. Download Ollama for macOS from the official website.
2. Install and open the application.
3. Open Terminal.
4. Verify the installation:

```bash
ollama --version
```

### Linux

Install Ollama using the official installation instructions:

https://ollama.com/download/linux

Then open a terminal and verify the installation:

```bash
ollama --version
```

If necessary, start the Ollama service according to the instructions for your Linux distribution. On systems using systemd, you can check it with:

```bash
systemctl status ollama
```

If Ollama is installed as a system service and is stopped, start it with:

```bash
sudo systemctl start ollama
```

## 3. Open the Model Folder

Open a terminal in the folder containing your `Modelfile`.

### Windows — PowerShell

If you created the folder on your Desktop:

```powershell
cd "$HOME\Desktop\MineAI-Model"
```

### macOS

If you created the folder on your Desktop:

```bash
cd ~/Desktop/MineAI-Model
```

### Linux

If you created the folder in your home directory:

```bash
cd ~/MineAI-Model
```

Adjust the path if you saved the folder somewhere else.

Make sure the `Modelfile` is present in the current directory before continuing.

## 4. Download the Base Model

The `FROM` instruction in the `Modelfile` identifies the base model required by MineAI.

For example, if the file contains:

```text
FROM gemma3:1b
```

download that model by running the following command.

**Windows, macOS, and Linux:**

```bash
ollama pull gemma3:1b
```

Wait for the download to complete.

If the `FROM` instruction references another model, download that model instead.

## 5. Create the Custom MineAI Model

Run the following command from the directory containing the `Modelfile`.

**Windows — PowerShell:**

```powershell
ollama create mineai-gemma -f .\Modelfile
```

**macOS and Linux:**

```bash
ollama create mineai-gemma -f ./Modelfile
```

Wait for Ollama to finish creating the model.

The model will be registered locally under the name `mineai-gemma`.

## 6. Verify the Installation

On all three operating systems, run:

```bash
ollama list
```

You should see `mineai-gemma` in the list of installed models.

To test it directly, run:

```bash
ollama run mineai-gemma
```

Enter a question and check whether the model responds.

To exit the interactive session, type:

```text
/bye
```

## 7. Use MineAI in Minecraft

Make sure Ollama is running, then launch Minecraft with Fabric and MineAI installed.

Open the Minecraft chat and list the available models:

```text
/ai list
```

Select the custom MineAI model:

```text
/ai select mineai-gemma
```

Ask a question:

```text
/ai How do I find diamonds efficiently?
```

MineAI should send your prompt to your local Ollama instance and display the generated answer in Minecraft chat.

## Troubleshooting

### The `ollama` Command Is Not Recognized

- **Windows:** Finish installing Ollama and reopen PowerShell or Windows Terminal.
- **macOS:** Make sure Ollama is installed and its command-line tools are available in your shell.
- **Linux:** Follow the official installation instructions and verify that the Ollama executable is available.

### The Modelfile Cannot Be Found

Make sure the terminal is in the directory containing the file and that the filename is exactly `Modelfile`, without a `.txt` extension.

### The Base Model Is Missing

Check the `FROM` instruction and run `ollama pull` with the exact model name it specifies.

### The Custom Model Does Not Appear

Run:

```bash
ollama list
```

If `mineai-gemma` is missing, repeat the `ollama create` command and check the error message.

### MineAI Cannot Connect to Ollama

The default local API address is:

`http://localhost:11434`

Check that Ollama is running and that its local API is available.

### Responses Are Slow

Performance depends on your hardware, available memory, and the underlying model. Smaller models generally require fewer resources, although their responses may be less detailed or accurate.

## Important Notes

- The `Modelfile` contains model configuration and instructions; it is not the model's complete weights.
- Ollama downloads the base model separately.
- Creating `mineai-gemma` registers the custom model in your local Ollama installation. It does not upload the model to GitHub.
- AI-generated responses can be inaccurate or incomplete.
- MineAI does not automatically give the model Internet access or real-time knowledge.

## Official Resources

- [Ollama Website](https://ollama.com/)
- [Ollama Downloads](https://ollama.com/download)
- [Ollama Documentation](https://docs.ollama.com/)
- [MineAI Repository](../../)

---

**MineAI**  
Copyright © 2026 NikoCreations
