# 🍽️ Food/Beverages Evaluation Tool

A **real-time collaborative** tasting and quality assessment tool for evaluating food and beverages. Multiple evaluators can rate products simultaneously from different devices and see updates instantly.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Next.js](https://img.shields.io/badge/Next.js-14-black.svg)
![Deployment](https://img.shields.io/badge/deploy-Vercel-black.svg)

## ✨ Features

- **Real-time Collaboration** — Evaluators rate from different devices simultaneously
- **Unlimited Evaluators** — Add as many evaluators as needed
- **Custom Criteria** — Define your own evaluation criteria for any product type
- **Session-based** — Create or join sessions with a 6-character code
- **Live Updates** — See ratings appear instantly as others evaluate
- **Multi-Product Support** — Add and compare multiple products
- **Side-by-Side Comparison** — Compare all products in a clear table
- **Winner Highlighting** — Automatic identification of best scores
- **Export Reports** — Download complete evaluation results
- **Works Offline** — Falls back to polling if WebSockets unavailable

## 🚀 Quick Start

### Deploy to Vercel (Recommended)

1. **Fork/Clone this repository**

2. **Create a Pusher account** (free tier) at [pusher.com](https://pusher.com)
   - Create a new Channels app
   - Note your App ID, Key, Secret, and Cluster

3. **Deploy to Vercel**
   - Import your repository
   - Add environment variables (see below)
   - Deploy!

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/food-evaluator)

### Environment Variables

Set these in your Vercel project settings:

```env
# Pusher (required for real-time sync)
PUSHER_APP_ID=your_app_id
PUSHER_KEY=your_key
PUSHER_SECRET=your_secret
PUSHER_CLUSTER=your_cluster

NEXT_PUBLIC_PUSHER_KEY=your_key
NEXT_PUBLIC_PUSHER_CLUSTER=your_cluster

# Vercel KV (optional - for persistent storage)
# Automatically set when you add Vercel KV to your project
KV_REST_API_URL=
KV_REST_API_TOKEN=
```

### Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/food-evaluator.git
cd food-evaluator

# Install dependencies
npm install

# Copy environment file and fill in your values
cp .env.example .env.local

# Run development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📱 How to Use

### Starting a Session

1. **Create Session** — Click "Create New Session" to start
2. **Share Code** — Share the 6-character session code with evaluators
3. **Or Share Link** — Click "Share Link" to copy a direct join URL

### Configure Session (⚙️ Settings)

- **Add/Remove Evaluators** — Adjust the number of evaluators as needed
- **Customize Criteria** — Add, edit, or remove evaluation criteria
- Default criteria: Appearance, Aroma, Taste, Texture, Packaging

### Evaluating Products

1. **Add Products** — Click "+ Add Product" and enter details
2. **Select Product** — Click a product chip to evaluate it
3. **Rate Criteria** — Each evaluator rates their assigned criteria (1-5 stars)
4. **Add Comments** — Optional notes for each evaluator
5. **View Results** — Switch to "Compare Products" tab

### Scoring System

- Unrated criteria count as **0** (not skipped)
- Overall score = average of all criteria across all evaluators
- Best scores highlighted in green
- Overall winner marked with 🏆

## 🏗️ Project Structure

```
food-evaluator/
├── src/
│   ├── app/
│   │   ├── api/session/     # API routes
│   │   ├── layout.tsx       # Root layout
│   │   ├── page.tsx         # Main app
│   │   └── globals.css      # Styles
│   ├── lib/
│   │   ├── pusher-server.ts # Pusher server config
│   │   ├── pusher-client.ts # Pusher client config
│   │   └── storage.ts       # KV/memory storage
│   └── types.ts             # TypeScript types
├── package.json
├── next.config.js
└── tsconfig.json
```

## 🔧 Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Real-time**: Pusher Channels
- **Storage**: Vercel KV (Redis) or in-memory fallback
- **Styling**: CSS
- **Deployment**: Vercel

## 📊 Storage Options

### With Vercel KV (Recommended for Production)
- Sessions persist for 7 days
- Survives server restarts
- Add KV to your Vercel project

### Without Vercel KV (Development/Demo)
- In-memory storage
- Sessions lost on restart
- Perfect for local testing

## 🔄 Real-time Sync Options

### With Pusher (Recommended)
- Instant updates across all devices
- Free tier: 200K messages/day

### Without Pusher (Fallback)
- Polls server every 3 seconds
- Works but slightly delayed

## 🌍 Perfect For

- 🍷 Wine tastings
- 🍺 Beer evaluations
- 🧀 Cheese comparisons
- ☕ Coffee cuppings
- 🍫 Chocolate tastings
- 🐟 Seafood assessments
- 🥃 Spirits reviews
- Quality control assessments
- Product development feedback
- Blind tasting events

## 📄 License

MIT License — feel free to use, modify, and distribute.

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues and pull requests.

---

Made with ❤️ for food and beverage enthusiasts
