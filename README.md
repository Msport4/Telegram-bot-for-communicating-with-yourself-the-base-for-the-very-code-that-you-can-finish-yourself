   from telegram import Update
   from telegram.ext import Updater, CommandHandler, CallbackContext

   # Функция для обработки команды /start
   def start(update: Update, context: CallbackContext) -> None:
       update.message.reply_text('Привет! Я ваш бот.')

   # Функция для обработки команды /привет
   def hi(update: Update, context: CallbackContext) -> None:
       update.message.reply_text('Привет! Как дела?')

   def main():
       # Вставьте сюда ваш токен
       TOKEN = 'YOUR_BOT_TOKEN_HERE'

       updater = Updater(TOKEN)

       # Получаем диспетчера для регистрации обработчиков
       dp = updater.dispatcher

       # Регистрация команд
       dp.add_handler(CommandHandler("start", start))
       dp.add_handler(CommandHandler("привет", hi))

       # Запуск бота
       updater.start_polling()

       # Ожидание завершения работы
       updater.idle()

   if __name__ == '__main__':
       main()
