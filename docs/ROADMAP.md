# Roadmap

We build the game in small stages. Each phase ends with something playable or
testable.

## Phase 0: Foundation

- Set up the repo, project structure, and engine.
- Agree on the design docs as the shared plan.
- Decide the engine and the art style.

## Phase 1: Core combat prototype

- Build a pigeon-vs-pigeon fight in a test arena.
- Add basic attacks plus puff, coo, and turn.
- Make displays change stats.
- Goal: the fighting feels fun.

## Phase 2: Opening duel

- Script the opening fight, where the rival's displays drop the hero's stats.
- The hero loses and is exiled.
- Goal: the story and tutorial moment works.

## Phase 3: Fight telemetry

- Log player actions in every fight.
- Build a simple player profile from the logs.
- Goal: data is ready for the AI systems.

## Phase 4: First town (vertical slice)

- Build one isometric town hub.
- Add a few animal townsfolk with scripted dialogue.
- Add a local arena with 3 to 4 challengers, including one non-pigeon species.
- Add one quest fight and one provoked fight.
- Add the first-town master who teaches basic puff, coo, and turn.
- Add display mastery that levels up with use.

## Phase 5: More species

- Add sparrows, the hummingbird (or a replacement), and chickens with distinct
  behaviors.
- Add species-specific reactions to displays.
- Add learning by observing: study opponents' special displays to earn them.

## Phase 6: Reputation and gossip

- Build reputation from telemetry.
- Scale gossip with fight history, from the fall in Modena to the hero's
  habits and notable wins.
- Make townsfolk and fighters react to your style.

## Phase 7: LLM townsfolk prototype

- Pick and test an open-source model.
- Add character sheets, memory facts, guardrails, and fallbacks.
- Start with 1 to 2 NPCs.

## Phase 8: Adaptive rival

- The rival learns from the full playthrough.
- The final rematch counters your habits.

## Phase 9: Full game

- Add more towns, quests, and story, with masters who teach display
  variations and combos.
- Build the ending.
- Polish, balance, and playtest.

> [!TIP]
> Consider a rough adaptive rival test right after Phase 3. Even a simple
> "counter the player's favorite opener" rule will show early whether the
> rematch idea feels fair and fun.
