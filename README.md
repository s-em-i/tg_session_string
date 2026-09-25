# How to get your Telegram Session String
Save your **API_ID** and **API_HASH** into the `tg_session_string.py` script,\
run it, and it prints out a very long session string -> your **TELEGRAM_SESSION**

```
import telethon, sys
from telethon import TelegramClient
from telethon.sessions import StringSession

async def main(client: telethon.TelegramClient):

    if(not client.is_connected()):
        await client.connect()
    
    session_string = client.session.save()
    print(f"\nSESSION STRING (for GitHub Secrets):")
    print(session_string)

###### Script Entrypoint ######

api_id = ""
api_hash = ""

client = TelegramClient(StringSession(), api_id, api_hash)

with client:
   client.loop.run_until_complete(main(client))
```

<a name="license"></a>
## License
`TDLib Flutter Client prebuilt Binaries` is licensed under the terms of the Boost Software License. See [LICENSE_1_0.txt](http://www.boost.org/LICENSE_1_0.txt) for more information.
