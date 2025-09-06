# telegram-chatbot-gemini

This project is a simple but powerful Telegram chatbot built using n8n, a workflow automation tool. It uses Google's Gemini model to respond to user messages in real-time, providing a conversational and interactive experience.

How to Import and Run the Workflow
To run this chatbot, you'll need an n8n instance and API credentials for both Telegram and Google Gemini.

Prerequisites
A running instance of n8n (Self-hosted or Cloud).

A Telegram Bot Token (You can get this from BotFather on Telegram).

A Google Gemini API Key.

Step-by-Step Guide
1. Import the Workflow
Open your n8n dashboard and navigate to the "Workflows" section.
Click on "New" and then select "Import from JSON."
Paste the contents of the telegram-chatbot-gemini.json file into the provided text box and click "Import."

2. Configure Credentials
The imported workflow will show credential errors because it's missing your API keys. You need to configure them.

Telegram Trigger: Double-click the "Telegram Trigger" node. In the credentials section, click "Create New" and paste your Telegram Bot Token into the Bot Token field.

Google Gemini Chat Model: Double-click the "Google Gemini Chat Model" node. In the credentials section, click "Create New" and paste your Google Gemini API Key into the API Key field.

3. Activate the Workflow
Once your credentials are set, save the workflow. In the top-right corner of the editor, click the "Active" toggle to turn on the workflow.

4. Set up the Webhook
Open the "Telegram Trigger" node again. You will now see a Webhook URL. Copy this URL. To connect your Telegram bot to n8n, you need to tell Telegram where to send messages. You can do this by opening a new browser tab and navigating to the following URL, replacing YOUR_BOT_TOKEN and YOUR_WEBHOOK_URL with your actual values:

https://api.telegram.org/bot<YOUR_BOT_TOKEN>/setWebhook?url=<YOUR_WEBHOOK_URL>

A successful response will confirm the webhook has been set.

5. Test Your Chatbot
Open your Telegram app, find your bot, and send it a message. The chatbot should now respond using the Gemini model!
