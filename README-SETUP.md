# ADK Integrator Frontend - Setup Complete! 🎉

## What's Been Installed

### ✅ Next.js 15 with TypeScript
- **Framework**: Next.js 15 (latest) with App Router
- **Language**: TypeScript with strict typing
- **Styling**: Tailwind CSS v4
- **Location**: `C:\Users\calum\adk-integrator-frontend`

### ✅ GSAP (GreenSock Animation Platform)
- **Package**: `gsap` + `@gsap/react`
- **Use**: 3D animations, smooth transitions, advanced UI effects

### ✅ shadcn/ui Components
- **MCP Server**: Configured for Claude integration
- **Config**: `.mcp.json` (MCP server configuration)
- **Components**: `components.json` with React Bits registry

### ✅ React Bits Registry
- **Registry**: `@react-bits` configured in `components.json`
- **URL**: `https://reactbits.dev/r/{name}.json`
- **Use**: Install premium UI components via natural language

---

## Quick Start

### 1. Start Development Server
```bash
cd ~/adk-integrator-frontend
npm run dev
```

Then open http://localhost:3000

### 2. Install shadcn Components
```bash
# Using natural language with MCP
npx shadcn add button

# From React Bits registry
npx shadcn add @react-bits/animated-card
npx shadcn add @react-bits/3d-carousel
```

### 3. Use GSAP for Animations
```typescript
// src/components/AnimatedHero.tsx
'use client';

import { useGSAP } from '@gsap/react';
import gsap from 'gsap';
import { useRef } from 'react';

export function AnimatedHero() {
  const containerRef = useRef<HTMLDivElement>(null);

  useGSAP(() => {
    gsap.from('.hero-title', {
      y: 100,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    });

    gsap.from('.hero-subtitle', {
      y: 50,
      opacity: 0,
      duration: 1,
      delay: 0.3,
      ease: 'power3.out'
    });
  }, { scope: containerRef });

  return (
    <div ref={containerRef}>
      <h1 className="hero-title">ADK Integrator</h1>
      <p className="hero-subtitle">Deploy AI agents in under 5 minutes</p>
    </div>
  );
}
```

### 4. Use React Bits Components
Browse available components at: https://reactbits.dev

Examples:
```bash
# 3D Card Hover Effects
npx shadcn add @react-bits/3d-card

# Animated Charts
npx shadcn add @react-bits/animated-chart

# Interactive Particles
npx shadcn add @react-bits/particles-background
```

---

## Project Structure

```
adk-integrator-frontend/
├── src/
│   ├── app/                # Next.js App Router
│   │   ├── layout.tsx      # Root layout
│   │   ├── page.tsx        # Home page
│   │   └── globals.css     # Global styles
│   ├── components/         # React components
│   │   └── ui/            # shadcn/ui components
│   ├── lib/               # Utility functions
│   └── hooks/             # Custom React hooks
├── public/                # Static assets
├── components.json        # shadcn config + React Bits registry
├── .mcp.json             # MCP server config (Claude)
├── tailwind.config.ts    # Tailwind configuration
├── tsconfig.json         # TypeScript config
└── package.json          # Dependencies
```

---

## Available Scripts

```bash
npm run dev       # Start dev server (http://localhost:3000)
npm run build     # Build for production
npm run start     # Start production server
npm run lint      # Run ESLint
```

---

## React Bits Registry Usage

The `@react-bits` registry is configured in `components.json`:

```json
{
  "registries": {
    "@react-bits": "https://reactbits.dev/r/{name}.json"
  }
}
```

### Installing Components from React Bits

```bash
# Syntax: npx shadcn add @react-bits/<component-name>

# Examples:
npx shadcn add @react-bits/animated-gradient
npx shadcn add @react-bits/glass-morphism-card
npx shadcn add @react-bits/magnetic-button
npx shadcn add @react-bits/parallax-scroll
```

### Using MCP with Claude

With the MCP server configured, you can ask Claude to:
- "Install an animated card component"
- "Add a 3D carousel from React Bits"
- "Search for particle effects components"

Claude will automatically use the shadcn MCP server to browse and install components.

---

## GSAP Animation Examples

### 3D Card Flip
```typescript
import { useGSAP } from '@gsap/react';
import gsap from 'gsap';

export function Card3D() {
  const cardRef = useRef(null);

  useGSAP(() => {
    gsap.to(cardRef.current, {
      rotationY: 180,
      duration: 0.6,
      ease: 'power2.inOut',
      paused: true,
      id: 'flip'
    });
  });

  return (
    <div
      ref={cardRef}
      onMouseEnter={() => gsap.getById('flip')?.play()}
      onMouseLeave={() => gsap.getById('flip')?.reverse()}
    >
      {/* Card content */}
    </div>
  );
}
```

### Scroll-Triggered Animations
```typescript
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

useGSAP(() => {
  gsap.from('.feature', {
    scrollTrigger: {
      trigger: '.features',
      start: 'top center',
      end: 'bottom center',
      scrub: 1
    },
    y: 100,
    opacity: 0,
    stagger: 0.2
  });
});
```

---

## Next Steps

1. **Design the Dashboard**: Create the main dashboard page with animated 3D cards
2. **Agent List UI**: Build the agent browser with filtering and search
3. **Deployment Monitor**: Real-time deployment status with GSAP progress animations
4. **Workflow Builder**: Visual graph editor using @xyflow/react + GSAP transitions

---

## Useful Links

- **Next.js Docs**: https://nextjs.org/docs
- **GSAP Docs**: https://gsap.com/docs/v3/
- **shadcn/ui**: https://ui.shadcn.com
- **React Bits**: https://reactbits.dev
- **Tailwind CSS**: https://tailwindcss.com/docs

---

## Integration with Backend

When ready to connect to the FastAPI backend (from the implementation plan):

```typescript
// lib/api-client.ts
const API_BASE_URL = process.env.NEXT_PUBLIC_API_URL || 'http://localhost:8000';

export async function listAgents() {
  const res = await fetch(`${API_BASE_URL}/api/v1/agents`);
  return res.json();
}

export async function deployAgent(agentName: string, platform: string) {
  const res = await fetch(`${API_BASE_URL}/api/v1/deployments`, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ agent_name: agentName, platform })
  });
  return res.json();
}
```

---

**Status**: ✅ Frontend setup complete!
**Next**: Start building your dashboard with animated 3D components!
