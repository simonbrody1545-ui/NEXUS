🤖 NEXUS

🧠 A powerful personal AI assistant for your computer

NEXUS is a JARVIS-style personal AI assistant designed to interact with your computer, understand voice input, see your screen/camera, remember information, use tools, and perform real actions.

It combines a Gemini Live AI core, real-time audio, a holographic-style avatar, computer automation, memory, plugins, browser control, vision, and a remote dashboard into one system.

⚡ NEXUS is designed to feel less like a chatbot and more like a digital assistant that can actually do things.

✨ Features

🧠 AI Core

🤖 Gemini-powered conversational intelligence

⚡ Real-time Gemini Live audio communication

🪜 Model fallback/ladders for more resilient AI requests

🧩 Automatic tool/action discovery

📝 Dynamic system knowledge about available capabilities

💾 Long-term local memory

🔎 Searchable stored memories

↩️ Undo support for supported actions

🎙️ Voice & Audio

🎤 Microphone input

🔊 Real-time AI voice responses

🗣️ Natural voice conversations

🎧 Microphone and speaker device selection

👂 Optional local "Hey Jarvis" wake-word support

🔇 Echo protection

🎙️ Push-to-talk support

👄 Real-time avatar lip-sync

👁️ Vision

🖥️ Screen capture and screen understanding

📷 Camera/surroundings processing

👀 Visual assistant capabilities

🧠 AI-powered interpretation of visual information

💻 Computer Control

NEXUS contains tools for interacting with the operating system, including:

🚀 Opening applications

🖱️ Computer/input control

📁 File management

🌐 Browser automation

🔍 Web searching

🖥️ Desktop actions

⚙️ System settings

🔊 System audio controls

📊 Process/system monitoring

🌐 Network-related tools

🔄 Power controls

📺 YouTube/video control

⚠️ Some actions can affect your computer. Only enable/use capabilities you understand and trust.

🧩 Plugin System

NEXUS can extend its capabilities through Python plugins.

Examples included in the project include:

📧 Discord/remote messaging

📊 Excel generation

🧠 General-purpose agents

🧪 Simulations

⏱️ Pomodoro tools

🧠 Second-brain functionality

📱 Telegram remote control

🎬 YouTube controls

📺 YouTube Studio tools

🔔 Notifications

💧 Water reminders

🧬 Hologram/CAD-related tools

Adding a new plugin can extend what the assistant can do without rewriting the entire core.

🌐 Remote Dashboard

NEXUS includes a web dashboard powered by FastAPI/Uvicorn.

The project contains interfaces for:

📱 Remote/phone access

📊 System information

🧠 Assistant status

🔐 Login/security

🕸️ Graph/network visualization

🛡️ Security

NEXUS includes security-related components such as:

🔐 Password protection

🧂 Salted password hashes

🔒 Confirmation gates for sensitive actions

↩️ Undo mechanisms

📝 Crash logging

🛑 Protected power/system operations

Never expose your API keys, private certificates, passwords, or security files publicly.

🏗️ Project Structure

NEXUS/
├── 🤖 actions/              # Computer, browser, system and web actions
├── 🧠 core/                 # AI, audio, vision, security and assistant core
├── 🧩 plugins/              # Optional/extended capabilities
├── 🧠 memory/               # Long-term memory and configuration
├── 🌐 dashboard/            # Web/phone dashboard
├── ⚙️ config/               # Configuration and security files
├── 💾 state/                # Runtime state, logs and generated data
├── 🖥️ ui/                  # Main graphical interface
├── 🚀 main.py               # Main application entry point
├── ⚙️ setup.py              # Installation/setup helper
├── 📦 requirements.txt      # Python dependencies
└── 📜 LICENSE               # Project license

💻 Supported Platforms

NEXUS is designed to work across:

🪟 Windows

🍎 macOS

🐧 Linux

Some computer-control features are naturally platform-specific.

🧰 Requirements

🐍 Python

The included setup script is designed for:

Python 3.11+

Python 3.11–3.13 is the tested range

Newer Python versions may work, but are not guaranteed by the included setup script.

📦 Main technologies

NEXUS uses technologies including:

🐍 Python

🖼️ PyQt6

🧠 Google Gemini / google-genai

🔢 NumPy

🎤 SoundDevice

🌐 Playwright

🌍 FastAPI

🚀 Uvicorn

👁️ OpenCV

🖼️ Pillow

💻 PyAutoGUI

