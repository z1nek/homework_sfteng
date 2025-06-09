playtime_tracker_AnnaSemen

A Telegram bot for monitoring and tracking game sessions on your PC.


Table of Contents

- Features
- Prerequisites
- Installation
- Configuration
- Usage
- Bot Commands
- Contributing
- License

Features

- Monitors selected game processes in real time (e.g., `steam.exe`, `minecraft.exe`)
- Sends Telegram notifications when games start and stop
- Tracks and accumulates total playtime for each game
- Provides commands for checking active sessions and overall statistics
- Runs monitoring and Telegram bot concurrently using multithreading

Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.9 or higher installed on your system ([Download Python](https://www.python.org/downloads/))
- Telegram account (to interact with the bot)
- Access to create a Telegram bot via [BotFather](https://t.me/BotFather)
- Your Telegram chat ID (for receiving notifications)

Installation

1. Clone the repository or download the source code

    ```bash
    git clone https://github.com/z1nek/playtime_tracker_AnnaSemen.git
    cd playtime_tracker_AnnaSemen
    ```

2. Create and activate a virtual environment:

    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\Activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```


Configuration

1. Create a `.env` file** in the project root directory with the following content:

    ```
    BOT_TOKEN= your_telegram_bot_token
    CHAT_ID= your_telegram_chat_id
    ```

    - `BOT_TOKEN` — Token you get from [BotFather](https://t.me/BotFather).
    - `CHAT_ID` — Your Telegram chat ID (can be obtained by messaging your bot and checking updates via Telegram API).

2. *(Optional)* Adjust the list of tracked games in `main.py` by editing the `tracked_games` list:

    ```python
    tracked_games = ['game.exe', 'steam.exe', 'minecraft.exe']
    ```


Usage

1. Run the bot:

    ```bash
    python main.py
    ```

2. Interact with your bot in Telegram:
    - Send `/start` to receive a welcome message and see available commands.
    - The bot will notify you when a tracked game starts or stops.
    - Use commands to check your gaming statistics.

Bot Commands

- `/start` — Show welcome message and available commands
- `/status` — Show currently active games and session durations
- `/stats` — Show accumulated gaming statistics
- `/help` — Show help message with commands and tracked games

Contributing

Contributions are welcome!  
To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes
4. Push to the branch (`git push origin feature/YourFeature`)
5. Create a Pull Request

Please follow [PEP8](https://pep8.org/) style guidelines and document your code.

License

This project is licensed under the MIT License.
