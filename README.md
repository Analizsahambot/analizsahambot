from telegram.ext import Updater, CommandHandler

# تابعی برای پاسخ به دستور /start
def start(update, context):
    context.bot.send_message(chat_id=update.effective_chat.id, text="سلام! ربات حاضر است.")

def main():
    # ساخت instance از Updater با توکن API ربات تلگرام شما
    updater = Updater(token='YOUR_TELEGRAM_BOT_TOKEN', use_context=True)

    # ساخت dispatcher برای ربات
    dp = updater.dispatcher

    # ثبت دستور /start با تابع start
    dp.add_handler(CommandHandler("start", start))

    # شروع پیگیری
    updater.start_polling()

    # فراخوانی عملکرد گره به صورت مداوم
    updater.idle()

if __name__ == '__main__':
    main()
