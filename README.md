Nithi – AI-Powered Telegram Chatbot 🤖📅
Nithi (Next-Gen Intelligent Telegram Helper Interface) is a smart, AI-powered Telegram chatbot that automates your daily tasks, answers your questions, and keeps you on top of your schedule—all in one place. Built with n8n, Mistral AI, and Telegram Bot API, Nithi is your personal assistant, always ready to help. 🚀

## ✨ Features

- **AI-Powered Conversations** – Answers personal and contextual questions using Mistral’s chat model  
- **Fully Automated Workflow** – Built with **n8n**, no manual coding required  
- **Telegram Triggers & APIs** – Real-time message handling with webhook integration  
- **Calendar Reminders** – Automatically sends upcoming events and tasks to Telegram  
- **AI Agent Layer** – Handles reasoning, planning, and API calls on its own  
Agent Logic: n8n AI Agent node
📥 Quick Setup
Option 1: Docker (Recommended)
Copy
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  -e N8N_ENCRYPTION_KEY=your_secure_key \
  -e TELEGRAM_BOT_TOKEN=your_telegram_token \
  -e MISTRAL_API_KEY=your_mistral_api_key \
  -e CALENDAR_API_KEY=your_calendar_api_key \
  n8nio/n8n
Open http://localhost:5678
Import nithi-workflow.json and activate the workflow.
Option 2: Local (Node.js)
Copy
npm install -g n8n
export N8N_ENCRYPTION_KEY=your_secure_key
export TELEGRAM_BOT_TOKEN=your_telegram_token
export MISTRAL_API_KEY=your_mistral_api_key
export CALENDAR_API_KEY=your_calendar_api_key
n8n start
Open http://localhost:5678
Import and activate the workflow.
🖼 Previews


n8n Workflow
Telegram Chat
🎯 How It Works
You send a message to your Telegram bot.
Nithi processes your request using Mistral AI for natural language understanding.
n8n automates the response—fetching calendar events, sending reminders, or answering questions.
You get instant, helpful replies—right in Telegram!
💬 Example Commands
"What’s on my schedule today?"
"Remind me about my meeting at 3 PM."
"Tell me a fun fact!"
📜 License
This project is MIT Licensed.

