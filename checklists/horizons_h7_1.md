# QA: Horizons H7-1: the planar rift core

Chapter id `horizons_h7_1`, 8 checks. In game this is the FTB Quests chapter **QA: Horizons H7-1: the planar rift core**; each check there has a green "Set up this check" line that builds its test site.

## 1. The rift: look and sound

Check id: `horizons_h7_1.rift_look`

**Steps**

1. You stand on an open pad with the creative Planar Vortex in slot 1 and the ordinary one in slot 2.
2. Place the creative one a few blocks ahead and stand back. Then place the ordinary one beside it (it grows for about 2.5 seconds, then turns hungry: leave the area).

**Expect**

- [ ] The creative rift is a black disc with a bright rim and a slowly turning halo, calm blue, with a low steady hum every three seconds; the ordinary one flickers red once it is hungry; both give off full light and cannot be walked into or broken in survival.

<sub>Already covered by automated pack tests: `recipes_and_research_are_loaded`</sub>

## 2. A hungry rift

Check id: `horizons_h7_1.hungry_pull`

**Steps**

1. You stand ten or so blocks behind a patch of cobblestone with a few apples dropped beyond it, holding the ordinary Planar Vortex.
2. Walk up, place the vortex against the cobblestone, then back off about ten blocks and watch for about twenty seconds. See what is left.

**Expect**

- [ ] Everything within fifteen blocks is pulled toward it, harder the closer it is; anything touching it is hurt; nearby soft blocks (dirt, stone, wood) are torn out and drop items; after about twenty seconds with no attenuator it collapses in a burst and is gone.

<sub>Already covered by automated pack tests: `rift_numbers_are_the_originals`, `rift_grows_eats_and_collapses_on_time`, `hungry_rift_pulls_hurts_and_spares_creative_players`</sub>

## 3. Six attenuators hold it

Check id: `horizons_h7_1.six_attenuators`

**Steps**

1. You stand in front of an ordinary Planar Vortex floating head height, ringed by six powered Vortex Attenuators (one on each side, a redstone block behind each).
2. Watch the beams and that the rift stays calm. Break one attenuator (it should hunger again; rebuild or restage). Throw a stone into the rift, then right-click the rift with the wand.

**Expect**

- [ ] Each powered attenuator shows a pale-blue beam to the rift; with six the pulling stops and the rift stays open indefinitely; with five it is hungry again; unpowering or breaking one lets it hunger. A wand click on the rift does nothing when nothing is stored (void crafting arrives in a later cycle).

<sub>Already covered by automated pack tests: `six_attenuators_hold_a_rift_stable`, `dispatcher_claims_items_only_when_stable`, `wand_click_pops_stored_items_one_at_a_time`</sub>

## 4. An attenuator calms a hungry node

Check id: `horizons_h7_1.attenuator_node`

**Steps**

1. You stand before a hungry node eight blocks ahead and a stone block three blocks ahead in line with it. Your hotbar holds two attenuators and two redstone blocks.
2. Place an attenuator on the stone block's far (node-facing) side so its muzzle faces the node, then power it with a redstone block beside it. Remove the power, then break it, and watch the node.

**Expect**

- [ ] The node stops pulling while the beam holds it and the beam is visible; when the attenuator is powered off, broken, or its chunk unloads, the node is hungry again. Two attenuators on one node keep it calm until both are gone.

<sub>Already covered by automated pack tests: `attenuator_holds_a_hungry_node_normal_and_gives_it_back`</sub>

## 5. Transduction Amplifier: bolts and flux

Check id: `horizons_h7_1.amplifier`

**Steps**

1. You stand in front of an energized node floating just above the ground, with two cows nearby. Your hotbar holds three transduction amplifiers and three redstone blocks.
2. Fix one amplifier to a side of the node and power it with a redstone block. Add a second, then a third, with free air around and the cows in view.

**Expect**

- [ ] With one amplifier the node's vis total and refill rise by ten per aspect; with two, bolts of sparks hit living things within ten blocks about every 2.5 seconds; with three, now and then flux gas or goo appears in the air around it; removing an amplifier takes its ten back.

<sub>Already covered by automated pack tests: `amplifier_boost_follows_the_signal_and_the_block`</sub>

## 6. The fourth amplifier opens a rift

Check id: `horizons_h7_1.fourth_amplifier`

**Steps**

1. You stand eight blocks back from an energized node with four unpowered amplifiers on its four sides and a bedrock block two blocks above it. Your hotbar holds four redstone blocks.
2. Power the amplifiers one at a time with the redstone blocks (place each against the back of an amplifier, from a distance), the fourth last, then watch.

**Expect**

- [ ] The node turns into a planar vortex about a second after the fourth is powered; the four amplifiers stay in place while the rift grows (about two and a half seconds), then it eats every block in the 5x5x5 around it at once, bedrock included (the amplifiers, the transducer above), and is hungry until held.

<sub>Already covered by automated pack tests: `fourth_amplifier_makes_the_rift_with_the_compound_aspects`</sub>

## 7. Recipes and research

Check id: `horizons_h7_1.conduit_recipes`

**Steps**

1. You stand in front of an arcane workbench with a full wand, void ingots, an ender pearl, air wisp essence and five crystals of each primal on your hotbar (enough for a Planar Conduit).
2. Open the Horizons tab: Planar Theory, Transduction Amplifier, Vortex Attenuation and New Horizons are all done. Craft the Planar Conduit at the workbench. (The amplifier and attenuator recipes need more parts: read their pages.)

**Expect**

- [ ] All four entries show at their original cells with the original text; the conduit and the amplifier craft with the listed vis and crystals; the attenuator infuses around a Node Stabilizer; New Horizons gives warp 3.

<sub>Already covered by automated pack tests: `recipes_and_research_are_loaded`</sub>

## 8. Wisp essence

Check id: `horizons_h7_1.wisp_essence`

**Steps**

1. You stand in front of a wisp hanging in the air five blocks ahead (it will not move) and an arcane workbench. Your hotbar holds two wisp spawn eggs, an Ethereal Shard and a sword.
2. Kill the wisp and look at what it drops. Open the Horizons creative tab and find the Ethereal Essence of each aspect.
3. Craft the Planar Conduit at the workbench with any kind of essence on the four edges (you need the other parts: or just try an essence in the grid). Place the Ethereal Shard and right-click it with a stack of essence of one aspect, then break the shard.

**Expect**

- [ ] The wisp drops one Ethereal Essence of its own aspect (and no essentia crystal); every essence is a grey wisp tinted by its aspect colour, named with the aspect.
- [ ] The conduit accepts any essence and not an essentia crystal. The shard takes the whole stack (4 capacity per essence) and not crystals; breaking it drops the essences back (capacity / 4 per aspect).

<sub>Already covered by automated pack tests: `a_wisp_drops_wisp_essence_of_its_aspect`, `wisp_essence_is_tagged_and_the_conduit_and_shard_take_it`, `ethereal_shard_capacity_tapping_and_drops`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_1`).
