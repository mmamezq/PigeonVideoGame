# Decisions

Use this log to preserve important project decisions and their context.

## Decision template

### YYYY-MM-DD: Decision title

- **Status:** Proposed, accepted, superseded, or rejected
- **Context:** What problem or question prompted this decision?
- **Decision:** What did the team decide?
- **Reasons:** Why was this option selected?
- **Consequences:** What tradeoffs or follow-up work does it create?

## Log

### 2026-11-07: Isometric story-driven RPG with real-time combat

- **Status:** Accepted
- **Context:** We needed a genre and view for the pigeon knight game.
- **Decision:** Make an isometric, story-driven RPG with real-time
  bird-vs-bird combat.
- **Reasons:** Isometric towns suit cozy hubs, and real-time combat makes
  displays feel active and expressive.
- **Consequences:** The engine must handle isometric maps well.

### 2026-11-07: Only birds fight

- **Status:** Accepted
- **Context:** Displays (puff, coo, turn) only make sense between birds.
- **Decision:** All combat is bird vs. bird. Other animals are townsfolk and
  never fight. Some birds, such as the owl and crows, are also non-combatants.
- **Reasons:** Keeps displays meaningful in every fight.
- **Consequences:** Opponent variety comes from different bird species.

### 2026-11-07: Displays are the core combat mechanic

- **Status:** Accepted
- **Context:** The story centers on a hero who lost his displays.
- **Decision:** Puff, coo, and turn change stats in combat. The hero starts
  with none and learns them during the game.
- **Reasons:** Ties progression directly to the story.
- **Consequences:** Displays need clear visuals, and some species must resist
  them so fights stay varied.

### 2026-11-07: Fight telemetry comes before other AI systems

- **Status:** Accepted
- **Context:** Reputation, the adaptive rival, and LLM townsfolk all need data
  about how the player fights.
- **Decision:** Build fight telemetry first and have the other systems read
  from it.
- **Reasons:** One shared data source keeps the AI systems consistent.
- **Consequences:** Telemetry needs a stable format that save files can store.

### 2026-11-07: Adaptive rival uses pattern tracking, not an LLM

- **Status:** Accepted
- **Context:** The rival must counter the player's habits in the rematch.
- **Decision:** Use pattern tracking and move prediction from telemetry.
- **Reasons:** Simpler, faster, and more predictable than an LLM.
- **Consequences:** The rival's counters must be visible so they feel fair.

### 2026-11-07: LLM townsfolk use open-source models with scripted fallbacks

- **Status:** Proposed
- **Context:** We want townsfolk who talk naturally and remember the player.
- **Decision:** Prototype with an open-source model and keep scripted dialogue
  as the default path.
- **Reasons:** Avoids hosted-model costs and keeps the game playable offline.
- **Consequences:** Model size, speed, and voice consistency need testing in
  Phase 7.

### 2026-11-07: Remove the squire companion for now

- **Status:** Accepted
- **Context:** The draft plan had an overeager young squire who follows the
  hero into exile.
- **Decision:** Remove the squire from the story, gameplay, and roadmap.
- **Reasons:** The concept did not feel right yet.
- **Consequences:** The hero travels alone. Cute moments and post-fight tips
  need another source if we want them. The idea can be revisited later.

### 2026-11-07: Learn the basics fast, master displays slowly

- **Status:** Proposed
- **Context:** If each town teaches one display, players wait too long to use
  the full combat system, which is what makes the game special.
- **Decision:** The first-town master teaches basic puff, coo, and turn within
  about the first hour. Displays then grow through mastery from use, learning
  by observing opponents, and town masters who teach variations and combos.
- **Reasons:** Players get the core mechanic early, the story keeps its
  learning arc (remembering, then understanding), and the number of towns can
  change freely.
- **Consequences:** Each town needs a variation or combo tied to its challenge.
  Mastery and observing need telemetry and enemy display variants.
