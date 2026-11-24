# QA: Phase 7: Valet Seal and Vengeful Golem

Chapter id `phase_7`, 14 checks. In game this is the FTB Quests chapter **QA: Phase 7: Valet Seal and Vengeful Golem**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumicconcilium:seal_valet`, `thaumaturge:golem_bell`, `minecraft:paper`, `minecraft:anvil`, `minecraft:experience_bottle`, `minecraft:lever`, `minecraft:oak_door`, `minecraft:redstone_lamp`, `minecraft:redstone_torch`, `thaumicconcilium:vengeful_golem_spawn_egg`, `enchanted:earmuffs`

## 1. Valet: a golem uses a lever on your chat phrase

Check id: `phase_7.valet_phrase_lever`

**Steps**

1. You stand in front of a lever with a Valet seal on it; the seal's phrase paper already says "open sesame".
2. Place the golem from your hotbar and give it the Use settings it needs (open the seal with the golem bell; right click, not into air).
3. Stand within 32 blocks and type exactly: open sesame

**Expect**

- [ ] The golem walks to the lever and flips it once, then goes back to what it was doing.
- [ ] Your message still shows in chat as normal.
- [ ] Judge this call: how readable the arming is (the only cue is the golem moving).

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`, `valet_armed_click_toggles_a_lever_once`</sub>

## 2. Valet: a door and a lamp

Check id: `phase_7.valet_door_lamp`

**Steps**

1. You stand between a door with a Valet seal on it (phrase "open sesame") and a redstone lamp with a button in front of it, no seal yet. An anvil is ahead of you; the kit has a seal, two papers, a golem and 10 levels.
2. Name a paper "light" in the anvil, put a Valet seal on the lamp's button (open it with the golem bell, paper in the second filter slot), place the golem.
3. Say each phrase in turn.

**Expect**

- [ ] The door opens or closes on its phrase; the button presses on its phrase; the other does not react.
- [ ] Judge this call: one click per phrase (it never repeats on its own).

<sub>Already covered by automated pack tests: `valet_armed_click_toggles_a_lever_once`</sub>

## 3. Valet: the phrase must match exactly

Check id: `phase_7.valet_exactness`

**Steps**

1. You stand in front of a lever whose Valet seal is set to "open sesame"; the golem is in your hotbar (place it and give it its Use settings).
2. Say "Open Sesame", "open  sesame" (two spaces), "open sesame!" and "open".
3. Then say "open sesame".

**Expect**

- [ ] Case, spacing and punctuation count: none of the near misses fires; the exact phrase does.
- [ ] Judge this call: exact match as the original (user decision).

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`</sub>

## 4. Valet: a renamed bell rung in the air

Check id: `phase_7.valet_bell`

**Steps**

1. You stand in front of a lever with a Valet seal ("open sesame"), an anvil on your right and a plain stone block on your left; the kit has the golem, two golem bells and 10 levels. Place the golem.
2. Rename the golem bell "open sesame" in the anvil.
3. Ring it in the air (aim at no seal, not sneaking). Then ring it aimed at the plain stone block.
4. Ring the second, unnamed bell, and ring the renamed bell while aiming at the seal (it opens the seal GUI) and while sneaking.

**Expect**

- [ ] Ringing the renamed bell in the air or at a seal-less block acts like saying the phrase: the golem goes and uses the lever. The bell still rings.
- [ ] An unnamed bell does nothing extra; aiming at a seal or sneaking keeps Thaumaturge's own gestures (GUI, remove) and does not trigger the Valet.
- [ ] Judge this call: the bell as a quiet trigger.

<sub>Already covered by automated pack tests: `valet_bell_arms_like_the_phrase`</sub>

## 5. Valet: two seals with the same phrase both fire

Check id: `phase_7.valet_two_seals`

**Steps**

1. You stand between two levers, each with a Valet seal set to "open sesame"; two golems are in your hotbar (use one or both, with Use settings).
2. Say the phrase.

**Expect**

- [ ] Both levers are flipped, each by whichever golem takes the task.
- [ ] Judge this call: every matching seal fires (user decision).

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`</sub>

## 6. Valet: out of range, and the arming lapses

Check id: `phase_7.valet_range`

**Steps**

1. Staged where you stand: a lever with a Valet seal ("open sesame") four blocks ahead. The golem is in your hotbar; place it and give it its Use settings.
2. Stand more than 32 blocks from the seal and say the phrase.
3. Back within range, remove the golem (or send it far away), say the phrase and wait about ten seconds.

**Expect**

- [ ] Out of range: nothing happens.
- [ ] No golem takes the task: the arming lapses after 200 ticks and the lever is not flipped later when a golem returns.
- [ ] Judge this call: distance measured to the seal, not the golem.

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`, `valet_expires_unserved_and_idles_free`</sub>

## 7. Valet: another player's phrase (LAN)

Check id: `phase_7.valet_multiplayer`

**Steps**

1. You stand in front of a lever with a Valet seal ("open sesame") and an anvil. Place the golem. Open the world to LAN, a friend joins (they must go to this site themselves) and stands near your seal.
2. The friend says your phrase.
3. Then the friend builds their own Valet seal with their own phrase and says it, while you stand by.

**Expect**

- [ ] The friend's saying your phrase does nothing: only the seal's owner arms it.
- [ ] The friend's own seal works for them and not for you.

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`</sub>

