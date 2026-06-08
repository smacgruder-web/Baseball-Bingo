# Deployment & Infrastructure Audit: Baseball Bingo (Beta Ready)

To take Baseball Bingo from a design prototype to a production-ready mobile app, you need a high-concurrency, low-latency stack that can handle live MLB data and AI-driven features.

## 1. The "Stateful Edge" Architecture
Since your app relies on persistent WebSockets for live bingo stamps and chat, standard serverless (like Lambda) isn't enough.
- **WebSocket Gateway**: Use **AWS AppSync** or **Google Cloud Run with WebSockets**.
- **Edge Acceleration**: Route traffic through **Global Accelerators** (AWS Global Accelerator or Cloudflare Spectrum) to ensure players at the stadium have sub-500ms latency.
- **WebTransport**: For 2026 standards, prioritize **WebTransport over HTTP/3** to handle 5G signal drops without losing your bingo state.

## 2. Real-Time Data Ingestion (MLB Stats API)
The MLB Stats API has strict rate limits. Don't poll it from every phone!
- **Data Pipeline**: Set up a **Node.js worker** on your backend that polls the MLB API every 1s.
- **Caching Layer**: Store the current game state in **Redis**. 
- **Broadcast**: When a home run happens, your server broadcasts the "stamp" event to all 10,000 players in the room simultaneously via a single socket message.

## 3. AI Governance (Gemini Integration)
Your "AI Color Commentator" (Bleacher Bill) and Umpire Assistant can get expensive if left unchecked.
- **Token Buckets**: Implement **rate limiting** per user session. A user shouldn't be able to spam the Umpire for 1,000 questions a minute.
- **Model Routing**: Use **Gemini 1.5 Flash** for quick chat moderation and trivia, and save **Gemini 1.5 Pro** for complex rules disputes.
- **Streaming**: Always use **Streaming APIs** so the chat bubbles appear character-by-character, reducing perceived latency.

## 4. Client-Side Performance
- **Web Audio API**: Ensure the "Bat Crack" and "Organ" sounds are synthesized locally using **Audio Worklets**. Never stream .mp3 files over a shaky stadium Wi-Fi.
- **Delta Compression**: Only send the *change* in score or the *specific* square index being stamped. Don't re-send the whole board state.

## 5. Deployment Checklist
- [ ] **SSL/TLS Certificates**: Secure your socket connections.
- [ ] **Auth0/Supabase**: Secure user logins and analytics.
- [ ] **Circuit Breakers**: If the AI hits a rate limit, the app should gracefully fall back to manual bingo only.
- [ ] **Bot Detection**: Mandatory for official MLB data compliance.
