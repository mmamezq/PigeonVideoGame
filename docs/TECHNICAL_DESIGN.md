# Technical Design

## Technology

- Game engine: to decide
- Programming language: depends on the engine
- Target platforms: to decide (PC first is a reasonable starting point)
- Development tools: Git and GitHub

## Architecture

Fight telemetry is the foundation. Every fight writes events to a log, and the
reputation, gossip, adaptive rival, and LLM townsfolk systems all read from it.

```text
Combat -> Fight telemetry -> Player profile (habits, record, choices)
                                  |-> Reputation and gossip
                                  |-> Adaptive rival
                                  |-> LLM townsfolk memory facts
```

## Core systems

- Player controller: isometric movement in towns; real-time controls in fights
- Camera: fixed isometric camera; tighter framing in arenas
- Input: keyboard and mouse plus gamepad
- Audio: coos and wing flaps double as combat feedback
- Saving and loading: must persist the telemetry-based player profile
- User interface: stat bars for Health, Stamina, Nerve, and Focus; display
  cooldowns

## AI systems

The AI systems are built in priority order. Each one depends on the ones
before it.

### Priority 1: Fight telemetry

- Log what the player does in every fight: moves used, order, timing, wins and
  losses, and opponent types.
- Summarize raw logs into a player profile, such as "opens with a coo 70% of
  the time" or "always turns left".
- Keep the event format simple and versioned so old saves keep working.

### Priority 2: Reputation and gossip

- Towns hear about your fighting style and choices before you arrive.
- Gossip scales with fight history *(proposed)*. Early on, towns only know
  about the fall in Modena. As fights pile up, gossip covers the hero's
  record, then his habits, then his notable wins and quests.
- Gate each gossip tier on telemetry thresholds (for example, number of
  fights or how strong a habit is), not on which town you are in.
- Local fighters prepare for your habits ("they say you always open with a
  coo") only after a habit is well established.
- Townsfolk mention your record and reputation.

### Priority 3: Adaptive rival

- The rival tracks the player's habits across the whole game.
- In the final rematch, the rival counters your most common patterns.
- Approach: pattern tracking and move prediction from telemetry, such as
  frequency counts and n-grams over move sequences. No LLM is needed.
- Fairness: show the rival reacting to your habits (for example, he
  sidesteps your favorite opener), so players understand why he is winning
  and know to change their approach.

### Priority 4: LLM townsfolk

- Animal townsfolk talk naturally and remember your actions.
- Use an open-source model. Candidates to evaluate include the Llama, Mistral,
  Qwen, Gemma, and Phi families, run locally through llama.cpp or Ollama.
- Guardrails:
  - A character sheet per NPC (personality, role, speech style, what they
    know)
  - A small set of memory facts per NPC (your wins, quests, choices)
  - Topic limits so NPCs stay in the world
  - Scripted fallback lines when output fails or goes off-character
- Questions to evaluate: model size vs. speed, local vs. hosted, cost, and
  consistency of character voice.

> [!IMPORTANT]
> Scripted dialogue should always be the default path. The game must be fully
> playable with the LLM turned off, so a slow machine or a bad model output
> never blocks the story.

### Later ideas

- Species behavior AI: flocking sparrows, hit-and-run hummingbird
- Personality-driven fighters: aggression, caution, and vanity settings

## Performance goals

To define after the engine choice. LLM dialogue must not stall gameplay;
generate replies asynchronously and show a scripted line while waiting.

## Testing and releases

To define after the engine choice. Telemetry logs can also help with balance
testing.

## Open technical questions

1. Which engine, and which language?
2. Which target platforms?
3. Which local model size runs well enough on target hardware?
4. Should the LLM be bundled with the game or optional?
5. How is telemetry stored in save files?
