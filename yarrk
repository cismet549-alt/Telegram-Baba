from telegram import Update, ReplyKeyboardMarkup
from telegram.ext import ApplicationBuilder, CommandHandler, MessageHandler, filters, ContextTypes
import os

TOKEN = os.getenv("8781637871:AAHKu5D87AUhsh2QET62OTQQEWoIfOj2QCA")

menu = [
    ["📋 Profilim", "🛡 Güvenli Ticaret"],
    ["📨 Destek", "ℹ️ Bilgi"]
]

keyboard = ReplyKeyboardMarkup(menu, resize_keyboard=True)

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Bot aktif ✅ Menü hazır", reply_markup=keyboard)

async def mesaj(update: Update, context: ContextTypes.DEFAULT_TYPE):
    text = update.message.text

    if text == "📋 Profilim":
        await update.message.reply_text(f"ID: {update.effective_user.id}")

    elif text == "🛡 Güvenli Ticaret":
        await update.message.reply_text("Güvenli işlem başlatıldı 🛡")

    elif text == "📨 Destek":
        await update.message.reply_text("Destek: @admin")

    elif text == "ℹ️ Bilgi":
        await update.message.reply_text("Bu bot Railway üzerinde çalışıyor 🚀")

def main():
    app = ApplicationBuilder().token(TOKEN).build()

    app.add_handler(CommandHandler("start", start))
    app.add_handler(MessageHandler(filters.TEXT, mesaj))

    print("Bot çalışıyor...")
    app.run_polling()

main()
