# Database & Analytics Architecture: Ballpark Bingo

To manage user logins and track complex gameplay analytics, we recommend a relational database structure (like PostgreSQL) paired with a real-time event store (like Firebase or Supabase).

## 1. Data Schema Overview

### Users Table (Authentication & Identity)
Stores core profile information and authentication credentials.
- `user_id`: Unique Identifier (UUID)
- `username`: Player's display name (e.g., Casey 'The Ace' Miller)
- `email`: Contact for account recovery
- `created_at`: Join date
- `membership_tier`: (Rookie, Pro, Hall of Fame)

### Game Sessions Table (Analytics)
Tracks every individual game a user participates in.
- `session_id`: Unique game ID
- `user_id`: Reference to the player
- `game_matchup`: (e.g., "SF Giants @ CHI Cubs")
- `duration_seconds`: Time spent in game
- `stamps_manual`: Number of manual marks
- `stamps_auto`: Number of AI-assisted marks
- `bingo_achieved`: Boolean (True/False)

### Events Log (Granular Behavior)
A high-volume table for behavioral analysis.
- `event_type`: (LOGIN, CARD_SHUFFLE, STAMP_APPLIED, CHAT_MESSAGE, FEEDBACK_SUBMITTED)
- `metadata`: JSON blob containing specific details (e.g., which square was stamped)
- `timestamp`: Precise UTC time

## 2. Analytics Strategy

- **Engagement Metrics**: Track "Daily Active Users" (DAU) and average session length to measure app stickiness.
- **Conversion Tracking**: Monitor how many users switch from "Manual" to "Auto-Mark" mode.
- **Retention Analysis**: Use the `created_at` field to see how many "Rookies" return for a second game after onboarding.

## 3. Tooling Recommendations
- **Database**: PostgreSQL (for structured user data)
- **Authentication**: Auth0 or Supabase Auth
- **Analytics Visualization**: Posthog or Mixpanel (integrated via the Events Log)