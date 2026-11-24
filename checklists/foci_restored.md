# QA: Foci ported 1:1

Chapter id `foci_restored`, 8 checks. In game this is the FTB Quests chapter **QA: Foci ported 1:1**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:snowball`, `minecraft:egg`, `thaumicconcilium:bottle_of_clear_water`, `minecraft:fire_charge`

## 1. Reflection: experience for warp, free

Check id: `foci_restored.reflection`

**Steps**

1. You are already wearing the eldritch bracelet (Reflection) and have 30 levels. Hold V for a few seconds.

**Expect**

- [ ] 10 experience points a tick become 1 temporary warp a tick (more with potency).
- [ ] The bracelet's vis doesn't go down: Reflection refunds what it charges.

## 2. Warp Extraction controls

Check id: `foci_restored.warp_extraction`

**Steps**

1. You are already wearing the ring and an eldritch bracelet with Reflection and hold a wand with Warp Extraction; two cows stand ahead. Hold V (Reflection) first to build up temporary warp.
2. Then with the wand: sneak + cast, a charge appears; sneak + cast again near it, it vanishes. Cast and hold while looking at the cows; let go.

**Expect**

- [ ] Holding draws the charge you look at in front of you; letting go hurls it.
- [ ] Each creature it touches costs a point of temporary warp a tick; damage comes from permanent warp only.

## 3. Alchemist's Spree transmutes

Check id: `foci_restored.spree`

**Steps**

1. You are already wearing the ring, hold a wand with Alchemist's Spree, and have snowballs, eggs, clear water bottles and fire charges. Channel Spree, and throw the items straight up (or have a friend throw them at you).

**Expect**

- [ ] Snowball → frost shard along your aim; egg → a taint spider; clear water bottle → thick taint bottle; fire charge → explosive orb that only sets fires with Primal Essence.

## 4. Taint Animation

Check id: `foci_restored.taint_animation`

**Steps**

1. You hold a wand with Taint Animation, in front of a strip of taint soil with fibres and flux gas, and a cow beyond it. Channel Taint Animation looking at the cow.
2. Tainted mobs for the sneak part are not staged: bring some (taint crawlers, spawn eggs) if you want to test it.

**Expect**

- [ ] Every half second a fibre wears down a stage (or vanishes) into a taintacle, or gas becomes a swarm, aimed at what you look at.
- [ ] Sneaking: tainted mobs within 16 go for your target, with Strength from your permanent warp (up to 200) at potency.

## 5. Ring of Blustering Light

Check id: `foci_restored.ring`

**Steps**

1. You hold the ring, a wand with Spotlight, loose Alchemist's Spree and Warp Extraction foci, and a shield. Cast each focus (socket the loose ones into the wand) with and without the ring worn (Curios ring slot); hold the shield in the off hand.

**Expect**

- [ ] The ring shows in the slot and fills a hotbar wand with vis, and shields; the three foci refuse without it (action-bar message, no vis spent).

## 6. Ethereal Manipulator

Check id: `foci_restored.ethereal`

**Steps**

1. You hold a wand with the Ethereal Manipulator, a bow and arrows; a diamond lies on the ground ahead. Channel the focus at the diamond, then at an arrow you shoot; scroll the mouse wheel while channelling.

**Expect**

- [ ] It holds the item or projectile in front of you; the wheel sets the distance 1 to 16 and does not change your hotbar slot while channelling.

## 7. Scribing on a second player

Check id: `foci_restored.scribing`

**Steps**

1. You hold a wand with the Scribing focus. This check needs a second player (open to LAN) wearing runic gear: channel at them.

**Expect**

- [ ] Their Thaumaturge runic shield refills, never past what their gear grants; runes stream from you to them.

## 8. Foundation foci: cost and fire rate

Check id: `foci_restored.presets`

**Steps**

1. You hold four wands: Signal, Impulse, Positive Burst and Cooling. Cast each; watch the vis bar and the Cooling flurry's fire rate.
2. Open the research book and check the Thaumic Concilium tab shows these four entries and their parts (staging has already granted them, so the unlock order is not tested here).

**Expect**

- [ ] Each focus costs a sensible amount of vis (report any that feel off); the flurry fires about every 4 + complexity/8 ticks; the Thaumic Concilium tab opens after Base Auromancy and gates its parts.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `foci_restored`).
