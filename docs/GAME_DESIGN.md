# Game Design

> [!NOTE]
> Draft v2 (2026-11-07). Story, characters, and towns live in
> [STORY_AND_WORLD.md](STORY_AND_WORLD.md). Items marked *(proposed)* are new
> suggestions that still need agreement before they become decisions.

## High concept

A cute, heartfelt isometric RPG about a disgraced Modena pigeon knight. After
losing his place in the roost, he travels from town to town, fights other
birds, relearns the lost art of pigeon displays (puffing, cooing, turning), and
earns a rematch with the rival who beat him.

- Setting: a medieval Emilia-Romagna populated by animals, starting in Modena
- View: isometric
- Genre: story-driven RPG with real-time bird-vs-bird combat
- Tone: cute and heartfelt, with plenty of humor

## Player experience

- Early game: the player feels the sting of the hero's fall and how outmatched
  he is without displays.
- First hour: the player regains all three basic displays and gets to play
  with the full combat system right away.
- Mid game: each variation, combo, and mastery level feels like a real power
  spike and opens new ways to win fights.
- Late game: the player sees their own habits reflected back at them by the
  world and the rival, and wins by fighting with attention instead of habit.

## Design pillars

1. Displays are power. Puffing, cooing, and turning are core combat mechanics,
   not decoration.
2. Birds fight birds. All combat is bird vs. bird, so displays always make
   sense. Not every bird fights, but every fighter is a bird.
3. Fights have meaning. Every fight connects to the story, a quest, or the
   hero's growth.
4. The world remembers you. Towns and rivals react to how you play.
5. Pay attention *(proposed)*. The hero lost because he stopped paying
   attention. Combat rewards reading opponents, and the AI systems read the
   player in return. Story, mechanics, and AI all share this theme.

## Core gameplay loop

1. Arrive in a town and hear gossip about its fighters. Gossip about you starts
   small and grows as you fight more (see below).
2. Explore, talk to townsfolk, and take quests.
3. Fight in the arena, in quests, or by provoking birds in the world.
4. Earn reputation, items, and the right to train with the local master.
5. Learn a display variation or combo, then use it in harder fights.
6. Beat the town champion and travel to the next town, where your reputation
   arrives before you do.

### Gossip grows with your story *(proposed)*

The amount and detail of gossip about the hero scales with how many fights he
has had. Gossip should feel earned.

| Stage      | What the towns know                 | Example gossip                                     |
|------------|-------------------------------------|----------------------------------------------------|
| Early game | Only the fall in Modena             | "Isn't that the champion who got spooked?"         |
| Mid game   | His record and a few habits         | "He's won six in a row. Likes to open with a coo." |
| Late game  | His full style, legends, and quests | "Watch his turn. He beat the Rimini gull with it." |

- Gossip about the town's own fighters and events is always available, so
  early towns still feel alive.
- Local fighters only start preparing for the hero's habits once there is
  enough fight history to talk about.
- Hearing your own habits in gossip is an early hint that the rival is
  watching too.

## Combat

Combat is real-time, one bird against one or more birds, in a small isometric
arena. The final move list is still to be defined with the combat developer.

### Stats *(proposed)*

| Stat    | What it does                                                         |
|---------|----------------------------------------------------------------------|
| Health  | When it hits zero, the bird is knocked out (ruffled) and loses       |
| Stamina | Spent on attacks, dodges, and displays; recovers over time           |
| Attack  | How much damage pecks and wing slaps deal                            |
| Nerve   | Courage. When it breaks, the bird is spooked and stunned or flees    |
| Focus   | Accuracy and how long the timing windows are for dodges and counters |

Breaking Nerve gives a second, non-violent way to win, which suits the cute
tone. It also explains the opening duel: the hero is not beaten up, he gets
spooked.

### Basic moves

- Peck: fast, light attack
- Wing slap: slower, stronger attack
- Hop or flutter: dodge and reposition

### Displays

