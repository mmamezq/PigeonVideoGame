# Technical Design

## Technology

- Game engine: Godot 4 (4.7.2)
- Programming language: GDScript
- Target platforms: macOS for prototyping; final platforms not decided
- Development tools: Godot editor, git/GitHub; input via gamepad with keyboard/mouse fallback

## Architecture

Describe the major game systems and how they communicate.

## Core systems

> **Combat (temporary note, 2026-11-15):** The combat prototype will use a simple action state machine per pigeon (idle/moving → warning → hit → recovery, plus dodge and hit-stun later). Hitboxes are active only during the hit phase and must match the animation. Timings, ranges and turn speeds live in an editable config, not hard-coded values. Enemy behavior is a small deterministic state machine. See `COMBAT_STATUS.md`.

- Player controller:
- Camera:
- Input:
- Audio:
- Saving and loading:
- User interface:

## Performance goals

Document frame-rate, resolution, memory, and loading-time targets.

## Testing and releases

Describe the testing strategy and how playable builds will be produced.

## Open technical questions

Track technical questions that still need investigation.
