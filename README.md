# Curio

Open-access museum art, curated by an agent. Ask for an artist, a feeling or something stranger, and Curio searches five museums' public-domain collections (the Art Institute of Chicago, Cleveland, The Met, the Statens Museum for Kunst and Minneapolis), looks at the works, reads what the museums say about them, and hangs a small exhibit with a note and a few comments on the works worth a closer look. Ask it about anything on the wall and it answers, or edits the exhibit in place. Every work is CC0 or public domain and downloads at full resolution with attribution.

Live at https://loupe-xi.vercel.app.

## Run it locally

```
npm install
npm run dev
```

Search, browsing, collections, downloads and the six recorded examples on the homepage work with no keys. Curio itself (and reading a description into a search) needs a model:

- **Local, free on a Claude subscription:** run `claude login` once (the Claude Code CLI). `npm run dev` then uses a local Claude session, locked to Curio's own tools.
- **AI Gateway:** copy `.env.example` to `.env.local` and set `AI_GATEWAY_API_KEY` to test the hosted path locally. On Vercel, the hosted site authenticates with OIDC automatically.

## Deploy

Vercel, with AI Gateway enabled. The hosted engine is chosen automatically and authenticates with Vercel OIDC. Set an AI Gateway budget because Curio makes several model calls per turn. See `.env.example` for model overrides and `AGENTS.md` for how everything fits together.

By [Shaun Latip](https://latip.me).
