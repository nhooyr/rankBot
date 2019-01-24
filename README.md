# rankbot

Very simple rank bot for [Discord](https://discordapp.com) channels.

## Why?

In some channels you get some experience points for every message you send.

## Install

    go get github.com/nhooyr/rankbot

## Usage

    Usage of rankbot:
      -chan string
        	channel to join
      -del
        	delete every message as soon as it's been sent
      -email string
        	account email
      -guild string
        	guild (server) to join
      -idiom string
        	file containing a set of messages
      -int duration
        	interval between messages (default 1m0s)
      -mean-delay duration
        	mean additional delay
      -msg string
        	message to be sent (default "_")
      -pass string
        	account password
      -runtime duration
        	running time

Say we want to send messages to the "random" channel on the "Yellow Team"
server. We can get away with the following invocation:

    rankbot -email user@example.com \
            -pass password          \
            -guild 'Yellow Team'    \
            -chan random

This will send a message containing "_", every minute, until terminated.

To send a custom message:

    -msg "Hello from rankbot"

To pick messages randomly from the lines of a file:

    -idiom sayings.txt

To delete messages after sending them:

    -del

To choose a different interval between messages:

    -int 1s       # A message per second.
    -int 1h       # A message per hour.
    -int 2m30s    # A message every 2 minutes and a half.

To *further* delay messages by a random amount of seconds:

    -mean-delay 5m    # The average delay (added to the interval).

To set a run time, after which rankbot will terminate:

    -runtime 10h      # Run for 10 hours before exiting.