The hero starts with no displays after his fall. The rule for learning them is
*learn the basics fast, master them slowly* (proposed).

| Display | Real pigeon behavior        | Proposed effect                                         |
|---------|-----------------------------|---------------------------------------------------------|
| Puff    | Inflating the chest         | Lowers opponent Nerve; briefly raises your defense      |
| Coo     | Cooing at a rival           | Lowers opponent Focus; can taunt them into attacking    |
| Turn    | Spinning and bowing         | Raises your Focus; a well-timed turn counters an attack |

- Displays cost stamina and leave a short opening, so spamming them is risky.
- Displays work less well against some species, so the hero also needs good
  basic moves and positioning.

### Learning displays *(proposed)*

The hero learns displays in three ways, so players get the full combat system
early without the game losing its sense of growth.

1. Basics in the first town. One master teaches basic puff, coo, and turn
   through short training fights, all within roughly the first hour.
2. Mastery through fighting. Each display levels up as you use it well (for
   example, longer effects or lower stamina cost). Mastery data comes from
   fight telemetry.
3. Learning by observing. When an opponent uses a special display on you,
   study it by dodging it or holding your Nerve, then earn it yourself. This
   ties to the "Pay attention" pillar.

Later towns teach variations and combos rather than new basics. Each one
answers that town's challenge or local species:

| Town (draft) | Master teaches                                               |
|--------------|--------------------------------------------------------------|
| Bologna      | Scholar's Coo: lowers Focus more and reveals weak spots      |
| Rimini       | Storm Puff: works on big birds like seagulls                 |
| Ferrara      | Tournament Turn: a counter that knocks enemies back          |
| Ravenna      | A combo: Puff into Turn                                      |
| San Marino   | A display that finally works on the falcon                   |

Because towns add depth instead of gating core moves, the number of towns can
change without breaking the combat.

### Where fights happen

1. Arena fights: each town has a ladder of challengers.
2. Quest fights: fights during main and side quests.
3. Provoked fights: the player can provoke certain birds in the world (for
   example, puffing at a rooster to start a fight).
4. Story duels: key fights with town champions and the final rival.

### Opponent species

Each species has its own fighting style and reacts to displays in its own way.

| Species     | Style                                    | Reaction to displays                  |
|-------------|------------------------------------------|---------------------------------------|
| Pigeons     | Varied styles; display duelists          | Fully affected, and display back      |
| Sparrows    | A swarming flock; weak one by one        | Mostly ignore intimidation            |
| Hummingbird | Tiny, very fast, hit-and-run, fearless   | Doesn't care how big you look         |
| Chickens    | Sturdy, stubborn; roosters display too   | Roosters start display-offs           |
| Seagull     | Big coastal bully *(proposed)*           | Puff barely works; coo makes it angry |
| Magpie      | Trickster that steals items *(proposed)* | Distracted by shiny things            |
| Falcon      | Feared predator boss *(proposed)*        | Immune to displays; outsmart it       |

> [!TIP]
> Hummingbirds do not live in Europe. If you want to keep things grounded, a
> wren, swift, or goldcrest could fill the tiny-and-fearless role. A
> hummingbird could also work as a far-traveled oddity.

## Progression

- Displays: learned from town masters, then upgraded
- Reputation: grows with wins, quests, and choices, and changes how towns treat
  you
- Items *(proposed)*: simple gear such as feather charms or grain snacks bought
  from pig merchants

## Win and loss conditions

- A fight is won by knocking out the opponent or breaking their Nerve.
- Losing an arena or provoked fight costs reputation and some coins, not a
  game over *(proposed)*.
- Losing a story duel lets the player retry, possibly with a hint
  *(proposed)*.
- The game is complete after the final rematch in Modena.

## Open gameplay questions

1. What is the full list of combat moves and stats?
2. How does provoking work: which birds, and which actions start a fight?
3. Is multi-opponent combat (sparrow flocks) in scope for the first versions?
4. Keep the hummingbird, or swap it for a European bird?
5. Should losing fights have any lasting cost?
