# Real-Time Data Integration Strategy: MLB Live Bingo

To ensure the "Ballpark Bingo" experience is truly live and reactive, the system utilizes a three-tier data synchronization architecture. This ensures that every pitch, hit, and out is reflected on player cards within milliseconds of the event occurring at the stadium.

## 1. The Real-Time Feed (WebSocket Layer)
We utilize a persistent **WebSocket connection** (via a service like Pusher or a dedicated Node.js socket server) to stream live MLB Gameday data.
- **Event Polling**: The server-side engine polls official MLB data providers (Stats API) every 500ms.
- **State Diffing**: Instead of sending the entire game state, the server only broadcasts "State Diffs" (e.g., `event: "STRIKE_LOOKING", batter: "S. Suzuki"`).
- **Client Sync**: Your mobile app listens for these specific events. When a match is found on your unique 5x5 grid, the corresponding square pulses or "glows" to signal it's ready to be stamped.

## 2. AI Umpire Validation (Gemini Layer)
For complex plays (e.g., "Was that a sacrifice fly or just a deep out?"), the **Gemini 1.5 Pro** model acts as the "Decision Engine."
- **Contextual Analysis**: Gemini ingests the raw play-by-play text and matches it against the specific bingo square requirements.
- **Conflict Resolution**: If a player disputes a square, Gemini evaluates the official ruling and provides the "Umpire's Decision" in the Stadium Chatter feed, ensuring fair play across the room.

## 3. Client-Side Deterministic State
To handle spotty stadium Wi-Fi, the app uses a **Seeded Deterministic Generator**.
- **Board Integrity**: Every room has a unique `RoomID` used as a PRNG seed. This ensures everyone in the same room sees the same "Event Pool," even if they join mid-inning.
- **Optimistic Stamping**: Stamps are applied locally for instant feedback, then reconciled with the server-side "Official Scorebook" to prevent cheating or desync.

## 4. Proposed Data Schema
```json
{
  "game_id": "748592",
  "inning": "Top 7th",
  "last_play": {
    "type": "SINGLE",
    "player": "Ian Happ",
    "description": "Happ singles on a line drive to center field.",
    "timestamp": "2023-10-24T21:04:12Z"
  },
  "bingo_trigger": "base_hit_single"
}
```