## 8. Valet: research and recipe

Check id: `phase_7.valet_research`

**Steps**

1. You know only the entries before the Valet; open the book (Thaumonomicon key) and look for the "Valet" entry in the Concilium tab (concealed until its parents are known). Read it and the infusion page.

**Expect**

- [ ] The entry appears at its place after its parents; the text explains the phrase paper and the bell; the infusion recipe is shown and can be crafted.
- [ ] Judge this call: the text, and that the seal's GUI has no 'I hear and obey' line (dropped).

<sub>Already covered by automated pack tests: `valet_registered_placed_and_saved`</sub>

## 9. Vengeful Golem: find one at night

Check id: `phase_7.vengeful_found`

**Steps**

1. It is night. A Vengeful Golem stands in a glass cage nine blocks ahead of you (it cannot see you through the glass); a spawn egg is in your hand to place another.
2. Look at it from a distance, side-on and from behind (walk round the cage), and watch it walk.

**Expect**

- [ ] A bell-carrying golem with a brain in a jar on its head shows up; it holds the golem bell in its right hand.
- [ ] Judge this call: how often it appears (weight 5, group 1 to 2, config vengefulGolem.spawnWeight), and its look and walk against the original.

<sub>Already covered by automated pack tests: `vengeful_golem_data_tag_loot_spawn_and_bestiary`, `vengeful_golem_attributes_bell_and_egg`</sub>

## 10. Vengeful Golem: taunts, enslaving and walking off

Check id: `phase_7.vengeful_taunt_enslave`

**Steps**

1. It is night and a Vengeful Golem stands eleven blocks ahead of you in the open. Do not fight it.
2. Stay in its sight and let it attack. Watch your character and the chat. Kill the golem to end the drift (the pad is too small to walk 32 blocks away: do that on real terrain if you want to).

**Expect**

- [ ] It stops at range, swings, an orb sound plays and about four in ten times a purple taunt appears in chat.
- [ ] You are enslaved: your character walks on its own, drifting toward it; you can still look around. Failing the roll (about one in five) releases you instead.
- [ ] Distance over 32 blocks or its death ends the drift.
- [ ] Judge this call: the feel of the enslavement, and the taunt text.

<sub>Already covered by automated pack tests: `vengeful_golem_enslaves_in_sight_and_releases_otherwise`, `vengeful_golem_ranged_goal_refuses_inside_one_block`</sub>

## 11. Vengeful Golem: earmuffs protect you

Check id: `phase_7.vengeful_earmuffs`

**Steps**

1. You wear Enchanted's earmuffs on your head and a Vengeful Golem stands eleven blocks ahead of you in the open.
2. Stand in the golem's sight.

**Expect**

- [ ] No enslaving, no taunt: the golem keeps trying but nothing happens.
- [ ] Judge this call: Enchanted's earmuffs as the protection.

<sub>Already covered by automated pack tests: `vengeful_golem_never_enslaves_with_earmuffs`</sub>

## 12. Vengeful Golem: it sends other mobs wandering

Check id: `phase_7.vengeful_mobs`

**Steps**

1. You wear earmuffs so the golem leaves you alone. A Vengeful Golem stands ten blocks ahead with two pigs and a villager in front of it.
2. Watch the pigs and the villager.

**Expect**

- [ ] Most of the time (about nine in ten) the mob walks off to a random point nearby.

<sub>Already covered by automated pack tests: `vengeful_golem_sends_mobs_wandering`</sub>

## 13. Vengeful Golem: a Nether and End sighting

Check id: `phase_7.vengeful_dimensions`

**Steps**

1. Staged where you stand: only a Vengeful Golem spawn egg (use it to confirm one can exist in each dimension). Explore the Nether, then the End, for a while.
2. Check the config blacklist: add a biome id to vengefulGolem.biomeBlacklist and confirm none appears there.

**Expect**

- [ ] It spawns in all three dimensions (user decision), at the config weight; blacklisted biomes have none.
- [ ] Judge this call: whether the Nether and End population is too much or too little.

<sub>Already covered by automated pack tests: `vengeful_golem_data_tag_loot_spawn_and_bestiary`</sub>

## 14. Vengeful Golem: bestiary page and drops

Check id: `phase_7.vengeful_bestiary`

**Steps**

1. Four Vengeful Golems stand still in a row ahead of you; you have a Thaumometer, a plain sword and a Looting III sword. You have not scanned a golem yet.
2. Scan a golem with the Thaumometer, then open the Concilium bestiary entry.
3. Kill the rest, with the plain sword and with the Looting sword.

**Expect**

- [ ] A page about the Vengeful Golem appears once one is scanned (the image page is skipped on purpose).
- [ ] Drops: 0 or 1 Knowledge Fragment, one more per Looting level.
- [ ] Judge this call: the page text.

<sub>Already covered by automated pack tests: `vengeful_golem_data_tag_loot_spawn_and_bestiary`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_7`).
