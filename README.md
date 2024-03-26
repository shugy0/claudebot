# claudebot
simple python script to run a claude 3 bot for your discord server

# how to run
```
pip install -r requirements.txt
python3 main.py
```

# features
- replies to discord messages with output from anthropic's API
- verbose logging, including each message's discord userID and username
- response status updates that are edited in the discord reply

# requirements
- anthropic API key + funded account
- discord API key + the bot account created and invited to your server(s)
- friendly server(s) cause there's no input validation :)
- python 3.8 or higher

# config notes
- you can change the model but opus (the default) is the best - https://docs.anthropic.com/claude/docs/models-overview
- you can change the max input and output tokens if you want to spend more or less money
- changing or removing the system prompt will greatly impact the output. if you remove it entirely, claude will not engage in any fun shenanigans. the "have fun" part makes for some cringe output sometimes, but you can see what your server(s) find funny

# extra notes
- rarely, the script misses a message (I blame discord). this is why I added the status updates. if you don't immediately get a reply, the script never saw the message
- this script was written almost entirely by claude 3 opus, directed by me. neat!
- rarely, claude will wrap the output in fake <response> tags. I assume this is because of the user tags. you could probably stop this by changing the system prompt or request formatting
- anthropic doesn't have a pre-request token counter in their python lib so I just use tiktoken. close enough
- I run mine on aws lightsail, but you can run yours locally or whatever
- sometimes it throws exceptions but it keeps working anyways lol
