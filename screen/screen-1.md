# Create named session

screen -S `session name`

# List screen sessions

screen -ls

# Attach to session

screen -r `session name`

# Kill existing session

once attached:
ctrl-a :quit

# Detach from session

ctrl-a d

# Change screen escape key

edit ~/.screenrc
This sets escape key to ctrl-b instead:
`escape ^Bb` 

# Reload screenrc

ctrl-a :source ~/.screenrc
