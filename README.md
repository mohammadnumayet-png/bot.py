import requests
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

BOT_TOKEN = "TELEGRAM_BOT_TOKEN"
SMS_API_URL = "BULKSMSBD_API_URL"
SMS_API_KEY = "BULKSMSBD_API_KEY"
SENDER_ID = "SENDER_ID"

async def sms(update: Update, context: ContextTypes.DEFAULT_TYPE):
    try:
        number = context.args[0]
        message = " ".join(context.args[1:])

        payload = {
            "api_key": SMS_API_KEY,
            "senderid": SENDER_ID,
            "number": number,
            "message": message
        }

        r = requests.post(SMS_API_URL, data=payload)

        if r.status_code == 200:
            await update.message.reply_text("✅ SMS পাঠানো হয়েছে")
        else:
            await update.message.reply_text("❌ SMS পাঠ
            BOT_TOKEN = "এখানে BotFather Token"
SMS_API_URL = "BulkSMSBD API URL"
SMS_API_KEY = "BulkSMSBD API Key"
SENDER_ID = "Approved Sender ID"
