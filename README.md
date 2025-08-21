#!/bin/bash

# Script to generate an improved README for Nithi Telegram Chatbot
# Usage: Save as generate_readme.sh, make executable (chmod +x generate_readme.sh), then run ./generate_readme.sh
# Output: Creates README.md in the current directory

# Configuration
OUTPUT_FILE="README.md"
REPO_URL="https://github.com/username/nithi"  # Replace with actual repository URL
SCREENSHOT_DIR="screenshots"  # Directory for screenshots
WORKFLOW_IMAGE="$SCREENSHOT_DIR/4.png"  # Placeholder for workflow screenshot
CHAT_IMAGE="$SCREENSHOT_DIR/1.png"  # Placeholder for Telegram chat screenshot

# Create screenshots directory
mkdir -p "$SCREENSHOT_DIR"

# Write improved README content to file
cat << EOF > "$OUTPUT_FILE"
# Nithi – AI-Powered Telegram Chatbot 🤖

[![Telegram](https://img.shields.io/badge/Platform-Telegram-blue)](https://telegram.org)
[![n8n](https://img.shields.io/badge/Automation-n8n-orange)](https://n8n.io)
[![Mistral](https://img.shields.io/badge/AI-Mistral%20Chat%20Model-purple)](https://mistral.ai)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

**Nithi** (**Next-Gen Intelligent Telegram Helper Interface**) is an intelligent Telegram chatbot powered by **n8n automation**, **Mistral's LLM**, and **Telegram APIs**. It delivers real-time, personalized, AI-driven conversations with no coding required. 🚀

## ✨ Features

- **AI-Powered Conversations**: Leverages Mistral’s chat model for contextual and intelligent responses.
- **Fully Automated Workflow**: Built with n8n, easily customizable without coding.
- **Real-Time Telegram Integration**: Handles messages instantly via Telegram webhooks.
- **AI Agent Logic**: Performs reasoning, planning, and API calls autonomously.

## 🛠 Tech Stack

- **Automation**: [n8n](https://n8n.io)
- **LLM**: [Mistral Chat Model](https://mistral.ai)
- **Messaging**: [Telegram Bot API](https://core.telegram.org/bots/api)
- **Agent Layer**: n8n AI Agent node for advanced logic

## 📥 Setup and Installation

### Prerequisites
- Docker (recommended) or Node.js installed
- Telegram Bot Token (get from [BotFather](https://t.me/BotFather))
- Mistral API Key (get from [Mistral.ai](https://mistral.ai))
- n8n workflow file (\`nithi-workflow.json\`, included in this repository)

### Option 1: Run n8n in Docker (Recommended)

1. Pull and run the n8n Docker container:
   \`\`\`bash
   docker run -it --rm \\
     -p 5678:5678 \\
     -v ~/.n8n:/home/node/.n8n \\
     -e N8N_ENCRYPTION_KEY=your_secure_key \\
     -e TELEGRAM_BOT_TOKEN=your_telegram_token \\
     -e MISTRAL_API_KEY=your_mistral_api_key \\
     n8nio/n8n
   \`\`\`
2. Access the n8n dashboard at [http://localhost:5678](http://localhost:5678).
3. Import the workflow:
   - Go to **Workflows → Import → Import from File**.
   - Select \`nithi-workflow.json\` from this repository.
   - Save and activate the workflow to start the bot.

### Option 2: Run Locally (Node.js)

1. Install n8n globally:
   \`\`\`bash
   npm install -g n8n
   \`\`\`
2. Start n8n with environment variables:
   \`\`\`bash
   export N8N_ENCRYPTION_KEY=your_secure_key
   export TELEGRAM_BOT_TOKEN=your_telegram_token
   export MISTRAL_API_KEY=your_mistral_api_key
   n8n start
   \`\`\`
3. Access the n8n dashboard at [http://localhost:5678](http://localhost:5678).
4. Import and activate \`nithi-workflow.json\` as described above.

## 🖼 Workflow & Chat Previews

### n8n Workflow
The workflow in n8n includes nodes for Telegram triggers, AI agent processing, and Mistral LLM integration.

![Nithi Workflow]($WORKFLOW_IMAGE)

*Note*: To capture this screenshot, open the n8n dashboard, load the workflow, and use your system's screenshot tool (e.g., Snipping Tool on Windows or Shift+Command+4 on Mac).

### Telegram Chat
Example interaction with the Nithi bot on Telegram.

![Nithi Chat]($CHAT_IMAGE)

*Note*: To capture this screenshot, start a chat with your bot (e.g., @NithiBot), send test messages, and take a screenshot of the Telegram app.

## 🎯 Usage

1. Start a chat with your Telegram bot (e.g., @NithiBot).
2. Try these example prompts:
   - "Who are you?"
   - "Tell me something interesting."
   - "What can you do?"
3. Receive real-time, AI-generated responses powered by Mistral.

## 📜 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 📚 Resources
- [n8n Documentation](https://docs.n8n.io)
- [Telegram Bot API](https://core.telegram.org/bots/api)
- [Mistral AI](https://mistral.ai)
- [Repository]($REPO_URL)

## ⚠️ Notes
- Replace placeholder environment variables (\`your_secure_key\`, \`your_telegram_token\`, \`your_mistral_api_key\`) with actual values.
- If images are missing, set up the bot and capture screenshots as described in the preview section.
- For support, check the [n8n Community](https://community.n8n.io) or open an issue in this repository.
EOF

# Notify user
echo "Improved README generated at $OUTPUT_FILE"
echo "Next steps:"
echo "1. Update REPO_URL in the script with the actual GitHub repository URL."
echo "2. Set up Nithi using the instructions in the README."
echo "3. Capture screenshots of the n8n workflow and Telegram chat."
echo "4. Place screenshots in $SCREENSHOT_DIR and update $WORKFLOW_IMAGE and $CHAT_IMAGE paths in README.md."
echo "5. Push README.md and screenshots to your repository."
