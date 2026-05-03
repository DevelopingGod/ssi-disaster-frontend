# Natural-Disaster.io — Frontend

> **Live site:** [natural-disaster-io.vercel.app](https://natural-disaster-io.vercel.app)  
> **Backend repo:** [ssi-disaster-dashboard](https://github.com/DevelopingGod/ssi-disaster-dashboard)  
> **Built by:** [Sankalp Sandeep Indish](https://www.linkedin.com/in/sankalp-indish/) · [GitHub](https://github.com/DevelopingGod)

![Next.js](https://img.shields.io/badge/Next.js-15-000000?style=flat&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38BDF8?style=flat&logo=tailwindcss&logoColor=white)
![Leaflet](https://img.shields.io/badge/Leaflet-map-199900?style=flat&logo=leaflet&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-deployed-000000?style=flat&logo=vercel&logoColor=white)

---

## Overview

This is the Next.js 15 frontend for Natural-Disaster.io — an AI-powered disaster intelligence platform. It communicates with a FastAPI + LangGraph backend to deliver real-time, natural-language disaster briefings plotted on a live interactive map.

Users can ask anything — *"What earthquakes happened in Japan this week?"* or *"Show me active wildfires in Asia"* — in any language, and receive a structured AI-synthesised response with matching events pinned on a geospatial map.

---

## Features

- **Natural-language interface** — conversational chat UI with markdown-rendered agent responses
- **Live interactive map** — Leaflet world map with Dark, Light, Satellite, and Terrain layer switching; pins show lat/lon on click
- **Resizable split layout** — drag the chat/map divider; position persists across sessions via `localStorage`
- **Auto-briefing on load** — global disaster overview fetched automatically when a new session opens
- **Multi-query support** — "earthquakes and cyclones in Asia" filters both the text and map correctly
- **Rotating loading messages** — contextual status updates while the agent fetches live data
- **Clear chat with confirmation** — two-click clear with a 4-second auto-cancel safety window
- **UTC timestamps** — all event times displayed in Coordinated Universal Time
- **Fully responsive** — works on desktop and mobile

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 15 (App Router) + React 18 |
| Language | TypeScript |
| Styling | Tailwind CSS v4 |
| Map | Leaflet via `react-leaflet` |
| Markdown | `react-markdown` |
| Icons | `lucide-react` |
| Deployment | Vercel |

---

## Pages

| Route | Description |
|-------|-------------|
| `/` | Landing page — hero, feature modules, data partners |
| `/dashboard` | Main intelligence interface — chat + live map |
| `/about` | Developer profile and data source credits |
| `/why` | Platform differentiators vs general-purpose LLMs |
| `/terms` | Terms and conditions |
| `/privacy` | Privacy policy |

---

## Local Development

This frontend connects to the FastAPI backend. Run the backend first (see the [backend repo](https://github.com/DevelopingGod/ssi-disaster-dashboard)), then:

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

By default the frontend calls `http://localhost:8000/chat`. To point it at the production backend instead, create a `.env.local` file:

```env
NEXT_PUBLIC_BACKEND_CHAT_URL=https://sankalp-indish-ssi-disaster-dashboard.hf.space/chat
```

---

## Project Structure

```
├── app/
│   ├── page.tsx              # Landing page
│   ├── dashboard/page.tsx    # Dashboard — chat + map
│   ├── about/page.tsx        # About page
│   ├── why/page.tsx          # Why Natural-Disaster.io
│   ├── terms/page.tsx        # Terms & conditions
│   ├── privacy/page.tsx      # Privacy policy
│   └── globals.css           # Coffee Dark design system + CSS variables
├── components/
│   ├── ChatPanel.tsx         # Chat UI, loading messages, clear confirmation
│   ├── MapPanel.tsx          # Leaflet map, layer switcher, lat/lon popups
│   ├── Navbar.tsx            # Navigation bar
│   ├── Footer.tsx            # Footer
│   └── BackendWarm.tsx       # Silent HuggingFace Space warm-up on page load
└── lib/
    ├── api.ts                # sendChatQuery(), warmBackend()
    └── types.ts              # Shared TypeScript types
```

---

## Designer & Developer

**Sankalp Sandeep Indish** — AI Engineer specialising in agentic workflows and LLM systems.

- LinkedIn: [linkedin.com/in/sankalp-indish](https://www.linkedin.com/in/sankalp-indish/)
- GitHub: [github.com/DevelopingGod](https://github.com/DevelopingGod)

---

## License

MIT
