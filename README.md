# MindEase — AI Mental Wellness App

> *Your safe space. Always available.*

A complete, production-ready mental wellness app built with React Native (Expo). Ships on iOS, Android, and Web from a single codebase.

---

## Screenshots & Features

| Screen | What it does |
|---|---|
| **Onboarding** | Animated 3-step flow — name, goal, disclaimer. Haptic feedback throughout. |
| **Home** | Mood logger (5 levels), streak tracker, sessions counter, quick actions |
| **AI Check-in** | Streaming Claude AI chat · distress keyword detection · crisis banner · live typing indicator |
| **Sessions** | 12 guided CBT exercises · filter by category · voice narration · ambient sounds · working seek/play player |
| **Insights** | 7-day mood bar chart · breakdown by mood · wellness tips · trend detection |
| **Therapist** | Therapist directory · booking flow · phone/text crisis resources |
| **Settings** | Edit name/goal · stats summary · clear mood history · full reset · legal disclaimer |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React Native + Expo SDK 52 |
| Navigation | Expo Router v4 (file-based) |
| Language | TypeScript (strict) |
| Fonts | DM Serif Display + DM Sans (Google Fonts) |
| Storage | AsyncStorage (on-device, private) |
| AI | Claude API via streaming SSE backend |
| Icons | Expo Feather + SF Symbols (iOS) |
| Dark mode | Automatic via `useColorScheme()` |
| Haptics | `expo-haptics` throughout |
| Tab bar | Liquid Glass (iOS 26+) / BlurView (iOS) / standard (Android/Web) |

---

## Quick Start

### 1. Install dependencies

```bash
npm install
```

### 2. Set environment variables

Create `.env` in the project root:

```env
EXPO_PUBLIC_DOMAIN=your-replit-domain.replit.dev
ANTHROPIC_API_KEY=sk-ant-your-key-here
```

Get your Claude API key free at: https://console.anthropic.com

### 3. Run

```bash
# Web preview (instant, no setup)
npx expo start --web

# iOS (requires Mac + Xcode)
npx expo run:ios

# Android
npx expo run:android

# Expo Go (scan QR, works on any phone)
npx expo start
```

---

## Preview Before Selling

**Best options to see the app live:**

| Tool | How | Cost |
|---|---|---|
| **Expo Go** (recommended) | Run `npx expo start`, scan QR with your phone | Free |
| **expo.dev web preview** | Run `npx expo start --web`, open browser URL | Free |
| **Snack (snack.expo.dev)** | Paste code into browser IDE, instant preview | Free |
| **Replit** | Import repo, run `npx expo start --web` | Free tier |
| **Netlify/Vercel** | Run `npx expo export -p web`, deploy `dist/` folder | Free |

---

## Customising for Your Brand

| What | File |
|---|---|
| App name | `app.json` → `"name"` and `"slug"` |
| Colours (light + dark) | `constants/colors.ts` |
| Sessions content | `app/(tabs)/sessions.tsx` → `ALL_SESSIONS` array |
| Therapist listings | `app/(tabs)/therapist.tsx` → `THERAPISTS` array |
| Crisis resources | `app/(tabs)/therapist.tsx` → `CRISIS_RESOURCES` array |
| AI personality/prompt | Server → `/api/anthropic` route system prompt |
| App icon | `assets/images/icon.png` (replace with 1024×1024 PNG) |
| Logo SVG | `assets/images/logo.svg` |

---

## Deploying

### Replit (easiest)
1. Import this repo into Replit
2. Add `ANTHROPIC_API_KEY` to Replit Secrets
3. Click Deploy → Autoscale
4. Live at `yourapp.replit.app`

### Web (Netlify/Vercel)
```bash
npx expo export -p web
# Upload the dist/ folder to netlify.com/drop
```

### App Stores
```bash
npm install -g eas-cli
eas login
eas build --platform all
eas submit --platform all
```

---

## Legal (required before launching publicly)

- ✅ Disclaimer shown on onboarding and settings: *"Not a substitute for professional mental health treatment"*
- ✅ Crisis resources panel on Therapist screen
- ✅ Distress detection with crisis banner in AI chat
- ⚠️ If storing data beyond on-device: use HIPAA-compliant backend (AWS HealthLake, Supabase + BAA)
- ⚠️ Sign a Business Associate Agreement (BAA) with any therapists you onboard
- ⚠️ Verify therapist licenses: NPI Registry (US), RCI (India)

---

## Folder Structure

```
app/
  (tabs)/
    index.tsx       # Home — mood, stats, actions
    chat.tsx        # AI check-in with distress detection
    sessions.tsx    # 12 CBT sessions with player
    insights.tsx    # Mood chart and wellness tips
    therapist.tsx   # Directory + crisis resources
  _layout.tsx       # Root layout, fonts, providers
  onboarding.tsx    # First-launch animated flow
  settings.tsx      # Profile, data management
assets/images/
  icon.png          # App icon (replace with yours)
  logo.svg          # New soothing line-art logo
components/         # Reusable UI components
constants/colors.ts # Full light + dark design tokens
context/AppContext  # Global state
hooks/useColors.ts  # Auto dark/light mode
utils/              # Web audio, ambient sounds
server/serve.js     # Claude API streaming backend
```

---

## License
MIT — free to use, modify, rebrand, and sell.
