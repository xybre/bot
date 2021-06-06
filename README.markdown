# Bot

Yet another chat bot written in Go.

## TODO

### Protocols

- IRC
- Twitch
- Discord

### Link Info

- display titles of URLs in chat
- display info about URL if no title present
- truncate length of titles that are over a given length

### Commands in General

- display help and list commands available to the asking user for that channel/query
- runtime settable simple commands for like quick reference to documentation or common links or rules
- commands can validate number and type of arguments
- commands can specify arguments by names (this can be done in Go using reflect)

### User Profiles

- stores a pronoun list for users
- stores other profile data about users, like if they have a website, soundcloud, or bandcamp that they want to share
- kudos functionality like "nick++"

### Music Functionality

- display random Oblique and Acute Strategies command
- track URLs in chat, particularly music from YT, Spotify, Bandcamp
- bandcamp/spotify/musicbrainz/freedb lookup from command
- lyrics lookup via Genius

### Persistence / Network Config

- persistent config to store all settings (TOML, SQLite, or similar)
- nick configurable
- list channels to join
- SASL support during connection
- TLS support for data in transit
- raw logs can be retained
- debug and other log events are collected through similar mechanisms as the raw logs so they can be stored together for drawing correlations for debugging/abuse forensics

### Developer Commands

- syntax highlight command for various languages like: `!hl ruby def foo; puts "foo"; end`
- run code command for various languages: `!run ruby puts RUBY_VERSION`

### IRC Games

- channel games: tic-tac-toe, russian nesting doll tic-tac-toe, hangman (with dictionary words, band names, genres, etc), trivial pursuit (music)
- alternative NLP conversational interactive commands using "botnick: " prefix and/or "@botnick" forms of address?
- dice roller: coin flip, fate dice, d20, etc like `!roll 5d6`
- probability analyzer, like `!probability 5d6` would give the median/mean roll

### Opers & Access

- user ACL is persisted and can be set at runtime
- configurable command prefix per channel default of `!` but `:` and `.` are also common, shouldn't be limited to a single char
- rate limits and timeouts can be set on-the-fly by opers
- understands Libera's implementation of NickServ and ChanServ
- understands hostnames and account names with NickServ
- understands channel access and account access via ChanServ
- opers can request that they be noticed/DMed debug events
- ability to set bot access/managers/moderators/ops with various permissions
- ability to set bot capabilities per channel
- bot ops can tell the bot to run arbitrary commands or say arbitrary things
- rate limits and timeouts for all output, channel output, and per user command input (for non-opers)

### Moderation / Events

- automod capabilities to +q or +b users who flood, repeat, match spam keywords, or join/part repeatedly
- bot attempts to correlated nicks, hosts, and NickServ accounts (where available)
- respond to events such as joins, keyword questions, with welcome or help info
