# QA: Monitors and machines (6b)

Chapter id `phase_6b`, 17 checks. In game this is the FTB Quests chapter **QA: Monitors and machines (6b)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:redstone_block`

## 1. Polished infusion without a draw

Check id: `phase_6b.polished_fail`

**Steps**

1. You stand in front of an infusion altar for the Cooling Focus: a focus on the centre pedestal, a torch on two of the ring pedestals. A Cooling Focus is in your inventory, and creative jars of every aspect stand behind the altar.
2. Look up the Cooling Focus in the book (Thaumonomicon key): its recipe page ends with the Polished Infusion line. Hover the Cooling Focus: the tooltip shows the requirement.
3. Start the infusion on the matrix and let it finish without channelling a crystal.

**Expect**

- [ ] The infusion completes, the pedestal ends up empty and a purple message says it unravelled. Nothing is left over and nothing duplicates.

<sub>Already covered by automated pack tests: `polishment_lookup`, `polishment_gate`</sub>

## 2. Polished infusion with a draw

Check id: `phase_6b.polished_ok`

**Steps**

1. You stand in front of the Cooling Focus infusion altar (creative jars of every aspect stand behind it), with a destabilized crystal charged with 100 aversio two blocks to your right, and the Vis Conductor wand in your hand.
2. Start the infusion, aim the Vis Conductor at the crystal and keep channelling until it has given up 64 or more.
3. Keep channelling while the infusion finishes.

**Expect**

- [ ] The crystal vanishes with a shock sound, you swing, a lightning arc runs from you to the matrix and the Cooling Focus appears on the pedestal. Letting go afterwards does nothing.

<sub>Already covered by automated pack tests: `polishment_gate`</sub>

## 3. Xylography

Check id: `phase_6b.xylography`

**Steps**

1. You stand in front of a crafting table with a charged wand in your hand.
2. Put the wand alone in the crafting grid and take the result.

**Expect**

- [ ] The wand now says it is signed with your name.

<sub>Already covered by automated pack tests: `xylography_signs_wand`</sub>

## 4. Astral Monitor: icon, pose, gems, tooltip

Check id: `phase_6b.monitor`

**Steps**

1. You stand in front of a crafting table with a wand and an Astral Monitor in your inventory.
2. Craft the wand alone in the grid to sign it. Look at the Astral Monitor in the inventory, the creative tab and the research book: is its icon drawn (not a missing texture)?
3. Hold it in the main hand, then the off hand: do both hands hold it up two-handed, steady, in first and third person?
4. Sneak and use it, put the signed wand in the slot, close it. Watch the gems on the frame for ten seconds, then hover the item.
5. Try with another player holding the signed wand too (LAN).

**Expect**

- [ ] The icon is the monitor with its gems.
- [ ] The two-handed pose looks right; nothing clips the face.
- [ ] The frame gems cycle through their colours; the tooltip says "Watching" and the signed player's name.
- [ ] Constellation glyphs hover over the screen showing that player's health (and mana with Botania); the slot cannot be emptied by clicking the monitor.

## 5. Lithographer: the full operation

Check id: `phase_6b.lithographer`

**Steps**

1. You stand in front of the bed pattern, already built: bed, thaumium block on its head, gold blocks either side of both, an alchemical construct on top. Two charged wands and two Astral Monitors are in your inventory, a crafting table is on your right and a sensus crystal with 100 floats above the construct.
2. Strike the construct with a charged wand (try both axes by rebuilding if you wish).
3. Craft each wand alone to sign it and put each in a monitor, then put both monitors in the Lithographer.
4. Put the Vis Condenser on top of the Lithographer (under the crystal), sleep in the bed and power the machine with the redstone block.

**Expect**

- [ ] The thaumium block becomes the Lithographer; the screen opens and holds four monitors.
- [ ] After the pulse the HUD appears and the crystal loses 32.

<sub>Already covered by automated pack tests: `lithographer_build`</sub>

## 6. Quicksilver Reactor: merging

Check id: `phase_6b.reactor`

**Steps**

1. You stand between a boiling crucible full of water (left) and a Quicksilver Reactor (right), 6 blocks apart.
2. Throw quicksilver into the reactor; give the crucible aspects whose last two combine (throw in the kit items, for example the parts of a compound).
3. Power it with the redstone block, then pause it with a lever; stand a creature in the mercury; add a comparator.

**Expect**

- [ ] Every second a flow of mercury runs from the reactor to the crucible and the last two aspects become one of their compound; a lever or redstone block pauses it; creatures inside the mercury are burned; the comparator reads the reactor.

<sub>Already covered by automated pack tests: `quicksilver_reactor_merge`</sub>

## 7. Polished items: tooltip and book line

Check id: `phase_6b.polished_tooltip`

**Steps**

1. A Cooling Focus and a Tight Belt are in your inventory.
2. Look at them in the inventory and at their recipes in the research book.

**Expect**

- [ ] The item shows the polished tooltip and the book page shows the polished line.

<sub>Already covered by automated pack tests: `polishment_lookup`</sub>

## 8. Lithograph HUD: readability and eye drops

Check id: `phase_6b.lithograph_hud`

**Steps**

1. You are already lithographed, watching yourself. Read the glyphs: health, then in Botania mana; try a dark cave and a bright day (use /time set to switch).
2. Use Coagulating Eye Drops twice.

**Expect**

- [ ] The glyphs are readable against bright and dark scenes and do not cover the crosshair.
- [ ] The drops switch the HUD off, then on again, costing 1 health each time.

## 9. Quicksilver Elemental

Check id: `phase_6b.elemental`

**Steps**

1. You stand beside a Quicksilver Elemental (it stands still) and a boiling crucible of water on the right.
2. Hit the elemental with fire, lava and a sword; watch its hitbox as it shrinks.
3. Throw the quicksilver from your inventory into the crucible.

**Expect**

- [ ] It is immune to what the original lists, its hitbox shrinks with its size, and the crucible becomes a Quicksilver Reactor.

<sub>Already covered by automated pack tests: `quicksilver_reactor_merge`</sub>

## 10. Polishment Device removes a rift

Check id: `phase_6b.device_rift`

**Steps**

1. A rift hangs in the air ahead of you and the Polishment Device is in your hand. Look at the rift and use the device.

**Expect**

- [ ] The rift disappears at once (no taint, no event); the device is not consumed.

## 11. Drum strike and sound

Check id: `phase_6b.drum_strike`

**Steps**

1. Both drums and the Void Bracelet are in your inventory.
2. Hold use on the Thaumaturge's Drum, then the Warped Drum, in the main hand; watch the strike against the beat.
3. Move a drum to the off hand (main hand empty) and hold use; then hold the Void Bracelet in the main hand and hold use again.

**Expect**

- [ ] The arm strikes in time with the bass-drum sound, in first and third person; the off hand strikes with the off arm (the bracelet's band shows on the striking wrist).

<sub>Already covered by automated pack tests: `drum_offhand`</sub>

## 12. Drumming left-handed

Check id: `phase_6b.drum_left`

**Steps**

1. Both drums and the Void Bracelet are in your inventory.
2. In Options > Skin Customization set the main arm to Left. Repeat the strike in the main hand, the off hand, and the off hand with a bracelet.

**Expect**

- [ ] Everything is mirrored: the same strike and sound, the right arm for the off hand, no arm clipping through the drum.

## 13. Drum summon rates

Check id: `phase_6b.drum_rates`

**Steps**

1. You stand on open ground with both drums.
2. Play the Thaumaturge's Drum for a minute, then the Warped Drum; count what appears.

**Expect**

- [ ] Roughly one wisp of a random primal every 1.5 seconds (up to 16 within 64 blocks); the Warped Drum calls a harmless mind spider every half second (up to 16 within 32).

<sub>Already covered by automated pack tests: `drum_offhand`</sub>

## 14. Stray wisps without a drum

Check id: `phase_6b.stray_wisps`

**Steps**

1. Nothing is staged: this check needs real terrain, so you stay where you are.
2. Without any drum, play for five minutes in an overworld forest, then a cave. Note any wisps near you and what the area is.

**Expect**

- [ ] No wisps follow you around. If some do, report where: the pack test found 16 wisps near its test player (source unknown).

<sub>Already covered by automated pack tests: `drum_offhand`</sub>

## 15. Drum stance: silent versus played

Check id: `phase_6b.stance_cast`

**Steps**

1. You stand with three cows in a line ahead of you at 2, 4 and 6 blocks (they stand still). The Void Bracelet with the QA Aura > Frost focus is in slot 1 and a drum in slot 2.
2. Put the bracelet in the main hand and the drum in the off hand. Press V with the drum held silent; note the vis and which cows are frozen.
3. Hold use on the drum so it plays, and press V again; compare.

**Expect**

- [ ] Silent: a plain wand's vis cost and cooldown, an aura of 3 blocks. Played: 1.5 times the vis and the aura reaches 1.5 times as far (4.5 blocks). V never interrupts the drumming.

<sub>Already covered by automated pack tests: `bracelet_drum_stance`</sub>

## 16. Drum stance: aimed spells refused

Check id: `phase_6b.stance_refused`

**Steps**

1. You stand with the Signal focus bracelet in slot 1 and a drum in slot 2, a cow six blocks ahead.
2. In the stance (bracelet main hand, drum off hand) press V, drum silent then played.

**Expect**

- [ ] Refused: the action-bar message "You cannot aim while drumming", the fail sound, no vis spent, no cooldown, and the drumming goes on.

<sub>Already covered by automated pack tests: `bracelet_drum_stance`</sub>

## 17. Drum stance: Taint Animation and Positive Burst

Check id: `phase_6b.stance_foci`

**Steps**

1. You stand with the Taint Animation bracelet in slot 1, a drum in slot 2 and a loose Positive Burst focus (slot 3). A zombie stands still five blocks behind you.
2. With the drum in the off hand press and hold V (a taint area with a tainted creature is not staged: go to one if you want to see raised creatures; command mode if you set it).
3. Then socket the Positive Burst focus in the bracelet with another player nearby, facing a different way each time.

**Expect**

- [ ] Taint Animation pulses (never picking what you look at: command goes for the nearest foe, raised creatures choose their own targets). Positive Burst releases its orbs straight up whichever way you face, and they find the other player.

<sub>Already covered by automated pack tests: `bracelet_drum_taint`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_6b`).
