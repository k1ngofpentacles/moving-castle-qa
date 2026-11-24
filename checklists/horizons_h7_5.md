# QA: Horizons H7-5: void-craft products

Chapter id `horizons_h7_5`, 6 checks. In game this is the FTB Quests chapter **QA: Horizons H7-5: void-craft products**; each check there has a green "Set up this check" line that builds its test site.

## 1. Void putty out of a rift, and a repair

Check id: `horizons_h7_5.putty_out_and_repair`

**Steps**

1. You stand in front of a creative planar vortex (always stable) with a crafting table beside you. Your hotbar holds 8 void ingots, a full wand, a damaged enchanted diamond sword, a damaged iron pickaxe, a fresh diamond pickaxe and a stick.
2. Throw the 8 void ingots in so they land inside the 3x3x3 box around the rift. Wait a second, then click the rift with the wand.
3. Put the damaged diamond sword and the putty in the crafting table, nothing else. Then try the sword with the stick added, the damaged pickaxe and sword together with putty, and the undamaged diamond pickaxe with putty.

**Expect**

- [ ] The ingots vanish; one click pops all 8 putty (one stored stack per click), with the chime. The putty shows the boiling purple blob icon.
- [ ] Sword plus putty gives the sword at full durability, sharpness still on and its name kept; every putty in the grid is used up. The other grids give nothing.

<sub>Already covered by automated pack tests: `void_ingots_become_stored_putty_popped_one_stack_per_click`, `putty_repair_matches_one_damaged_item_plus_putty_only`, `research_recipes_and_tag_are_in_the_jar`</sub>

## 2. Wisp swarm from salis mundus

Check id: `horizons_h7_5.wisp_swarm`

**Steps**

1. You stand in survival six blocks from a creative planar vortex, holding 64 salis mundus (stand back: wisps attack).
2. Throw 2 salis mundus into the rift and look at the wisps' colours. Then throw in 8 more, then keep throwing salt while watching the count of wisps near the rift (about 32 within 32 blocks stops it).

**Expect**

- [ ] Each grain makes between one and four wisps at the rift, so 2 grains give 2 to 8. Their aspects are drawn from the rift's own aspects (a creative rift may hold none: the wisps then pick as wild ones do).
- [ ] The rift takes one grain per item per half second, not the whole stack at once. While 32 or more wisps are within 32 blocks it takes no grain at all and the salt waits in the box; kill some wisps and it resumes (the limit is wispCap in the planar config).

<sub>Already covered by automated pack tests: `salis_mundus_makes_one_to_four_wisps_per_grain_of_the_rifts_aspects`, `the_wisp_cap_pauses_the_salt`</sub>

## 3. Crystalline wand: use it, never refill it

Check id: `horizons_h7_5.crystal_wand_use`

**Steps**

1. You stand in front of a creative planar vortex with an arcane workbench beside you. Your hotbar holds an Inert Crystal Wand, a full wand and a Vis Relay.
2. Drop (Q) the Inert Crystal Wand into the rift and click the rift with the full wand. Read the new wand's tooltip and vis bars.
3. Craft something that costs vis at the arcane workbench with it. Then hold it in a node's aura (or place the relay near it and put it on a vis charger), and wait. Look at it held in first and third person.

**Expect**

- [ ] A Crystalline Wand with 250 vis of each of the six primals. Crafting spends vis from it as from any wand (the 0.9 cap discount applies).
- [ ] Nothing refills it: not the node, not a charger, not a relay, not anything else.
- [ ] A pale pink rod with a pale cap.

<sub>Already covered by automated pack tests: `an_inert_wand_comes_back_as_a_crystalline_wand_with_250_of_each_primal`, `crystal_wand_store_ignores_increases_and_applies_decreases`</sub>

## 4. Voidling: follows and warns

Check id: `horizons_h7_5.voidling_follow_and_warnings`

**Steps**

1. You stand in survival on easy in front of a creative planar vortex. Your hotbar holds two golem animation powders, a golem seal, a golem bell and two zombie spawn eggs.
2. THROW one powder (drop it with Q) so it lands in the rift's box. Walk away and around, then fight a zombie with the voidling near.
3. Try the seal and the bell on it. Leave the game running for about ten minutes and watch the chat. Look at it beside an ordinary powder golem (make one by dropping the second powder away from the rift).

**Expect**

- [ ] A dark golem with hearts and the wand sound appears. It starts following you from 16 blocks away, never expires and fights monsters; it takes no seal and the bell does nothing to it. Powder that is simply dropped by a dispenser, or that nobody threw, stays where it is.
- [ ] On average every four minutes or so a chat line: One of your golems is acting strangely; has begun softly chanting; then the italic purple hollow laughter.
- [ ] It is a dark metal figure with a solid black void for a face (no eyes, no glow); the ordinary golem is the block it came from. If you stand beside a hungry planar rift (fewer than six attenuators) with a voidling, the rift does not pull or hurt it, while an ordinary powder golem is dragged in.

<sub>Already covered by automated pack tests: `golem_powder_makes_a_voidling_for_its_thrower_and_a_stranger_powder_is_left`, `a_hungry_rift_leaves_a_voidling_alone_and_pulls_a_normal_golem`, `a_voidling_follows_from_sixteen_blocks`, `voidling_counter_is_a_step_function_of_age_and_roll`</sub>

## 5. Voidling turns into a guardian

Check id: `horizons_h7_5.guardian_turn`

**Steps**

1. You stand in survival in front of a creative planar vortex, holding two golem animation powders.
2. Throw a powder into the rift to make a voidling, then run /data merge entity @e[type=thaumichorizons:powder_golem,limit=1,sort=nearest] {pg_void_count:3} to skip the warnings. Wait (on average four minutes; stand a little way off).
3. Quit and reload the world with a voidling at count 2 (merge pg_void_count:2) and check it carries on.

**Expect**

- [ ] The voidling bursts in portal particles and smoke with a thump, and an Eldritch Guardian stands where it was; the guardian stays within about 32 blocks of that spot.
- [ ] The counter is saved: the reloaded voidling is still a voidling.

<sub>Already covered by automated pack tests: `voidling_turns_into_a_guardian_on_the_fourth_step_and_saves_its_count`</sub>

## 6. The four research entries

Check id: `horizons_h7_5.research_reachable`

**Steps**

1. Only Planar Rift and Golem Powder are done in your research (and what they need), so the gate is real. Open the Horizons tab in the thaumonomicon.
2. Read Wisp Propagation, Crystalline Wand, Void Putty and Voidling Golems.

**Expect**

- [ ] The four entries sit right of New Horizons (15,6), (15,10), (16,9), (16,7); the Crystalline Wand page shows the arcane recipe (pattern, balanced shards and a crystal cluster; any of the six primal clusters works). Voidling Golems gives 1 warp. Texts are the originals plus a short usage note.

<sub>Already covered by automated pack tests: `research_recipes_and_tag_are_in_the_jar`, `four_more_handlers_after_the_pearl`, `a_rift_that_is_not_stable_claims_nothing`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_5`).
