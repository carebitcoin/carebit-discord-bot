# Carebit Discord Bot

Forked from https://github.com/gluneau/discord-crypto-bot and developed by J3ll3#9391

## Installing the prerequisites

```
sudo apt install python-pip
pip install pipenv
```

## Installing the bot:
```
git clone https://github.com/carebitcoin/carebit-discord-bot.git
cd discord-crypto-bot
pipenv install
```

## Here is a proposed sample for your .env file:
```
YOURDISCORDTOKEN=Nxxxxxxxxxxxxxxxxxxxxxx4.Dxxxxw.mxxxxxxxxxxxxxxxxxxxxxxxxxk
BOTSLEEP=15
BOTPAIR=STONE_BTC
BOTFIAT=USD
```

## Running the bot
```
pipenv run python3 bot.py
```

## Running the bot as a daemon, making sure it starts at bootup and if it crashes
```
1. Install the supervisord package. On Ubuntu/Debian this would be done with:
sudo apt-get install supervisor

2. Make sure you are running as root:
sudo -i

3. Go to the directory of supervisord where programs to be started are configured:
chdir /etc/supervisor/conf.d

4. Create a new configuration file:
vi discord_carebit_priceticker_bot.conf

5. Insert the following:
[program:CarebitPriceBot]
user=discordbot
directory=/home/discordbot/discord-crypto-bot
command=/home/discordbot/.local/bin/pipenv run python3 bot.py
autostart=true
autorestart=true
stderr_logfile=/var/log/CarebitPriceBot.err.log
stdout_logfile=/var/log/CarebitPriceBot.out.log

That is assuming you have placed your bot in the home directory of user discordbot.

6. Make sure supervisord rereads the configuration:
sudo supervisorctl reread

7. Hopefully it will show as running:
sudo supervisorctl status

output:
CarebitPriceBot                  RUNNING   pid 5244, uptime 0:34:51 

Installing python is outside the scope of this document, needless to say it needs to be installed.
```
