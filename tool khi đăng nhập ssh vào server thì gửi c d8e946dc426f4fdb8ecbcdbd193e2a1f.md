# tool khi đăng nhập ssh vào server thì gửi cảnh báo telegram

Để gửi cảnh báo qua Telegram khi bạn đăng nhập vào một máy chủ thông qua SSH, bạn có thể sử dụng một số công cụ và kịch bản tùy chỉnh để thực hiện việc này. Dưới đây là hướng dẫn sử dụng một công cụ phổ biến là "Telegram Bot" để thực hiện cảnh báo này.

### Bước 1: Tạo Telegram Bot

1. Mở Telegram và tìm "BotFather" để tạo một bot mới. Bạn có thể tìm "BotFather" trong ô tìm kiếm của Telegram và theo hướng dẫn để tạo một bot.
2. Sau khi tạo bot, bạn sẽ nhận được một mã token cho bot của mình. Lưu trữ mã token này, chúng ta sẽ sử dụng nó trong bước tiếp theo.

### Bước 2: Cài đặt Telegram Bot trên máy chủ

1. Cài đặt một thư viện Telegram API để gửi tin nhắn từ máy chủ. Sử dụng pip (hoặc pip3 nếu bạn đang sử dụng Python 3):
    
    ```bash
    pip install python-telegram-bot
    
    ```
    
2. Tạo một mã Python script để gửi cảnh báo khi bạn đăng nhập. Dưới đây là một ví dụ về mã Python:
    
    ```python
    import telegram
    from telegram.ext import Updater, CommandHandler, MessageHandler, Filters, CallbackQueryHandler
    
    # Thay thế 'YOUR_BOT_TOKEN' bằng mã token của bot Telegram của bạn.
    bot_token = 'YOUR_BOT_TOKEN'
    chat_id = 'YOUR_CHAT_ID'  # Điều này cần được cung cấp bởi bạn.
    
    def send_notification(update, context):
        context.bot.send_message(chat_id=chat_id, text="SSH login detected: " + update.message.text)
    
    def main():
        bot = telegram.Bot(token=bot_token)
        updater = Updater(bot_token, use_context=True)
        dp = updater.dispatcher
    
        dp.add_handler(MessageHandler(Filters.text, send_notification))
    
        updater.start_polling()
        updater.idle()
    
    if __name__ == "__main__":
        main()
    
    ```
    
    Trong mã trên, bạn cần thay thế `YOUR_BOT_TOKEN` bằng mã token của bot Telegram của bạn và `YOUR_CHAT_ID` bằng chat ID của người nhận cảnh báo.
    
3. Chạy mã Python script trên máy chủ. Điều này sẽ khởi động một bot Telegram đang lắng nghe và gửi cảnh báo khi bạn đăng nhập vào máy chủ thông qua SSH.

### Bước 3: Kích hoạt cảnh báo SSH

Khi đã cài đặt bot Telegram và mã Python script, mọi lần bạn đăng nhập vào máy chủ qua SSH, bot Telegram sẽ gửi cảnh báo tới bạn thông qua Telegram. Đảm bảo rằng bạn đã cấu hình mã Python script này để khởi động cùng với hệ thống hoặc bằng một cách khác có thể sử dụng nó mọi khi có sự kiện đăng nhập SSH.