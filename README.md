# play.themanaworld.org

The browser client of The Mana World, published on GitHub Pages.

The page is the WebAssembly build of the [Mana client](https://github.com/mana/mana)
(`wasm` branch), configured to connect straight to `server.themanaworld.org`
through the WebSocket proxy on that host, so players never see the server
dialog. The generic build, which shows the server list instead, lives at
https://mana.github.io/mana/.

The workflow in `.github/workflows/deploy.yml` builds the client from source
and deploys it. It runs on every push here, on a manual dispatch, and on a
`client-updated` repository dispatch event, which the client repository can
send after a successful build of its own.

Query parameters still override the baked-in settings: `server`, `port`,
`proxy`, `update-host`, `skip-update` and `default` map to the matching
client options.
