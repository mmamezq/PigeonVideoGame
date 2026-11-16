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

> **Combat (temporary note, 2026-11-15):** No combat decisions are logged here yet. The working direction is deliberate one-on-one duels with twin-stick movement and facing, and readable warning → hit → recovery attacks, starting with a wing slap. These become logged decisions once the prototype confirms them. See `COMBAT_STATUS.md`.

### 2026-11-15: Engine is Godot 4 with GDScript

- **Status:** Accepted
- **Context:** No code could be written until an engine was chosen. The first milestone is a small 2D combat prototype with gamepad and keyboard/mouse input.
- **Decision:** Use Godot 4 (installed version 4.7.2) and GDScript. Prototypes go in `prototypes/`, one Godot project per experiment.
- **Reasons:** Free and lightweight, strong 2D tools, built-in input mapping for gamepad and keyboard/mouse, fast iteration, and a text-based project format that diffs well in git.
- **Consequences:** Everyone working on the game needs Godot 4.x installed. Tuning values should live in exported variables or resource files rather than hard-coded constants.
