# Joter Blox
A Node.js multiplayer 2D platforming shooter

## Running with Docker

```sh
cp .env.example .env
docker network create stack 2>/dev/null || true
docker compose up -d --build
```

The app listens on `127.0.0.1:33016` (host) → port 3000 (container).  
nginx vhost: `joterblox.nimos.ws` (see `nginx.conf`).

## Environment variables

| Variable    | Default                                | Description            |
|-------------|----------------------------------------|------------------------|
| `MONGO_URL` | `mongodb://mongo:27017/joterblox`      | MongoDB connection URL |
| `PORT`      | `3000`                                 | App listen port        |

> Note: MongoDB persistence (player profiles/sessions) is currently disabled in
> `classes/Profile.js` — the mongo service is provisioned for future re-enable.

## Development

```sh
npm install
node Game.js
```

Entry point: `Game.js`, port configurable via `PORT` env (default 3000).

# License

Unless specified otherwise, all code files are licensed under AGPL, see LICENSE.txt for more information.  
The font found in assets/PressStart2P.tff is licensed under OFL, see OFL.txt  
All other files in assets/ are licensed under [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/), (C) 2016 [The Joterblox Team](https://github.com/Nimos/joterblox)
