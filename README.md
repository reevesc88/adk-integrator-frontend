# ADK Integrator Frontend

> Web application for deploying AI agents from adk-samples to production in under 5 minutes

## Overview

The ADK Integrator Frontend provides a visual interface for the [ADK One-Shot Integrator](https://github.com/google/adk-samples) platform. Deploy AI agents to Cloud Run, AWS Lambda, or Azure Functions with one click.

## Features

- 🎨 **Modern UI**: Next.js 15 + TypeScript + Tailwind CSS v4
- ✨ **3D Animations**: GSAP for smooth transitions
- 🎭 **Premium Components**: shadcn/ui + React Bits registry
- 🤖 **MCP Integration**: Claude-powered component browsing
- 📊 **Visual Builder**: Real-time workflow designer
- 🚀 **Multi-cloud**: Deploy to GCP, AWS, Azure

## Tech Stack

- **Framework**: Next.js 15 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **Animations**: GSAP + @gsap/react
- **Components**: shadcn/ui + React Bits
- **MCP**: shadcn MCP server (Claude)

## Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

## Installing Components

```bash
# shadcn/ui
npx shadcn add button card dialog

# React Bits (3D animations)
npx shadcn add @react-bits/animated-gradient
npx shadcn add @react-bits/3d-card
npx shadcn add @react-bits/magnetic-button
```

Browse more: [reactbits.dev](https://reactbits.dev)

## Project Structure

```
src/
├── app/           # Next.js App Router pages
├── components/    # React components
│   └── ui/       # shadcn/ui components
├── lib/          # Utilities & API client
└── hooks/        # Custom React hooks
```

## MCP Integration

Ask Claude to browse and install components:
- "Install an animated button"
- "Add a 3D card component"
- "Search for loading spinners"

## Documentation

See [README-SETUP.md](./README-SETUP.md) for detailed setup guide with GSAP examples.

## Related Projects

- [adk-samples](https://github.com/google/adk-samples) - Google ADK agents
- [agent-starter-pack](https://github.com/GoogleCloudPlatform/agent-starter-pack) - Production infrastructure

## License

MIT