📊 OpenPyXL

📄 python-pptx

🔐 Cryptography

🚀 Installation

1️⃣ Clone or extract the project

git clone <YOUR-REPOSITORY-URL>
cd NEXUS

Or simply extract the project ZIP and open the project folder.

2️⃣ Check Python

python --version

Python 3.11+ is recommended.

3️⃣ Install dependencies

The project includes a setup script:

python setup.py

This installs the Python dependencies and attempts to install the required Playwright browsers.

If you prefer installing dependencies manually:

python -m pip install -r requirements.txt

Then:

python -m playwright install chromium firefox

4️⃣ Configure your AI API key 🔑

NEXUS uses the Google Gemini API.

Add your API configuration using the project's configuration flow/files rather than publishing your key in GitHub.

🚨 NEVER commit a real API key to a public repository.

5️⃣ Launch NEXUS 🚀

python main.py

🎙️ Optional Wake Word

NEXUS can optionally use a local wake word.

Install the optional package:

pip install openwakeword

Then enable the wake-word feature from the application's settings.

Example:

🗣️ "Hey Jarvis"

The assistant can then wake up and begin listening.

🧩 Adding Plugins

Plugins live inside:

plugins/

A plugin can expose additional functionality to the assistant.

A simplified example:

TOOL = {
    "name": "my_tool",
    "description": "Does something useful."
}

def my_tool():
    return "Hello from NEXUS!"

The exact interface should follow the existing plugin/action patterns in the project.

🛠️ Actions vs Plugins

NEXUS separates capabilities into two major systems:

⚙️ Actions

Actions are core computer/system capabilities such as:

actions/
├── browser_control.py
├── computer_control.py
├── file_controller.py
├── open_app.py
├── process_manager.py
├── system_monitor.py
├── web_search.py
└── ...

🧩 Plugins

Plugins provide additional or optional capabilities:

plugins/
├── discord_messenger.py
├── excel_writer.py
├── general_agent.py
├── pomodoro.py
├── second_brain.py
├── telegram_remote.py
├── youtube_control.py
└── ...

This modular design makes it easier to add or remove capabilities.

🧠 Memory

NEXUS includes local memory functionality for retaining useful information across sessions.

Memory components include:

memory/
├── config_manager.py
├── memory_manager.py
└── long_term.json

Depending on configuration, the assistant can store and retrieve information from its local memory system.

🔐 Security Warning

Because NEXUS can control parts of a computer, security matters.

Before publishing this project:

❌ Do NOT upload

config/api_keys.json
config/security.json
config/lock.json
config/certs/*.key

if they contain real secrets or private credentials.

🔑 If a secret was accidentally published

Revoke/rotate the affected API key.

Replace exposed passwords or credentials.

Generate new certificates if necessary.

Remove secrets from Git history.

Add sensitive files to .gitignore.

🧪 Troubleshooting

❌ Python version error

Check:

python --version

Try Python 3.11–3.13 if your current version causes dependency problems.

🌐 Playwright doesn't work

Run:

python -m playwright install chromium firefox

🎤 Microphone doesn't work

Check:

Windows/macOS/Linux microphone permissions

The selected input device in NEXUS

Your system's default recording device

🔊 Audio output doesn't work

Check:

Your selected speaker/output device

System volume

Application audio permissions

🧠 Gemini doesn't respond

Check:

Your API key

Internet connection

Gemini API availability

The model/configuration selected by NEXUS

🗺️ Roadmap

Possible future upgrades:

🧠 More advanced autonomous agents

🏠 Smart-home integrations

🕶️ Wearable/AR interfaces

🤖 Physical robot integration

🛰️ Remote device control

🧩 More community plugins

🎨 More HUD/Avatar customization

🔐 Stronger permission management

🧠 Improved local/offline capabilities

⚠️ Responsible Use

NEXUS is a powerful automation project.

Do not use computer-control, network, messaging, surveillance, or automation capabilities to access systems or accounts you do not own or have permission to control.

Always review what an AI-controlled action will do before giving it permission to run.

❤️ Credits

Built as a personal AI-assistant project inspired by futuristic assistants such as JARVIS.

🤖 The goal: build an assistant that doesn't just answer — it helps you get things done.

📜 License

See LICENSE for the project's license and usage terms.

⭐ If you build something cool with NEXUS...

Improve it, extend it, add plugins, build new interfaces, and make it your own.

Welcome to NEXUS. 🤖⚡
