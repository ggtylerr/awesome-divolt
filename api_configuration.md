# Contents
- [revolt.js](#revoltjs)
- [Revolt.NET](#revoltnet)
- [RevoltSharp](#revoltsharp)
- [Volt](#volt)
- [Java Revolt Bridge](#java-revolt-bridge)
- [Revolt.io](#revoltio)
- [Voltare](#voltare)
- [Revoltx](#revoltx)
- [Reject.js](#rejectjs)
- [Voltage](#voltage)
- [defectio](#defectio)
- [Revolt.py](#revoltpy)
- [Luster](#luster)
- [Robespierre](#robespierre)
- [Revolt.rs](#revoltrs)
- [Ruvolt](#ruvolt)
- [RevoltKit](#revoltkit)
- Not Compatible:
  - [Revolution](#revolution)
  - [Revoltgo](#revoltgo)
  - [Revoltkt](#revoltkt)
  - [pyrevolt](#pyrevolt)

## [revolt.js](https://www.npmjs.com/package/revolt.js)
```js
const { Client } = require("revolt.js");
let client = new Client();

client.configuration = {
  app: "https://api.divolt.xyz",
  ws: "wss://ws.divolt.xyz",
  features: {
    autumn:  { url: "https://autumn.divolt.xyz" },
    january: { url: "https://january.divolt.xyz" }
  }
}
```

## [Revolt.NET](https://www.nuget.org/packages/Revolt.Net/)
Note: Possibly broken with Divolt, have not been able to login successfully
```cs
using Revolt;

var client = new RevoltClient("https://api.divolt.xyz");
client.LoginAsync(TokenType.Bot, token).Wait();
```

## [RevoltSharp](https://github.com/xXBuilderBXx/RevoltSharp)
```cs
using RevoltSharp;

var config = new ClientConfig();
config.ApiUrl = "https://api.divolt.xyz";
config.Debug.UploadUrl = "https://autumn.divolt.xyz";
config.Debug.WebsocketUrl = "wss://ws.divolt.xyz";

var client = new RevoltClient(token, ClientMode.WebSocket, config);
```

## [Volt](https://github.com/volt-framework/volt)
```dart
import 'package:volt/volt.dart';

void main() {
  final bot = Volt(token, options: ClientOptions(
    httpBaseUrl: "api.divolt.xyz",
    wsBaseUrl: "ws.divolt.xyz"
  ));
}
```

## [Java Revolt Bridge](https://github.com/jrvlt/jrv)
Note: There's probably a way to set WS and such but jesus is javadocs horrid
```java
import ga.geist.jrv.RevoltBridge;
import ga.geist.jrv.RevoltEventListener;

import java.net.URI;
import java.net.URISyntaxException;

public class Main {
  public static class EventManager extends RevoltEventListener {
    ...
  }

  public static void main(String[] args) throws URISyntaxException {
    RevoltBridge jrv = new RevoltBridge(new URI("https://api.divolt.xyz"));

    jrv.registerEventListener(new EventManager());
  }
}

```

## [Revolt.io](https://github.com/revolt-io/revolt.io)
Note: AFAIK this package doesn't support CommonJS, you have to set it to ESM in your package.json file. (`"type": "module"`)
```js
import { Client } from 'revolt.io'
const client = new Client()

client.configuration = {
  app: "https://api.divolt.xyz",
  ws: "wss://ws.divolt.xyz",
  features: {
    autumn:  { url: "https://autumn.divolt.xyz" },
    january: { url: "https://january.divolt.xyz" }
  }
}
```

## [Voltare](https://github.com/Dexare/Voltare)
Note: This package is archived. You're also required to use the node parameter `--experimental-specifier-resolution=node` and to use ESM (set `"type": "module"` in package.json)
```js
import { VoltareClient } from 'voltare';

const client = new VoltareClient({
  login: {
    type: 'bot',
    token: token
  },
  revoltOptions: {
      apiURL: "https://api.divolt.xyz",
  },
  autumnHost: "https://autumn.divolt.xyz"
});
```

## [Revoltx](https://github.com/kaname-png/revoltx)
Note: You're required to use the node parameter `--experimental-specifier-resolution=node` and to use ESM (set `"type": "module"` in package.json)
```js
import { Client } from '@kaname-png/revoltx';

const client = new Client({ defaultPrefix: "!" });
client.x.configuration = {
  app: "https://api.divolt.xyz",
  ws: "wss://ws.divolt.xyz",
  features: {
    autumn:  { url: "https://autumn.divolt.xyz" },
    january: { url: "https://january.divolt.xyz" }
  }
}
```

## [Reject.js](https://github.com/revoltrejectorg/reject.js)
Note: This does not support Discord.js v14 yet.
```js
// Reject.js is just a layer for Discord.JS and Revolt.js, so you can just do a normal revolt client:
const RevoltClient = require("revolt.js").Client;

const bot = new RevoltClient();
bot.configuration = {
  app: "https://api.divolt.xyz",
  ws: "wss://ws.divolt.xyz",
  features: {
    autumn:  { url: "https://autumn.divolt.xyz" },
    january: { url: "https://january.divolt.xyz" }
  }
};

// ...and then add reject:
const reject = new RejectClient(bot);

const botReady = (client) => {
  console.log(`Logged in as ${client.user.username}`);
}
bot.on("ready", () => {
  botReady(reject);
})
```

## [Voltage](https://github.com/EnokiUN/voltage)
```py
import voltage
client = voltage.Client()

client.http.api_url = "https://api.divolt.xyz"
```

## [defectio](https://github.com/Darkflame72/defectio)
Note: This package is archived.
```py
import defectio
client = defectio.Client()

client.api_url = "https://api.divolt.xyz"

# It is also possible to change the WS URL using...
await client.create()
client.websocket.ws_url = "wss://ws.divolt.xyz"
# ...but good luck figuring out Python's broken async logic
```

## [Revolt.py](https://github.com/Zomatree/revolt.py)
```py
import revolt
import asyncio
import aiohttp

class Client(revolt.Client):
  ...

async def main():
  async with aiohttp.ClientSession() as session:
    client = Client(session, "token")
    client.api_url = "https://api.divolt.xyz"
    await client.start()


asyncio.run(main())
```

## [Luster](https://github.com/nerdguyahmad/luster)
Note: This package is still in a very early stage. Message sending isn't even supported and you'll have to use the HTTP and WebSocket handlers directly for basic stuff.
```py
import luster

client = luster.Client(token="token")
client.http_handler.BASE_URL = "https://api.divolt.xyz"
```

## [Robespierre](https://github.com/dblanovschi/robespierre)

## [Revolt.rs](https://github.com/AkiaCode/revolt.rs)

## [Ruvolt](https://github.com/Arthur-Damasceno/ruvolt)
TODO: Suffer through Rust and write up examples for the above 3 packages

## [RevoltKit](https://github.com/3PIV/RevoltKit)
Note: I don't own a Mac (so no XCode), there's no docs, and I don't know Swift. This is probably incorrect / incomplete.
```swift
let clientAPI = RevoltAPIClient

clientAPI.basePath = "https://api.divolt.xyz"
```

# ☠️ Not Compatible

## [Revolution](https://github.com/li223/Revolution)
See ["Revolt API 0.5.3 Support"](https://github.com/li223/Revolution/issues/1)

## [Revoltgo](https://github.com/5elenay/revoltgo)
See ["URLs are constant"](https://github.com/5elenay/revoltgo/issues/10)

## [Revoltkt](https://github.com/XuaTheGrate/RevoltKt)
Dead project, last commit was before API 0.5.3 which had breaking changes. Also the template doesn't even work and I was not able to make it work.

## [pyrevolt](https://github.com/GenericNerd/pyrevolt)
No current way to set API / WS URL. I may be incorrect though - the docs are auto-generated garbage and PyCharm didn't help. Also note that this is in Alpha.
