Game Time Tracker Telegram Bot

This Python application monitors specified game processes on your computer, tracks the time spent playing each game, and sends notifications and statistics via a Telegram bot. It provides real-time updates when games start and stop, and allows you to query current sessions and accumulated playtime through Telegram commands.



Features

- Process Monitoring: Tracks specified game executables running on your system.
- Session Tracking: Records start and end times of game sessions.
- Accumulated Playtime: Maintains total playtime for each tracked game.
- Telegram Notifications: Sends messages to a Telegram chat when games start and stop.
- Telegram Commands: Supports commands to check current active games, view statistics, and get help.
- Thread-Safe: Uses threading and locks to safely manage shared data.
- Automatic Bot Restart: Handles Telegram bot errors and restarts polling automatically.

---

Supported Games

By default, the bot tracks the following game executables (you can modify this list in the code):

- game.exe
- steam.exe
- minecraft.exe

---

Requirements

- Python 3.7+
- psutil — for process monitoring
- pyTelegramBotAPI (also known as telebot) — for Telegram bot interaction
- python-dotenv — for loading environment variables from .env

Install dependencies via pip:

pip install psutil pyTelegramBotAPI python-dotenv

---

Setup

1. Create a Telegram Bot:

   - Talk to [@BotFather](https://t.me/BotFather) on Telegram.
   - Use /newbot to create a bot and get the bot token.

2. Get Your Chat ID:

   - Start a chat with your bot.
   - Use tools like [@userinfobot](https://t.me/userinfobot) or send a message to the bot and check updates via Telegram API to find your chat ID.

3. Create a .env file in the project directory with the following content:

   
   BOT_TOKEN=your_telegram_bot_token_here
   CHAT_ID=your_telegram_chat_id_here
   

---

## Usage

Run the script:

python your_script_name.py

The program will:

- Start monitoring the specified game processes.
- Launch the Telegram bot to interact with you.

You can type exit in the console to stop the program gracefully.



Telegram Bot Commands

- /start — Display a welcome message and basic instructions.
- /status — Show currently active game sessions with start times and elapsed durations.
- /stats — Show accumulated playtime statistics for all tracked games, including ongoing sessions.
- /help — Show available commands and the list of tracked games.



How It Works

- The script continuously scans running processes every 5 seconds.
- When a tracked game starts, it records the start time and sends a Telegram notification.
- When a tracked game stops, it calculates the session duration, updates total playtime, and sends a notification.
- The Telegram bot runs concurrently, responding to user commands.
- Thread locks ensure safe access to shared session data.



Customization

- Tracked Games: Modify the tracked_games list in the script to add or remove games by their process executable names.
- Polling Interval: Adjust the time.sleep(5) in monitor_processes() to change how often the script checks running processes.
- Messages: Customize notification and reply messages in the code to your preferred language or style.


Troubleshooting

- Bot Token or Chat ID Missing: Ensure your .env file is correctly set up and loaded.
- Permissions: Run the script with appropriate permissions to access process information.
- Telegram Bot Errors: The bot automatically retries on errors after 30 seconds.
- Process Names: Make sure the process names in tracked_games exactly match the executable names on your system.
