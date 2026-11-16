# Combat Status

> **Temporary document.** This is a snapshot of where combat design stands while we prototype. It will change often and may be folded into `GAME_DESIGN.md` once combat is proven. Last updated: 2026-11-15.

## Where we are

- **Stage:** Planning is done; no combat code exists yet.
- **Engine:** Godot 4 (4.7.2) with GDScript, installed and verified. See `DECISIONS.md`.
- **Next build:** A small 2D combat prototype in `prototypes/wing-telegraph/`, covering only Phases 0–2 below.
- **Blocked on:** Four proposed prototype changes (listed at the bottom) need a yes/no before the coder starts.

## The combat idea in short

The player is a round, armored Modena pigeon. Fights are deliberate one-on-one duels, closer to Dark Souls than to a fast button-mashing game: committed attacks, readable warning animations, positioning and punishing mistakes.

What should make it feel different:

1. **Real pigeon fighting moves:** wing slap, beak peck, jump kick.
2. **Twin-stick control:** the left stick moves, the right stick turns the body. You can strafe or back away while facing your opponent, and which way your body and wings face matters for attacking and defending.
3. **Later, dominance displays** (chest puff, coo, spinning in place) that change how the opponent fights. These come only after plain physical combat is proven fun.

The guiding rule: find out what feels good to play before building art, progression, story or AI opponents.

## Decided so far

- One-on-one (or very small) deliberate duels, not crowds.
- Start in a plain 2D test arena with simple pigeon-shaped placeholders and moving wings. No final art needed.
- Left stick moves, right stick sets facing, independently. Keyboard and mouse must also work.
- Every attack has three visible phases: **warning (startup) → hit (active) → recovery**. Damage only happens during the hit phase.
- Start with the **wing slap** only.
- Attacking can leave you open. The working idea is that an extended wing exposes your flank while it's out, not a permanent penalty for facing sideways.
- Enemies follow the same rules as the player.
- "Spinning" as a dominance display means turning in place around its own axis, not circling the opponent.

## The first experiment: can you read a wing slap coming?

Idea from real pigeon behavior: before a wing strike, the pigeon lifts its **far** wing, then strikes with the **near** wing. The question is whether a player can read that from the animation alone, without text or colored warnings.

Three warning styles to compare:

| Variant | Warning cue |
|---|---|
| A | Far wing lifts only |
| B | Far wing lifts + body braces (starting default) |
| C | B + striking wing visibly draws back |

Starting timings, all adjustable: warning about 0.7 s, hit 0.1–0.2 s, recovery 0.4–0.7 s.

## Prototype phases

| Phase | What gets built | Status |
|---|---|---|
| 0 | Arena with two labeled pigeons, facing arrows, debug toggle, reset | Next |
| 1 | Player movement and independent facing (gamepad + keyboard/mouse) | Next |
| 2 | Enemy wing slap with warning variants A/B/C and optional debug text | Next |
| 3 | Dodge, hits, health, hit/miss feedback | Later |
| 4 | Player wing slap, attack angles, exposed flank while attacking | Later |
| 5 | One full duel: maybe peck/kick, simple enemy behavior | Later |
| 6 | Playtest with two people and decide whether the core is worth keeping | Later |
| 7 | One dominance display (chest puff), only if Phase 6 passes | Later |

Not part of this prototype: dominance displays, progression, gear, story, multiple enemies, AI/LLM opponents.

## Open questions

- Does the player pick which wing attacks, or do facing and the opponent's position decide it?
- How much protection does the front of the body give, and what changes while a wing is extended?
- Instant turning or a capped turn speed?
- Top-down or angled (3/4) camera: which makes a raised wing readable?
- Is a separate parry needed, or do facing and dodging give enough defense?
- Can the enemy turn to track the player without making circle-strafing an easy win?

## Proposed changes to the prototype (awaiting decision)

1. **Show wing height.** From straight above, a raised wing barely changes shape. Proposal: the raised wing shifts up the screen, grows a little and casts a shadow.
2. **Rule for which wing strikes.** Proposal: the wing on the side the opponent is on; if the opponent is straight ahead, a fixed default wing.
3. **Turn speed as a setting.** Proposal: cap turning speed with an adjustable value, so an exposed flank can actually matter.
4. **Predict button.** Proposal: press when you think the strike is coming; the game logs how early or late you were, per warning variant, so A/B/C can be compared with numbers.
