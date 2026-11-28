# QA: Gadomancy

Chapter id `gadomancy`, 50 checks. In game this is the FTB Quests chapter **QA: Gadomancy**; each check there has a green "Set up this check" line that builds its test site.

## 1. The Gadomancy tab and the Aura Core

Check id: `gadomancy.aura_core`

**Steps**

1. Read its research entry ("Aura Core") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You know Infusion and Metallurgy. Open the Gadomancy tab.
3. Find the Aura Core entry, a round node, near the left of the tab. Hover it and check its parents. Do not buy it yet.
4. Next: Open the Aura Core entry and finish its first stage (theory) as usual.
5. Once the entry is open past the first stage, page back through all its stages with the history arrows: the text, the infusion recipe, then seven setups.
6. Next: You stand near a terra crystal cluster with a mix of blocks around it (stone, ore, water, a log, a flower, leaves, sand). A charged wand and a blank aura core are in your inventory.
7. Toss the blank aura core a block or two from the cluster.
8. Strike the cluster with the wand and watch and listen for about 25 seconds.
9. Next: An infusion altar stands seven blocks ahead with the Primal Charm in the centre and four Balanced Shards and eight thaumium ingots on its ring pedestals; creative jars of every aspect stand behind it to supply the essentia (the infusion recipe costs auram, praecantatio, alienis and vacuos). Open the Aura Core research and check its infusion page, then run the infusion.
10. Then swap the shards for essentia crystals (a few are in your hotbar) and try again.

**Expect**

- [ ] The Gadomancy tab is there (it appears once Infusion is known), with the original's purple-pink icon and a tiled magical background.
- [ ] Judge the background: the original picture is 700 pixels wide and the book expects 1024, so it may look zoomed or soft.
- [ ] The Aura Core entry is visible, with the core as its icon, and its connectors lead to Infusion and Metallurgy (in the other tabs).
- [ ] The Core Cleaning entry is not visible yet.
- [ ] Nothing is charged for any stage after the first, and no click is needed: they open by themselves, and you can still read every one afterwards.
- [ ] Six setups show a crystal cluster of one primal (air, fire, water, earth, order, entropy) and a cost of 84 of that primal. The seventh shows the Balanced Crystal Cluster from Thaumic Horizons and a cost of 14 of each primal.
- [ ] Each setup's text names the blank Aura Core lying beside the cluster and the wand striking it; the wand and the core are not drawn (the book draws blocks only).
- [ ] The infusion recipe is on the second stage.
- [ ] The cluster is used up and a stream of dust runs from it to the core; the core cannot be picked up while it works.
- [ ] Three motes of colour then orbit the core in a shrinking ring, and a sound marks the end. A new coloured core drops, tuned to the cluster's primal and showing in its tooltip.
- [ ] On bare ground with nothing to scan the attuning does not finish; the core stays blank.
- [ ] The recipe asks for four Balanced Shards; essentia crystals no longer work.
- [ ] The research text already mentions balanced shards.
- [ ] Judge this call: the recipe page shows the shards clearly.

<sub>Already covered by automated pack tests: `gadomancy_research_parses`, `aura_core_recipes`, `aura_core_attunes_earth`, `aura_core_fails_on_bare_ground`</sub>

## 2. Attuning an Aura Core with a Balanced Crystal Cluster

Check id: `gadomancy.core_balanced`

**Steps**

1. Read the Aura Core entry's seventh setup (the balanced cluster): judge clarity, and whether it says the wand must hold 14 vis of each primal and that the blocks around decide the primal.
2. You stand near a Balanced Crystal Cluster with water around it, a blank aura core and a charged wand in your inventory. Toss the blank core a block or two from the cluster.
3. Strike the cluster with the wand and watch for about 25 seconds.
4. Next: empty the wand (cast until it is dry, or take a fresh empty one), place the second Balanced Crystal Cluster from your inventory, toss a blank core beside it and strike it again.

**Expect**

- [ ] The book page draws the Balanced Crystal Cluster block itself, not an amethyst cluster or an empty spot.
- [ ] The strike takes 14 vis of each of the six primals from the wand and uses up the cluster; dust runs to the core as with a primal cluster.
- [ ] The new core is tuned by the surroundings (here most likely water), not fixed in advance.
- [ ] With the empty wand nothing happens beyond a message that the cluster needs 14 vis of each primal; the cluster and the blank core stay.
- [ ] Judge the cost: 14 of each primal, against 84 of one for a primal cluster.

<sub>Already covered by automated pack tests: `balanced_cluster_attunes`, `balanced_cluster_needs_vis`, `primal_cluster_still_starts_at_60`</sub>

## 3. Core Cleaning and the crucible washes

Check id: `gadomancy.core_cleaning`

**Steps**

1. Read its research entry ("Core Cleaning") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You know the Aura Core entry. Open the Gadomancy tab: Core Cleaning should be there. Do not buy it yet.
3. Put an air core into a boiling crucible holding 12 praecantatio, 12 aqua and 18 victus (use the creative aspect tools). Then buy Core Cleaning, and try again.
4. Next: You stand in front of a boiling crucible full of water, with an attuned (air) aura core in your inventory. The crucible holds no aspects: add the ones the cleaning recipe needs (see the Aura Core page in the book) first.
5. Drop the attuned core into the crucible.

**Expect**

- [ ] Before Core Cleaning the wash does nothing; after it, the air core comes out blank.
- [ ] The Core Cleaning page lists the six washes. An earth core alone in a crafting grid does nothing (the original's free undo recipe loads only without Thaumic Concilium).
- [ ] The core turns back into a blank aura core (one recipe per type), consuming the crucible's water as with any crucible recipe.
- [ ] The aura core's research page in the Gadomancy tab (appears after Infusion; the washes need the Core Cleaning entry) shows the infusion recipe and the six cleaning recipes.

<sub>Already covered by automated pack tests: `aura_core_recipes`, `aura_core_undo_recipes`</sub>

## 4. The Aura Pylon: building it and feeding it

Check id: `gadomancy.aura_pylon`

**Steps**

1. Read its research entry ("Aura Pylon") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You know Aura Core and the tubes research, but have never held a core attuned to fire. Open the Gadomancy tab: the Aura Pylon entry (below the Aura Core, bottom of the tab) must not show.
3. Attune a fire core (blank core beside a fire cluster, wand strike) and pick it up. Reopen the tab: the entry now shows, hidden-style. Open it: the first stage is the original's text, the second has both arcane recipes, the second text and a 1 x 4 x 1 drawing of the peak over three pylons with the cost 150 of each primal.
4. Next: Place the peak on air: it must refuse. Place two pylons and a peak on top; strike the peak with your wand: nothing happens (the original is silent) and no vis is spent.
5. Add a third pylon under them and strike the peak, then (after breaking it down and rebuilding) a pylon instead: both forward to the peak. With a wand under 150 vis of each primal you get the vis message; with enough, the wand pays 150 of each primal (a little more with an iron cap) and the column forms. Try it once with five pylons stacked under the peak: it forms over the top three and the two extra pylons pop off as items.
6. Strike the formed column again: nothing is paid. Break any part: every other part breaks and drops as its item.
7. Next: With a formed column, throw an essentia crystal from about seven blocks away. Watch it: it should drift toward the column and float under the peak, bobbing in a spray of white rays.
8. A crystal thrown from ten blocks must be left alone.
9. Wait three seconds, then walk up to the column's middle: the crystal comes into your inventory and the column forgets its aspect.
10. Next: Put a jar under the column's lowest pylon and fill it with the crystal's aspect (the creative jar from the kit works: set its aspect first). With a crystal held, essentia should leave the jar one at a time, about every 16 ticks.
11. Try a jar of another aspect: nothing leaves it. The column holds at most 15 and burns one every 32 ticks, so a jar empties slowly while the column is full.

**Expect**

- [ ] The entry appears only after a fire core was picked up; it lists the pylon and the peak recipes and the column drawing; its text is the original's with the spelling slips fixed.
- [ ] Silence for too few pylons, the vis message for too little vis; vis only spent on success; the peak glows (light 10) even when plain; the column survives a relog; breaking any part breaks the whole column and drops all four items.
- [ ] The pull feels like the original (slow near the edge, quicker close; a wall between stops it, as in the original); the crystal can be picked up by walking close after about three seconds of hold.
- [ ] Only the crystal's aspect is drawn; a tube or jar below never takes essentia back out of the pylon.

<sub>Already covered by automated pack tests: `pylon_research_waits_for_a_fire_core`, `pylon_recipes_and_research_parse`, `pylon_forming_needs_research_and_pays`, `pylon_needs_three_pylons`, `pylon_forms_with_extra_pylons_below_and_drops_them`, `pylon_peak_places_on_a_pylon_only_and_glows`, `pylon_breaking_any_part_breaks_the_whole_column`, `pylon_ticker_only_for_the_formed_master`, `pylon_pulls_crystal_within_eight_blocks`, `pylon_held_crystal_is_picked_up_by_proximity_after_60_ticks`, `pylon_removing_the_crystal_clears_the_column`, `pylon_draws_only_the_crystals_aspect`, `pylon_burns_and_dispatches`</sub>

## 5. The Aura Pylon: how it looks

Check id: `gadomancy.pylon_visuals`

**Steps**

1. Read its research entry ("Aura Pylon") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Build a column (three pylons and a peak) and strike it with a charged wand.
3. Next: Look at a formed column with no crystal in it, from a few blocks away.
4. Next: Put a jar of fire (ignis) essentia under a formed column and hold an ignis crystal in it. Watch for ten seconds.
5. Repeat with water (aqua), with air (aer) and with entropy (perditio).

**Expect**

- [ ] A burst of pastel sparkles fills the column and the blocks around it for about a second, then it is gone. Wisps start rising from the peak at once.
- [ ] A white, flame-shaped blob sits over the peak with small droplets drifting up from it; nothing else moves. Unform it and the effect stops at once.
- [ ] Pale beads climb from the jar to the peak in a thin chain; three bright comets circle the peak on differently tilted rings; wisps take the aspect's colour, with a hot white core in daylight. For perditio the blob, wisps and comets are black or dark grey with no glow.
- [ ] The held crystal bobs and turns mid-column in a spray of white rays.

<sub>Already covered by automated pack tests: `pylon_forming_needs_research_and_pays`, `pylon_ticker_only_for_the_formed_master`, `pylon_pulls_crystal_within_eight_blocks`, `pylon_draws_only_the_crystals_aspect`</sub>

## 6. Pylon auras that give potion effects

Check id: `gadomancy.effects_potion`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: A formed pylon column stands ahead. Feed it an aer crystal (toss it within seven blocks so it floats under the peak, or fill a jar below the lowest pylon with aer) and stand within 8 blocks.
3. Check your effect list: aer should give Speed. Repeat with terra, ordo, potentia and sensus, one at a time.
4. Stand outside the 8 blocks: nothing is added. Step back in and watch the duration rise toward its cap but never past it.

**Expect**

- [ ] Each aspect adds its own potion (aer Speed II, terra Resistance, ordo Regeneration, potentia Strength, sensus Night Vision), refreshed while you stay in range.
- [ ] The duration grows a little each refresh and stops at the cap; leaving range lets it run out.

<sub>Already covered by automated pack tests: `effects_table_binds_every_aspect`, `effects_potion_adds_up_to_the_cap`, `effects_burning_column_applies_its_binding`</sub>

## 7. Lux denies monster spawns

Check id: `gadomancy.effects_lux`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed a formed column a lux crystal. Set the difficulty to easy and stand in a dark cave or room within 64 blocks.
3. Run /kill @e[type=!player] and wait a minute. Then move 70 blocks away (or remove the crystal) and repeat.

**Expect**

- [ ] No monster appears within 64 blocks of a lit column in its own dimension; they spawn again outside it or once the column is out of lux. A column in the Overworld has no effect on the Nether.

<sub>Already covered by automated pack tests: `effects_lux_denies_monster_spawns`</sub>

## 8. Gelum freezes water

Check id: `gadomancy.effects_gelum`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Water lies around the column. Feed a gelum crystal and stand nearby.

**Expect**

- [ ] Still water within range turns to ice a block or two at a time; the freezing is not instant.

<sub>Already covered by automated pack tests: `effects_freeze_turns_still_water_to_ice`</sub>

## 9. Herba speeds up crops

Check id: `gadomancy.effects_herba`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: A field of young wheat grows next to the column. Feed a herba crystal and wait.

**Expect**

- [ ] Crops near the column mature much faster than elsewhere; infused grain from Thaumaturge Tinker ticks faster too.

<sub>Already covered by automated pack tests: `effects_tick_blocks_grows`</sub>

## 10. Spiritus and bestia spawn mobs

Check id: `gadomancy.effects_spawners`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed a bestia crystal, easy difficulty, open ground. Watch for a minute.
3. Swap to spiritus (do it in the dark, not on peaceful).

**Expect**

- [ ] Bestia produces sheep, cows, chickens and pigs now and then (also on peaceful); spiritus produces zombies and skeletons only where dark enough and not on peaceful.

<sub>Already covered by automated pack tests: `effects_spawn_mobs_and_lightning`, `effects_on_animals_and_undead`</sub>

## 11. Vitium spreads taint

Check id: `gadomancy.effects_vitium`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed a vitium crystal, stand within 14 blocks and wait a minute.

**Expect**

- [ ] Taint fibres sprout on nearby blocks, the biome around turns tainted, and living things in range may be poisoned.

<sub>Already covered by automated pack tests: `effects_burning_column_applies_its_binding`</sub>

## 12. Auram charges your wand

Check id: `gadomancy.effects_auram`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Hold a wand with low vis and stand within 8 blocks of a column fed with auram.

**Expect**

- [ ] The wand slowly fills with vis (a trickle each tick) while you stay in range.

<sub>Already covered by automated pack tests: `effects_wand_charge_and_insight`</sub>

## 13. Cognitio gives insight

Check id: `gadomancy.effects_cognitio`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Stand within 8 blocks of a column fed with cognitio for a minute or two.

**Expect**

- [ ] Now and then you gain a point of insight (an experience-like message); sometimes it also costs a little warp, as in the original.

<sub>Already covered by automated pack tests: `effects_wand_charge_and_insight`</sub>

## 14. Alienis makes champions

Check id: `gadomancy.effects_alienis`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed an alienis crystal and stay in range of monsters (easy difficulty).

**Expect**

- [ ] Monsters near the column gain a champion trait for a while, tougher ones getting the higher tiers, as in the original.

<sub>Already covered by automated pack tests: `effects_eldritch_ladder_makes_a_champion`</sub>

## 15. Mining Luck, Vis Affinity and Golem Buff

Check id: `gadomancy.effects_buffs`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed desiderium and break ore with a pickaxe in range.
3. Then feed praecantatio and cast or craft something with vis cost.
4. Then feed fabrico with a golem near the column.

**Expect**

- [ ] Mining Luck raises fortune on the held tool; Vis Affinity lowers the vis you pay; Golem Buff makes golems faster, tougher and stronger (a deliberate change from the original, where it did nothing).

<sub>Already covered by automated pack tests: `effects_mob_effects_behave`</sub>

## 16. Vitreus makes you see-through

Check id: `gadomancy.effects_achromatic`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed a vitreus crystal, stand within 8 blocks in third person (F5) and look at yourself.
3. Let a skeleton shoot at you.

**Expect**

- [ ] Your body turns mostly transparent; armour may stay visible (see the harness shot). Mobs lose sight of you, arrows pass without targeting you as the original does.

<sub>Already covered by automated pack tests: `effects_mob_effects_behave`, `effects_burning_column_applies_its_binding`</sub>

## 17. Learning effects by standing near them

Check id: `gadomancy.effects_research`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Without any effect entry, feed a column an aer crystal and stand in range.
3. Open the Gadomancy tab.

**Expect**

- [ ] A notice tells you what you have learnt; the "aer" effect entry appears (round, aspect icon) in the six-wide block right of Aura Effects; entries sit in order of aspect name with no overlap.

<sub>Already covered by automated pack tests: `effects_research_unlocks_in_range`</sub>

## 18. Ventus calls lightning

Check id: `gadomancy.effects_lightning`

**Steps**

1. Read the effect entries involved (Gadomancy tab, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: With Thaumic Additions installed, feed a ventus crystal (use /give with thaumadditions:ventus) and wait.

**Expect**

- [ ] Lightning strikes near the column from time to time; with no Thaumic Additions the entry is absent.

<sub>Already covered by automated pack tests: `effects_spawn_mobs_and_lightning`</sub>

## 19. Silverwood golems

Check id: `gadomancy.golem_silverwood`

**Steps**

1. Read the Silverwood Golems entry (Gadomancy tab): judge clarity, typos, and whether it explains the feature.
2. Next: An infusion altar stands ahead with creative jars of every aspect. Infuse a Silverwood Golem Frame: a silverwood log in the centre; a primal charm, two salis mundus, two Illuminating Curiosities and two quicksilver on the pedestals.
3. Next: At a Golem Press, build a golem with the silverwood material (the frame and a simple mechanism), then build a wood golem beside it.
4. Place both and compare them: how many hits they take, and how fast they walk to you when you ring the bell to make them follow.

**Expect**

- [ ] The frame infuses only after the research; the press offers Silverwood as a material and uses one frame per golem.
- [ ] The silverwood golem has wood's health, more armour (as clay), damage 1, and walks as fast as a wood golem (light). Its body shows the silverwood planks texture.

<sub>Already covered by automated pack tests: `silverwood_material_is_registered_with_the_decided_numbers`, `frame_and_girdle_infusions_load_with_their_gates`, `golem_research_entries_load_with_parents`</sub>

## 20. Golemic Shielding: the Runic Golem Girdle

Check id: `gadomancy.golem_runic_girdle`

**Steps**

1. Read the Golemic Shielding entry: judge clarity, typos, and whether it explains the feature.
2. Next: Infuse a Runic Golem Girdle: a Fancy Belt in the centre and two salis mundus on the pedestals. Infuse a second one.
3. Put one girdle on a silverwood golem and one on an iron golem, as you fit other golem accessories. Look at both.
4. Wait about a minute, then hit each golem a few times with a sword. Then push the silverwood golem into deep water and let it drown a little.
5. Pick a golem up and place it again: the girdle drops as an item, as other accessories do.

**Expect**

- [ ] The golems wear a belt with a runic sheen. Hits on a charged golem flash the runic ward and play the shield sound, and its health does not drop until the shield runs out; the silverwood golem's shield lasts about 2.6 times longer than the iron golem's.
- [ ] Drowning hurts the golem through the shield (no flash). The shield recharges slowly (one point every 50 ticks).

<sub>Already covered by automated pack tests: `girdle_binds_as_a_golem_accessory`, `shield_limit_is_larger_for_silverwood`, `shield_absorbs_whole_points_and_passes_the_rest`, `shield_recharges_by_ticks`, `shield_ignores_drowning_wither_void_and_starvation`</sub>

## 21. Bodyguard and Break: the host does it

Check id: `gadomancy.golem_bodyguard_break`

**Steps**

1. Read the Golem Core: Bodyguard and Golem Core: Break entries: judge clarity, and whether they point you to the right host features.
2. Follow the Bodyguard entry: give a golem the Fighter addon, ring it with the Golemancer's Bell, walk away and let a zombie hit you.

**Expect**

- [ ] Neither entry has a recipe. The Bodyguard entry explains the bell's follow mode and the Fighter addon; the golem follows you and attacks what hurts you. The Break entry points to the Breaker seal.

<sub>Already covered by automated pack tests: `golem_research_entries_load_with_parents`</sub>

## 22. Sticky jars

Check id: `gadomancy.sticky_jar`

**Steps**

1. Read the Sticky Jars entry (Gadomancy tab, after the warded jars): judge clarity, typos, and whether it explains the feature.
2. You stand in front of an arcane workbench, a stone wall, a stone ceiling slab and a grass floor. In the workbench put a warded jar in a slot with a slimeball directly below it, nothing else, and craft (the kit has a charged wand, aqua and terra crystals, jars and slimeballs). Try a slimeball beside the jar and a slimeball above it: neither may craft. Try a void jar over a slimeball: it crafts a sticky void jar.
3. Put the crafted sticky jar back over a fresh slimeball: it must not craft again.
4. Place a sticky jar against the wall, against the ceiling slab and on the floor, then on the side of a pillar you build: it hangs from the face you click, base to the surface, lid away from it.
5. Next: Pour essentia into each (a phial from the kit, or a creative jar and a tube). Run a tube against the lid of the wall jar and against the lid of the ceiling jar: both must connect and fill. A tube on the side against the wall must not connect.
6. Put a label on a wall jar: the label sits on a side of the jar, readable from where you stand.
7. Break a filled, labelled sticky jar and pick up the drop: its tooltip says Sticky, its bar shows the contents, and placing it again keeps contents and label. Break a braced one: the brace drops too.
8. Look at the jars from several angles: judge how the liquid, label and brace sit on a jar lying on its side or hanging upside down. risk: the renderer is custom for the sticky jars and the host's own for the mirrored one.

**Expect**

- [ ] The entry appears once you know the warded jar entry (it is hidden-style). The recipe is a jar over a slimeball and costs aqua 10 and terra 10.
- [ ] A sticky jar is made only from jar over slimeball, keeps the jar's contents and label, and refuses a second slimeball. The warded jar, the void jar and the mirrored jar can be made sticky; nothing else.
- [ ] Each jar hangs from the face clicked, its essentia connects only at its lid, a tube on the side against the surface does not connect, and a void jar still voids what it cannot hold.
- [ ] Breaking one gives back the plain jar item marked Sticky with its contents and label; the adhesive is never lost.

<sub>Already covered by automated pack tests: `sticky_recipe_matches_and_keeps_components`, `marked_jars_place_the_sticky_twin_on_the_clicked_face`, `sticky_faces_follow_the_face_it_hangs_from`, `sticky_wall_jar_pulls_through_its_outer_face_only`, `sticky_ceiling_jar_pulls_through_its_outer_face_only`, `sticky_void_voids_the_excess`, `sticky_drops_keep_the_mark_contents_and_label`, `jar_orientation_table_matches_the_blockstates_and_shapes`, `jar_blocks_and_items_are_wired`</sub>

## 23. Mirrored jars

Check id: `gadomancy.mirrored_jar`

**Steps**

1. Read the Mirrored Jars entry (Gadomancy tab, after the warded jars and the essentia mirror): judge clarity, typos, and whether it explains the feature.
2. You stand in front of an arcane workbench. Craft two mirrored jars (greatwood logs around, a warded jar above an essentia mirror in the middle; the kit has the parts, a charged wand and crystals).
3. Place one mirrored jar. Right-click it with the other: chat says a new network was created, and the item's tooltip now shows a "Network:" name made of two words. Right-click the placed jar with the item again: no new message.
4. Place the linked item as a second jar, and craft a third from the kit and link it the same way. Pour essentia into one jar (a phial). Watch the three jars: they should even out to within one essentia of each other, a few essentia at a time, and then stop (the combined space is three jars).
5. Break a jar of the network and pick it up: its tooltip still names the network. Place it elsewhere: it rejoins and evens out again.
6. Sneak and right-click in the air with a linked jar item: chat says it was disconnected and the tooltip loses the network name.
7. Put another aspect into a fourth jar of the network, with less in it than the others: it is left alone. risk: the original blocks balancing while a jar of another aspect is the emptiest; judge whether that is acceptable.
8. Make a mirrored jar sticky (sticky jar recipe) and hang it on the wall: it keeps its network. Look at an empty mirrored jar, an empty sticky mirrored jar and a full one: an empty one shows a mirror pane inside. risk: this mirror is drawn by custom rendering.

**Expect**

- [ ] The recipe is GJG over GMG and costs aqua 10, terra 10 and ordo 10. Linking clicks give the three chat lines (new, connected, disconnected); the tooltip name is the same for the item and for every jar of that network.
- [ ] Any number of jars share one network, in this world and across dimensions, and balance at about four essentia per three ticks; an even network does nothing.
- [ ] A jar holds as much as a warded jar (250); drops keep the network id; a different aspect or a label for another aspect stops a jar from taking part.
- [ ] An empty mirrored jar shows a mirror pane in the glass, as the original did; the jar looks like a warded jar otherwise.

<sub>Already covered by automated pack tests: `mirrored_jar_recipe_matches`, `mirrored_network_of_three_balances_and_goes_idle`, `mirrored_balancing_rate_and_no_overshoot`, `mirrored_jar_with_another_aspect_is_never_touched_and_blocks_like_the_original`, `mirrored_jar_with_a_label_takes_only_its_aspect`, `mirrored_jar_leaves_the_network_when_removed`, `mirrored_linking_and_drops_keep_the_network`, `network_names_are_two_words_and_stable`</sub>

## 24. Arcane Dropper

Check id: `gadomancy.arcane_dropper`

**Steps**

1. Read the Arcane Dropper entry (Gadomancy tab, after the essentia smelter and the bellows): judge clarity, typos, and whether it explains the feature.
2. You stand in front of an arcane workbench. Craft an Arcane Dropper (stone, a dropper, bellows and an alchemical construct; the kit has the parts, a charged wand and crystals).
3. Place it against the side of a block: it opens away from the face you click. Place others on a floor and a ceiling and look at how each turns.
4. Throw a few different items into the box two blocks in front of the open face. Put a hopper against a flat side of the dropper (not the open face, not the two sides with the window openings): it should pull the items out of the box one by one.
5. Put a chest, hopper or dropper in front of a flat side so that it pushes items in: they appear at the open face and fly out gently. A hopper on a window side or on the open face must do nothing.
6. Put a comparator on a flat side: it should read more the more items lie in the box.
7. Hold the wand (no focus socketed) and look at the dropper: the 3x3x3 box is outlined. Hold a focus wand or nothing: no outline.

**Expect**

- [ ] The recipe is SDS over BAB over SSS and costs ordo 14, aer 14 and terra 10.
- [ ] The box is a three by three by three area centred two blocks in front of the open face; the dropper behaves like an inventory of the items in it, and takes items of any kind into ten extra slots.
- [ ] Only the three flat sides take hoppers and pipes; the open side and the two window sides do not.
- [ ] The outline appears only for a wand without a focus.
- [ ] The bellows inside the dropper pump without stopping, as in the original (visible through the side windows).

<sub>Already covered by automated pack tests: `dropper_insert_spawns_the_item_in_front`, `dropper_extract_from_the_items_in_the_box`, `dropper_flat_faces_only`, `dropper_comparator_reads_the_box`, `dropper_flip_rule`, `dropper_cache_follows_the_world`, `logistics_blocks_items_and_recipes_are_wired`</sub>

## 25. Arcane Dropper over a crucible

Check id: `gadomancy.arcane_dropper_crucible`

**Steps**

1. You stand beside a filled crucible over a fire. Place an Arcane Dropper on the ceiling above it (or on a wall beside it, open side toward the crucible): you are its owner.
2. Put a hopper full of cobblestone into the dropper (flat side): the cobblestone should dissolve into the crucible, with the bubbling, as if you had thrown it in. Check that the crucible gains aspects.
3. Craft something through the dropper: put the catalyst item for a crucible recipe you know into the crucible first and feed the dropper the item a recipe needs: the product should come out of the crucible as for a thrown item.
4. Leave the game and let someone else (or no one) run the machine, or break and place a dropper from a creative tab with nobody as owner: the items simply fall into the crucible space as normal drops and do not dissolve.

**Expect**

- [ ] While its owner is online, the dropper hands each item to the crucible as that owner (research and recipes as for the owner); items the crucible refuses drop normally.
- [ ] With the owner offline, or no owner, the items drop as usual.

<sub>Already covered by automated pack tests: `dropper_over_a_crucible_hands_the_item_to_its_owner`</sub>

## 26. Arcane Packager

Check id: `gadomancy.arcane_packager`

**Steps**

1. Pick up an aer aura core (the kit has one): the Arcane Packager entry appears (Gadomancy tab, after the Aura Cores). Read it: judge clarity, typos, and whether it explains the feature.
2. You stand in front of an arcane workbench. Craft an Arcane Packager (greatwood planks, a piston, warded glass, an aer core, warded jars and a workbench; the kit has the parts, a charged wand and crystals).
3. Place it and open it: nine item slots, a leather slot, a string slot, an output slot, a progress bar and three checkboxes (use essentia, automatically start, disguise as loot bag).
4. Leather and string mode: put leather, string and a few stacks (some identical) in the nine slots, then power the packager with a lever: a bar fills and the output slot gets a package with its tooltip "Click to open". One leather and one string are used, the nine slots are empty.
5. Switch on "Automatically start" and put more leather, string and items in: it should start by itself the moment everything is there, and again when you take the package out. A held lever must not restart it; only a new switch-on does.
6. Essentia mode: tick "Use essentia", put a tube from an essentia source (fabrico) on top: it fills up to 8; each package then costs 4 fabrico and leather and string stay in their slots. Note that other aspects are refused.
7. Tick "Disguise as loot bag": the output is a common (leather) or uncommon (essentia) loot bag by name and look, and still opens like a package.
8. Right-click the package: its contents drop at your feet with the coins sound and the package is used up.
9. Overpressure: put a package that holds a package inside another stack and pack it, or fill the nine slots with items carrying a great deal of data (a stack of written books, filled bundles): the packager explodes weakly (no fire, no block damage) and throws the nine stacks out on top.
10. Hopper automation: a hopper under it takes the output; a hopper on the side facing you (the front) feeds leather, string and items; a hopper on the other sides does nothing. Break it: the items drop; essentia is lost.

**Expect**

- [ ] The recipe is PSP over GCG over JTJ and costs aer 100, ordo 60 and perditio 50. The entry stays hidden until you pick up an aer core.
- [ ] A package holds up to nine stacks (merged where they match) and costs one leather and one string, or 4 of the 8 fabrico it stores; packing takes about two seconds and the piston moves.
- [ ] The three checkboxes work and survive reloading; the redstone signal starts it on the rising edge only.
- [ ] Opening a package drops its stacks at the holder; a package inside a package that already holds a package, or too much data, makes the packager blow instead.
- [ ] While a package is made, the piston on top presses down over about two seconds and springs back; at rest it sits just above its seat.

<sub>Already covered by automated pack tests: `packager_leather_pack`, `packager_essentia_pack`, `packager_needs_its_cost`, `packager_starts_on_the_rising_edge_only`, `packager_auto_start_on_insert`, `packager_disguise`, `packager_nested_package_drops_and_explodes`, `packager_oversize_drops_and_explodes`, `packager_automation_faces`, `packager_breaking_drops_the_slots`, `packager_saves_and_syncs`, `packager_research_waits_for_an_aer_core`</sub>

## 27. Arcane Packages

Check id: `gadomancy.arcane_package`

**Steps**

1. Take a leather package and an essentia package from the Gadomancy creative tab (they are empty there) and look at their icons: they use the loot bag art (common and uncommon).
2. Hold a package made by the packager: its tooltip says "Click to open". Hold a disguised one: it has no tooltip and carries the loot bag name.
3. Right-click a packed package: the stacks drop at your feet (not into your inventory) with the coins sound.

**Expect**

- [ ] Packages stack to 16; two with the same contents stack together.
- [ ] A disguised package looks and is named like a host loot bag and opens exactly like a package.

<sub>Already covered by automated pack tests: `package_opening_drops_the_stacks`, `packager_disguise`</sub>

## 28. Alchemy Seals: Essentia Draw

Check id: `gadomancy.essentia_draw`

**Steps**

1. Read the Alchemy Seals entry (Gadomancy tab): judge clarity, typos, and whether it explains both seals.
2. Next: An infusion altar stands ahead with creative jars of every aspect. The centre pedestal holds a Control Seal: Empty, and the four ring pedestals a warded jar and three glass bottles. Run the infusion for the Essentia Draw seal.
3. Next: A creative jar full of aqua stands beside a warded jar. Build a wood golem at the golem builder, place it, and put the Essentia Draw seal on the creative jar (use the seal on the jar's top).
4. Put an Essentia Fill seal (from your inventory) on the warded jar, then watch the golem: it should walk to the creative jar, take essentia, and carry it to the warded jar.
5. Look at the golem while it carries: a jar of essentia should show in front of it, and fill with the amount carried.

**Expect**

- [ ] The infusion works only after the research, and gives the Essentia Draw seal.
- [ ] The seal can be set on a jar and on a block that gives essentia, and not on plain stone.
- [ ] The golem takes essentia only when its hands are empty, carries one aspect at a time, and a wood golem carries at most 16 per trip, an iron golem 125.
- [ ] Judge the carried jar: readable, at a sensible size, not buried in the golem's body.

<sub>Already covered by automated pack tests: `carry_table_is_the_decided_one`, `seals_are_registered_with_their_rules`, `draw_and_fill_move_essentia`, `draw_takes_what_fits_and_one_aspect`, `draw_reads_the_alembic_stack_fullest_first`, `carried_essentia_survives_save_and_load`</sub>

## 29. Alchemy Seals: Essentia Fill

Check id: `gadomancy.essentia_fill`

**Steps**

1. Read the Alchemy Seals entry again, its second page: the jar order and the connected jars.
2. Next: A creative jar full of aqua stands ahead. Beside it, three warded jars stand in a row touching each other: the first has a label for aqua, the second is empty, the third is empty. A wood golem stands by them. Put the Essentia Draw seal on the creative jar and the Essentia Fill seal on the middle jar.
3. Watch the golem work for a minute: the labelled jar should fill first, then the others (a wood golem carries 16 a trip).
4. Try a void jar in the row too (in your inventory): it should be filled last.

**Expect**

- [ ] A sealed jar fills the jars connected to it, not only itself.
- [ ] The labelled jar of that aspect fills before an unlabelled one; a void jar is used last.
- [ ] A jar holding another aspect is left alone.
- [ ] No essentia tube changes behaviour because a seal sits on a jar.

<sub>Already covered by automated pack tests: `connected_jars_fill_too`, `fill_chooses_jars_in_the_originals_order`, `host_fill_seal_does_not_see_carried_essentia`, `tubes_and_other_blocks_are_untouched`</sub>

## 30. Essentia Condenser: forming and the golem start

Check id: `gadomancy.essentia_condenser`

**Steps**

1. Read the Essentia Condenser entry (Gadomancy tab): the recipe, the Element of Darkness page and the three stacked blocks.
2. Next: three condensers stand stacked ahead. Right-click the bottom one with a charged wand: the column forms (the wand loses vis) and the bottom glows faintly.
3. A creative jar of aqua stands beside it, with a warded jar of ignis and a wood golem. Try to fill the condenser by hand with a phial and with an essentia tube on a middle side: neither works.
4. Put the Essentia Draw seal on the creative jar and the Essentia Fill seal on a side of the middle condenser block. Once the golem has delivered, take the golem away and watch for a minute.

**Expect**

- [ ] Three stacked condensers form on one wand click with the research; the wand pays vis.
- [ ] An empty condenser pulls nothing by itself; phials and tubes cannot fill it.
- [ ] After the golem's first delivery it pulls essentia by itself from nearby jars (about 1 every half second), only from jars holding no more in total than it does.
- [ ] An infusion on a matrix nearby can draw essentia from it.

<sub>Already covered by automated pack tests: `condenser_forming_needs_research_and_pays`, `condenser_empty_pulls_nothing`, `condenser_pulls_one_per_ten_ticks`, `condenser_fill_seal_delivers_and_tubes_never_connect`, `condenser_is_a_source_for_the_matrix`, `condenser_caps_800_and_2200`</sub>

## 31. Essentia Condenser: the Element of Darkness

Check id: `gadomancy.condenser_element`

**Steps**

1. Hold the Element of Darkness near a mob (a zombie spawns ahead): you and it go blind while it is within 8 blocks.
2. Drop the Element and walk away: the item does not despawn.
3. Next: a formed condenser stands ahead with an ancient pedestal 2 blocks beside its bottom block. Put the Element on the pedestal and wait 20 seconds.
4. Stand within 4 blocks of the condenser afterwards.

**Expect**

- [ ] The Element blinds living things within 8 blocks, held or dropped.
- [ ] On the pedestal it is consumed after about 20 seconds; the condenser's capacity rises (800 to 2200 per aspect).
- [ ] An enlarged condenser slowly pulls you and nearby items toward it; more Elements pull harder (at most 8).

<sub>Already covered by automated pack tests: `element_of_darkness_blinds_within_eight`, `condenser_consumes_an_element_from_a_pedestal`, `condenser_pulls_entities_once_enlarged`</sub>

## 32. Essentia Condenser: breaking a filled one

Check id: `gadomancy.condenser_explosion`

**Steps**

1. Next: a formed condenser holding aqua stands ahead (fill it first with the golem setup of the earlier check, or use the one built here). Break its top block with the axe and step back at once.
2. Look around it afterwards.

**Expect**

- [ ] The other two blocks explode without breaking terrain, vanish and drop nothing; the broken block drops; the essentia is lost.
- [ ] Flux goo and flux gas are left around it, and a taint seed appears at the bottom block (only when it held essentia).

<sub>Already covered by automated pack tests: `condenser_breaking_a_part_explodes_the_column`, `condenser_saves_and_loads`</sub>

## 33. Infusion Claw: automated infusion

Check id: `gadomancy.infusion_claw`

**Steps**

1. Read the Automated Infusion entry (Gadomancy tab): the infusion recipe and both text pages.
2. Next: a Runic Matrix with its pillars and pedestals stands ahead; a lever is beside the claw spot. Activate the matrix with your wand, put an infusion recipe you know on the pedestals (the kit gives a Thaumonomicon for one), place the claw on top of the matrix and right-click it: open its screen and put a charged wand (no focus) in the slot.
3. Flip the lever on (one pulse). Watch for about 22 seconds.
4. Check the matrix's stability with goggles before and after the click; then try the same with a staff or a better-capped wand.
5. With the claw still powered, wait: it does not start again until the signal goes off and on.

**Expect**

- [ ] The claw takes only a wand: no sceptre, no wand with a focus.
- [ ] About 14 seconds after the pulse the claw clicks the matrix and the infusion starts, as if you had clicked it; the wand loses some vis of each primal.
- [ ] The claw runs a visible routine of about 22 seconds: side plates rise, four small zaps crackle (quiet zap sound), the ring spins up, a primal orb drops below the claw just before it clicks.
- [ ] The matrix's stability drops when the claw starts it (about 14 for an iron-capped wooden wand); staffs and better caps cost less.
- [ ] A comparator behind the claw gives 15 while the infusion runs.
- [ ] A wand too low on vis: the claw does not start at all.

<sub>Already covered by automated pack tests: `slot_refuses_sceptres_and_focused_wands`, `rising_edge_runs_and_clicks_at_tick_290`, `instability_formula_on_host_wand_parts`, `no_vis_means_no_click_and_nothing_spent`, `a_registered_target_is_clicked`</sub>

## 34. Infusion Claw: owner, lock and hoppers

Check id: `gadomancy.infusion_claw_owner`

**Steps**

1. Place a claw yourself: it is yours. A second player right-clicking it opens its screen but does not take it over.
2. Tick "Keep useable wand", put a hopper under the claw's side and one beside it; feed a charged wand from a hopper above.
3. Set up the infusion from the previous check, log out (in multiplayer) or have another player pulse the claw while you are offline.
4. Break the claw.

**Expect**

- [ ] Hoppers can put a wand in from any side but the bottom; with the box ticked they cannot take out a wand that still has enough vis, unticked they can.
- [ ] The claw works with its owner offline, with the owner's research (a recipe you have not researched is refused).
- [ ] Nothing goes in or out while it runs. Breaking it drops the wand.

<sub>Already covered by automated pack tests: `owner_is_set_by_a_real_player_and_never_a_fake_one`, `hopper_insert_any_face_but_down_and_lock_blocks_extraction`, `offline_owner_research_comes_from_the_player_file`, `breaking_drops_the_wand_and_saving_keeps_the_state`</sub>

## 35. Book of Knowledge: finishing research notes

Check id: `gadomancy.knowledge_book`

**Steps**

1. Read the Book of Knowledge entry (Gadomancy tab). Try to place the book on the ground, then on the arcane pedestal ahead.
2. Right-click the book.
3. Put the jar of cognitio beside the pedestal, take a research note from a research table (unfinished) and drop it within a few blocks of the book.
4. Wait a few minutes; then place bookshelves around it and compare the speed.

**Expect**

- [ ] The book goes only on top of an arcane pedestal with free space above; it pops off (one item) when the pedestal goes or the space above is filled.
- [ ] Right-click opens the Thaumonomicon.
- [ ] While it works with cognitio, runes glow at the pedestal and you hear pages turning and a quill writing now and then; when the note completes, sparkles spread from the book.
- [ ] The book pulls the unfinished note to itself and holds it floating; it drinks cognitio from the jar; after a while the note turns complete and stays floating until you take it. A complete note is ignored.
- [ ] Bookshelves (and other enchanting boosters) nearby make it faster, though not by much. A comparator gives 15 while it works with cognitio, 1 without.

<sub>Already covered by automated pack tests: `places_only_on_an_arcane_pedestal_with_air_above`, `breaks_with_one_drop_when_the_space_above_is_filled_or_the_pedestal_goes`, `pulls_an_incomplete_note_ignores_a_complete_one_and_finishes_it_with_cognitio`, `shelf_count_is_enchanting_power_plus_two_per_book`, `idle_book_has_comparator_zero_and_no_work`</sub>

## 36. Enervation Field Emitter: no more creeper craters

Check id: `gadomancy.enervation_emitter`

**Steps**

1. Read the Enervation Field Emitter entry (Gadomancy tab; it appears once Sticky Jar is known). Check its recipe page.
2. Place the emitter on top of the jar of ordo ahead of you (the jar must be directly below it). Stand back and watch for about 20 seconds.
3. Place the redstone block against the emitter and wait: the field grows one step, then rests, then grows again (about 100 seconds to full strength).
4. Place the comparator on a side of the emitter with its back toward it (the comparator points away from the emitter), then replace the redstone block with a lever on the emitter and switch it on and off.
5. Next: Build a small wall of planks beside the emitter, about three blocks away. Spawn a creeper beside the wall with the egg and light it with the flint and steel.
6. Wait. Then move the lit creeper out of the field (or switch the redstone off and wait for the field to shrink to nothing) and watch again.

**Expect**

- [ ] The emitter takes ordo from the jar below, slowly (one point every quarter second), and from no other side or aspect; nothing can be pulled out of it. With no redstone signal it does nothing. The small jar inside shows a pale, near-white liquid whose level rises with the ordo stored (empty: plain glass; 8: up to the neck).
- [ ] With the redstone block, the emitter lights up: a green glow, a growing area and light that follows its size. It does not spend ordo until it is powered, and then one point every 0.75 seconds.
- [ ] A comparator beside it reads the size of the field (0 to 15). A weaker redstone signal gives a smaller field; the field shrinks again one step at a time when the signal drops or the ordo runs out.
- [ ] The lit creeper inside the field never explodes: its fuse stays at zero. The same creeper outside the field blows up as usual.
- [ ] TNT or any other explosion inside the field still hurts mobs but breaks no blocks. Endermen inside cannot teleport or pick up blocks. You are not affected by any of it.
- [ ] The emitter does not give a redstone signal itself (only the comparator reading). The particles of the original (green wisps over the jar and on mobs in the field) are not in yet.

<sub>Already covered by automated pack tests: `emitter_ramps_to_the_power_and_holds`, `emitter_decays_without_power_or_ordo`, `emitter_ticker_light_comparator_and_no_redstone_output`, `emitter_fills_from_below_only`, `emitter_explosions_break_no_blocks_inside`, `emitter_keeps_a_creeper_from_exploding`, `emitter_stops_ender_teleports_but_not_players_or_bosses`, `emitter_denies_mob_griefing_inside`, `emitter_recipe_matches`</sub>

## 37. Node Manipulator: roulette for a node

Check id: `gadomancy.node_manipulator`

**Steps**

1. Read the Node Manipulator entry (Gadomancy tab; it appears once the Infusion, Node Stabilizer, Paving Stones and Recharge Pedestal entries are known). Check its two recipe pages and the pattern page.
2. A free node floats three blocks ahead of you. Put the Node Manipulator on the ground under it, the Randomization Focus on top of the manipulator (the node is then one block above the focus), an Ancient Pedestal at each of the four corners around the manipulator (diagonally) and an Ancient Stone on each pedestal.
3. Take the charged wand and strike the manipulator (or the focus) with it. Note the vis spent.
4. Put the charged wand into the manipulator with a right click, and stand back. Watch the vis drain and wait for one result on the node (the drain takes up to 36 seconds with a full wand, the work 15 more).
5. Take the wand out with an empty hand, and read the node with your goggles to see what changed.
6. Break one of the pillars and watch the rest.

**Expect**

- [ ] The recipes and the pattern page are readable. The pattern shows the manipulator at the bottom, the focus above it, the node above that, ancient pedestals and stones at the corners.
- [ ] Striking the unformed pattern with the wand turns the four pedestals and stones into curved pillars that lean in toward the node, and costs 100 vis of each primal. Without the wand's vis, or without the research, nothing is formed.
- [ ] The wand floats and spins over the manipulator once it is in. The manipulator drains it slowly, one point of vis per tick, until each primal has been taken up to 120 points; with at least 70 points of every primal it starts working.
- [ ] Fifteen seconds after it starts working one change lands on the node: its type, its brightness (bright, normal, pale, fading) or its aspects (a compound split, two aspects joined, or a new primal) change. Then, while the wand still has vis, it starts again. A full charge of 120 of each makes the bad changes about a fifth less likely.
- [ ] While it charges, a coloured wisp line rises from the wand for the primal being drawn. While it works, bolts jump from the node to the pillar tips and red runes circle the manipulator every few seconds; forming shows runes on the pillars; when a change lands, sparkles burst round the node.
- [ ] Breaking a pillar breaks its other half (you get an ancient pedestal and an ancient stone back); the other three corners turn back into ancient pedestals and stones and the wand drops out.

<sub>Already covered by automated pack tests: `forming_refused_without_research_pattern_or_vis`, `forming_refuses_energized_and_jarred_nodes`, `forming_pays_exactly_and_swaps_corners`, `only_a_formed_manipulator_ticks`, `unforms_when_a_pillar_breaks`, `unforms_when_a_pillar_top_breaks`, `unforms_when_the_manipulator_breaks`, `unforms_when_the_node_goes`, `unforms_when_the_node_is_energized_or_jarred`, `wand_goes_in_only_when_formed`, `drain_takes_100_per_tick_and_stops_at_the_cap`, `work_starts_at_70_of_each_and_not_below`, `the_real_ticker_drains`, `a_run_takes_300_ticks_and_applies_one_result`, `without_a_node_the_vis_is_lost`, `quality_rule_follows_the_formula`, `draw_weights_are_the_originals`, `result_break_compounds_splits_the_first_compound`, `result_combine_aspects`, `result_modifiers_step_and_stop_at_the_ends`, `result_gain_primal_adds_a_missing_primal`, `result_switch_type_table`, `manipulator_growing_result`, `a_result_survives_save_and_reload`, `the_run_survives_save_and_reload`, `recipes_and_entry_load`, `focus_needs_a_manipulator_and_pillars_drop_their_stand_ins`</sub>

## 38. Gate of the Voidwalkers: the node becomes a way into the Outer Lands

Check id: `gadomancy.gate_of_the_voidwalkers`

**Steps**

1. Read the Gate of the Voidwalkers entry (Gadomancy tab, left of the Node Manipulator). Check its two recipe pages and the pattern page.
2. Build the Node Manipulator as in the other check, but with the Redirection Focus on the manipulator in place of the Randomization Focus: the free node floats three blocks ahead of you. Then set four more Ancient Pedestals anywhere within 8 blocks of the manipulator (between 5 blocks below it and 10 above), no two in the same column, and an Eldritch Eye on each of the four.
3. Strike the manipulator (or the focus) with the charged wand. Note the vis spent. Put the charged wand into the manipulator with a right click and stand back. Watch the drain, then the run (about 20 seconds after the drain ends, a full wand is drained in about 45 seconds).
4. During the run take one Eldritch Eye off a pedestal, then put it back at once; then take one off and leave it off. Fill the pedestal again afterwards and read the manipulator's wand.
5. Run it to the end with the four eyes in place. Look at where the node was. Then step into what is there, with a player who has not got the Gate research first (a second player on your LAN world; the kit's research command grants yours), then with you.
6. On the other side look round; go back through the way you came. Fight to the end of the Outer Lands maze and use the return portal.

**Expect**

- [ ] The recipes and the pattern page are readable. The pattern page shows the manipulator at the bottom, the redirection focus above it, the node on top, ancient pedestals and stones at the corners; the four pedestals within 8 blocks are in the text only.
- [ ] Striking the pattern forms it only with four ancient pedestals found round it (the corner ones do not count), the research and 150 vis of each primal in the wand. The pillars turn as in the Node Manipulator check; the four far pedestals stay as they are.
- [ ] The manipulator drains the wand one point per tick up to 150 of each primal, and starts working at 120 of each. While it works, blue pulses run over the manipulator and the pedestals, and bolts jump from the node to the pillar tips and to the pedestals.
- [ ] An eye taken off for a moment and put back at once changes nothing. An eye left off after the run is under way ends the run: the work and the vis it took are lost, the gate stays formed. An eye missing in the very first moments only holds the run back (it goes on within a second of the eye coming back).
- [ ] After 20 seconds of work (400 ticks), each of the four eyes vanishes with a burst of sparkles on its pedestal (not in the screenshots: check it here), the node is replaced by a dark swirling portal, and the manipulator lets go of the pillars and drops the wand. If the Outer Lands cannot open another labyrinth (or host labyrinths are off in its config), nothing is consumed and a message says so: a puff of smoke and a few dim blue sparkles at the node, and the vis is lost (also not in the screenshots).
- [ ] A player without the Gate research cannot enter the portal (nothing happens, silently). With the research you are taken to the Outer Lands, and the portal vanishes behind you: nobody else can follow and there is no way back through it.
- [ ] At the end of the maze the host's return portal takes you back to where the gate stood.

<sub>Already covered by automated pack tests: `forming_rules`, `the_focus_decides_the_mode`, `scan_range_columns_and_order`, `scan_cache_rescans_only_on_a_failure`, `drain_cap_150_and_start_at_120`, `a_missing_eye_cancels_the_run_or_stalls_it`, `a_pedestal_removed_unforms`, `the_node_or_the_focus_going_unforms`, `a_400_tick_run_opens_the_gate_or_fizzles`, `a_run_fizzles_when_labyrinths_are_off`, `the_command_stages_a_run_that_opens_nothing`, `the_pass_rule_table`, `the_travel_event_holds_the_gate_to_one_passage`, `gate_records_save_and_clean_up`, `a_gate_run_survives_save_and_reload`, `recipe_entry_and_focus_load`</sub>

## 39. Ancient Stones: the optional recipes

Check id: `gadomancy.ancient_stones`

**Steps**

1. Run /datapack list. Look in the Gadomancy tab for an Ancient Stones entry.
2. Run /datapack enable "mod/gadomancy:resourcepacks/ancient_stones", save and quit to the title screen, and open the world again. Look in the Gadomancy tab again (left of the Gate of the Voidwalkers), unlock the entry and read its pages.
3. At an arcane workbench make ancient stone from the eight arcane stones round the eldritch eye; in a crucible with alienis 8, permutatio 8 and perditio 12 turn the arcane brick into an ancient pedestal.
4. Run /datapack disable "mod/gadomancy:resourcepacks/ancient_stones" to leave the QA world as it was.

**Expect**

- [ ] The pack is listed as available but not enabled (it is off in every new world, as the original's option was), and there is no Ancient Stones entry.
- [ ] After the reopen the entry is there, with the original's text and both recipes.
- [ ] Eight arcane stones and an eye make four ancient stones (perditio 16, terra 8 from the wand); the brick becomes one ancient pedestal.

<sub>Already covered by automated pack tests: `the_ancient_stones_pack_is_off_and_valid`</sub>

## 40. Growing nodes: a node that feeds, preys and strikes

Check id: `gadomancy.growing_node`

**Steps**

1. Stand where you can see the two nodes ahead (goggles on). The left one is a growing node (the kit made it with /gadomancy growing); the right one is a smaller plain node 4 blocks from it. Read both: note their aspects.
2. Toss one of each food, one by one, a few blocks from the growing node: an air essentia crystal, a mana bean of air, a vis crystal of air (the cluster item), and a victus essentia crystal (victus is a compound). Read the growing node after each.
3. Wait up to a minute at a distance of about 8 blocks (outside 6, so nothing strikes you). Watch the growing node and the smaller node.
4. Open the Gadomancy tab of the Thaumonomicon and look for new entries beside the Node Manipulator.

**Expect**

- [ ] The growing node is drawn half again as large as the plain node beside it. All four foods, the victus crystal too, are pulled in a curve to the growing node and vanish when they reach it. Each accepted food raises that aspect's base by 1 (the number in the goggles); some are eaten with no gain, more often as the node fills.
- [ ] The growing node locks on to the smaller node, bolts and crumbs run between them and orbs of its aspects stream from the smaller node to the growing one, its aspects fall one at a time and when it is empty it disappears. It never attacks a larger node, an energized one, one being jarred, or a node in a jar.
- [ ] Entries appear without being bought, when you have the entry before them and see the thing happen: Growing Nodes (shown when a node was made growing near you), Growing Behavior (when a node you stand near accepts food), Destroying Behavior (when it drains another node within 16 blocks), (Aggressive Behavior comes with its strikes: the next check). After those, Secrets of Growth can be bought as usual.

<sub>Already covered by automated pack tests: `state_survives_save_and_reload`, `idle_ticker_and_stale_entries`, `level_ticker_runs_listed_nodes`, `primal_foods_are_eaten_and_grow_the_base`, `a_new_aspect_enters_the_base_and_far_food_is_pulled`, `depleted_entries_refill_before_growth`, `compound_food_is_eaten_and_grows_the_base`, `aspectless_food_is_left_alone`, `gains_match_the_original`, `saturation_decides_acceptance`, `happiness_rules`, `predation_chooses_free_smaller_nodes`, `predation_drains_and_removes_the_prey`, `witnessed_research_is_granted_not_bought`, `manipulator_growing_result`</sub>

## 41. Growing nodes: jar one and let it out

Check id: `gadomancy.growing_node_jar`

**Steps**

1. Ahead is a node inside a glass box under a wooden slab roof, 3 by 3 by 3. It is a growing node with a high happiness. Take the charged wand and strike the glass (research Node Jar needed: the kit has it).
2. Wait for the glass to break and the jar to form. Break the jar with your hand (or a pickaxe) and pick up the item. Hover over it.
3. Place the jar item on the floor, then strike it with the wand (the same click that lets out any jarred node).
4. Wait near it for half a minute, within 5 blocks for a few seconds, and do not throw anything near it (this staged node is restless: food would set off its explosion, which is the next check).

**Expect**

- [ ] The jar looks like any jarred node. The jar's node does not feed or strike while it is jarred.
- [ ] The item looks like any node jar and shows the node's type and aspects. It keeps the growing node's state hidden in itself (no visible sign).
- [ ] The node comes back as a growing node: it strikes you when you are close, as before the jar.

<sub>Already covered by automated pack tests: `jar_keeps_the_growing_state`</sub>

## 42. Growing nodes: strikes and the vortex explosion

Check id: `gadomancy.growing_node_restless`

**Steps**

1. A growing node floats 10 blocks ahead of you (goggles on). It was staged restless: its happiness is far above anything play reaches, so it strikes often. With full health, walk to within 5 blocks of it for a few seconds, then come back to where you started.
2. From where you started, throw one air vis crystal toward the node (it lands within its reach and is pulled in), then walk at once to the back edge of the pad (12 blocks behind you) and watch for half a minute. Read the node with your goggles afterwards.

**Expect**

- [ ] Within 5 blocks a bolt of magic damage strikes you now and then with a zap sound (at this happiness 6 hearts each; in play 1 to 6 hearts, more as the node is happier). Creative players are not hit; on Peaceful nothing is. Aggressive Behavior appears in the Gadomancy tab after the first strike.
- [ ] Eating the crystal tips it over: a vortex explosion of about 30 seconds. First it lashes everything within 6 blocks with magic damage and bolts; then it eats the blocks round it, a few each tick, in a cube that grows to about 9 blocks out, with three small taint bursts (flux goo and gas). Warded blocks and nodes are spared.
- [ ] At the end each of its aspects either vanished or was halved, and its stored vis halved too. (Staged this high it is still over the limit: feed it again and it starts over. In play the limit is reached only by long feeding of one aspect.)

<sub>Already covered by automated pack tests: `zaps_hurt_within_six`, `zap_damage_bands`, `explosion_phases_and_end`, `removal_spares_wards_and_the_field_stops_the_bursts`</sub>

## 43. Ethereal Familiar: the wisp and its zap

Check id: `gadomancy.familiar_attack`

**Steps**

1. Read its research entry ("Ethereal Familiar") and its recipe page: judge clarity, typos, and whether it explains the feature.
2. You stand on a pad with the aura topped up. Two husks stand still ahead of you: one in the open 4 blocks ahead, one 5 blocks to your right behind a stone wall. Put the plain fire familiar from your hotbar in your necklace slot (Curios).
3. Look at yourself in third person (F5) and watch the wisp for a full orbit (8 seconds). Hover the familiar in your inventory, with and without Shift.
4. Stay where you are until the husk in the open dies, then pick up what it drops. A second player, if you have one, stands beside you and watches the wisp and the bolts.
5. Take the familiar off, then try to put it on a friend who does not know Ethereal Familiar (or `/thaumaturge research reset` yourself first).

**Expect**

- [ ] An orange wisp with a white halo circles you at about one block, bobbing gently; it reads as a small spirit, not an item.
- [ ] About every 1.6 seconds a bolt jumps from the wisp to the husk in the open, with a zap sound; it takes half a heart each time (husks have 10 hearts). The husk behind the wall is never struck.
- [ ] The kill counts as yours: the husk drops experience and its player-kill loot. A husk struck and not killed turns on you (with NoAI it cannot act on it).
- [ ] The tooltip names the aspect; Shift shows the augments (none here). The other player sees the same wisp and bolts.
- [ ] Without the research the familiar cannot be put in the slot. Taking it off is always allowed; the wisp is gone at once.

<sub>Already covered by automated pack tests: `gear_numbers_match_the_original`, `gear_equip_needs_the_research_and_fits_the_necklace_slot`, `gear_targets_cube_sight_and_hostile_only`, `gear_damage_and_cooldown_per_variant`, `gear_damage_is_credited_to_the_wearer`, `gear_only_the_first_familiar_acts_and_the_controller_is_dropped`</sub>

## 44. Ethereal Familiar: living off the aura, wand fuel

Check id: `gadomancy.familiar_upkeep`

**Steps**

1. The aura of this pad was drained. A husk stands still 4 blocks ahead. Put the Flash Burn I familiar in your necklace slot and wait 10 seconds.
2. Run `/thaumaturge aura vis add 500` and watch for 10 seconds.
3. The charged wand is in your hotbar. Check its vis, let the familiar strike about ten times, and check the vis again.
4. Drop the wand (and any other wand you carry) and watch. Then pick it up again.
5. Swap to the plain familiar (also in your hotbar), drop the wand and watch.

**Expect**

- [ ] With no vis in the aura the familiar idles: no bolts, the wand untouched.
- [ ] Within about a second of the aura coming back it strikes again. It keeps living off the aura: 1 vis every 10 seconds, too little to notice in a normal aura.
- [ ] An augmented familiar pays from the wand, about one hit in three: the wand loses a little ignis and ordo (Flash Burn I costs 4 ignis + 2 ordo hundredths per paid hit). Judge whether the cost feels right.
- [ ] With no wand it stops (it needs fuel for its augments) and starts again within half a second of the wand coming back. Wands in the main inventory pay first (last slot first), then the off-hand, then a wand worn as a curio.
- [ ] The plain familiar never needs a wand; only the aura feeds it. In creative mode nothing is paid.

<sub>Already covered by automated pack tests: `gear_upkeep_takes_one_vis_every_200_ticks`, `gear_familiar_idles_without_aura`, `gear_plain_familiar_spends_nothing`, `gear_augmented_familiar_needs_vis`, `gear_one_hit_in_three_is_paid`, `gear_fuel_sources_in_order`, `gear_vis_comes_from_the_last_wand`, `gear_creative_pays_nothing`</sub>

## 45. Ethereal Familiar: the four elements

Check id: `gadomancy.familiar_elements`

**Steps**

1. Read the four element entries (Lightning Impact, Flash Burn, Corrosive Venom, Enervation Impulse): judge clarity, typos, and whether they explain the feature.
2. You are in creative mode (so the mobs leave you alone and nothing is paid). Four vindicators stand still in a row 4 to 5 blocks ahead; two loose vindicators wander in a fenced pen 5 blocks to your left. Wear each of the four familiars in your hotbar in turn for about 10 seconds, the Lightning Impact one while the loose husks are in reach. Read the effects on the vindicators with a second look or `/data get entity`.
3. Swap between them quickly a few times.

**Expect**

- [ ] Each element has its own bolt colour (the plain familiar's is its aspect colour). Judge whether each reads clearly.
- [ ] Lightning Impact III: harder hits; half the time the struck vindicator is thrown away from you and upward (the loose ones; still mobs do not move).
- [ ] Flash Burn III: the vindicator burns for nearly two minutes and gets Sun Scorned III for a minute.
- [ ] Corrosive Venom III: Poison II for 30 seconds and Wither IV for two minutes; its reach is a little longer. It strikes any hostile mob (undead shrug the poison off).
- [ ] Enervation Impulse III (with Sensitivity Boost II): three vindicators struck at once, each with Weakness II and Slowness II for 30 seconds; its hits are weaker, its reach longer.
- [ ] Only the familiar you wear acts; a swap takes effect at once.

<sub>Already covered by automated pack tests: `gear_element_effects`, `gear_weakness_three_strikes_three_of_four`, `gear_range_follows_the_augments`, `gear_damage_and_cooldown_per_variant`</sub>

## 46. Ethereal Familiar: infusing it and its upgrades

Check id: `gadomancy.familiar_upgrades`

**Steps**

1. Read the Ethereal Familiar, Flash Burn and Arc Amplification entries and their recipe pages: judge clarity, typos, and whether they explain the feature. Check that Arc Amplification and Sensitivity Boost were locked with a message until an element was known.
2. An infusion altar stands 7 blocks ahead with empty pedestals; creative jars stand behind it. Put the runic-shielded Fancy Amulet on the centre and two ignis crystals, two salis mundus and two yellow nitor on the ring, and run the infusion with your wand.
3. Try the same with the plain Fancy Amulet, then with one ignis and one aer crystal.
4. Upgrade the new familiar to Flash Burn I (four ignis crystals and four blaze powder), then put Flash Burn I's items round the Flash Burn I familiar again.
5. Try Lightning Impact I on it (four ignis crystals, two alumentum, two amber), then Arc Amplification I (four ignis crystals, two amber, two gunpowder). Then try the four ignis crystals of any upgrade swapped for aer crystals.
6. Try to put runic shielding on the familiar with the host's runic augment infusion.

**Expect**

- [ ] The base infusion makes a fire familiar (orange wisp; the aspect in its tooltip). It costs ignis 10, auram 12, praecantatio 18.
- [ ] The plain amulet and the mixed crystals are refused.
- [ ] Flash Burn I takes it to Flash Burn I. The same items again do nothing: each upgrade takes only the level just below it (Flash Burn II has its own items), and no augment goes past its top level (3, or 2 for range and speed).
- [ ] Lightning Impact is refused (one element per familiar); Arc Amplification I works (it needs an element first). Crystals of another aspect are refused: upgrades take the familiar's own aspect.
- [ ] The familiar cannot take runic shielding.

<sub>Already covered by automated pack tests: `gear_the_20_recipes_resolve`, `gear_base_recipe_takes_a_shielded_amulet_and_one_aspect`, `gear_upgrade_takes_own_aspect_crystals_and_adds_a_level`, `gear_each_level_takes_only_the_level_below`, `gear_upgrade_conflicts_and_precondition_refuse`, `gear_familiar_entries_load_in_their_cells`, `gear_damage_and_range_need_any_one_element`, `gear_addon_aspects_with_their_fallbacks`, `gear_familiar_is_not_runic_shieldable`</sub>

## 47. Thaumic Sight

Check id: `gadomancy.thaumic_sight`

**Steps**

1. Read its research entry ("Thaumic Sight") and its recipe page: judge clarity, typos, and whether it explains the feature.
2. An infusion altar stands 7 blocks ahead; a node floats 4 blocks to your left and creative jars stand behind the altar. Infuse Thaumic Sight onto the iron helmet: the helmet on the centre, the goggles of revealing and two salis mundus on the ring.
3. Wear the helmet. Look at the node, at a creative jar, and at your aura readout. Then take it off and look again.
4. Infuse Thaumic Sight onto the Protection IV, Unbreaking III diamond helmet and compare the essentia it asks for. Try the enchanting table and an anvil with a book on a plain helmet.

**Expect**

- [ ] The helmet carries the enchantment "Thaumic Sight" with the glint, beside its other enchantments.
- [ ] Worn, it reveals as the goggles do: the node is visible with its aspects, the jar's contents and the aura readout show. Off, they are hidden again. Also in a Curios head slot.
- [ ] The enchanted helmet costs more (about sensus 26 + praecantatio 13 instead of 16 + 8, as the host's own enchantment infusions) and may add one warp. The enchanting table, loot and villagers never give Thaumic Sight.

<sub>Already covered by automated pack tests: `gear_sight_enchantment_is_head_armour_level_one_and_out_of_every_tag`, `gear_sight_recipe_resolves_and_is_the_one_the_matrix_finds`, `gear_sight_recipe_adds_the_enchantment_and_keeps_the_rest`, `gear_sight_reveals_like_goggles`, `gear_sight_entry_loads_in_its_cell`</sub>

## 48. Armour Disguise: disguised and transparent

Check id: `gadomancy.armor_disguise`

**Steps**

1. Read its research entry ("Armour Disguise") and both recipe pages: judge clarity, typos, and whether it explains the feature.
2. An infusion altar stands 7 blocks ahead; an armour stand is beside you. Disguise the iron chestplate as the golden one: the iron chestplate on the centre, two slime balls, two quicksilver and the golden chestplate on the ring.
3. Make the iron helmet transparent: the helmet on the centre, the same four items and the invisibility potion on the ring. Then disguise the carved pumpkin as the zombie head.
4. Try a golden helmet as the chestplate's disguise, and try the elytra as either piece.
5. Wear the three pieces and look at yourself in third person (F5), with your armour bar in view; hover them in your inventory. Then put them on the armour stand. A second player, if you have one, looks at you.

**Expect**

- [ ] Each infusion gives back the same piece with a green tooltip line, "Disguised as Golden Chestplate" or "Transparent"; its armour points, durability and enchantments are unchanged.
- [ ] A piece for another slot and the elytra are refused.
- [ ] Worn, you look as if you wore the golden chestplate; the helmet is not drawn at all; the pumpkin is drawn as the zombie head. Your armour bar still counts iron. The other player sees the same.
- [ ] On the armour stand each piece shows its true look (only players are disguised).

<sub>Already covered by automated pack tests: `gear_disguise_recipe_resolves_and_is_the_one_the_matrix_finds`, `gear_disguise_result_keeps_the_stats`, `gear_disguise_slot_rules`, `gear_disguise_invisibility_potion_makes_it_transparent`, `gear_disguise_entry_loads_in_its_cell`</sub>

## 49. Armour Disguise: washing it off

Check id: `gadomancy.armor_disguise_removal`

**Steps**

1. Two pools of Purifying Fluid (one source block each) lie 3 blocks ahead, left and right; a pool of water lies straight ahead. Throw the disguised chestplate into the water and wait 10 seconds, then pick it up.
2. Throw the disguised chestplate into the left Purifying Fluid pool and watch for 5 seconds.
3. Throw the transparent helmet into the right pool and watch.

**Expect**

- [ ] Water does nothing.
- [ ] In the Purifying Fluid the chestplate bubbles for 2 to 5 seconds, then the golden chestplate pops out beside it, the pool is used up, and the iron chestplate lies there plain (no tooltip line).
- [ ] The transparent helmet loses its disguise the same way, and nothing else drops.

<sub>Already covered by automated pack tests: `gear_disguise_purifying_source_removes_it`, `gear_disguise_transparent_drops_nothing`, `gear_disguise_flowing_fluid_and_water_do_nothing`, `gear_disguise_water_does_nothing`</sub>

## 50. Jade: claw owner and jar network

Check id: `gadomancy.jade_lines`

**Steps**

1. Place the Infusion Claw from the kit anywhere and look at it with Jade showing (no goggles needed).
2. Place the mirrored jar from the kit and hang the sticky mirrored jar on a wall; look at each. Compare with the items' tooltips (hover a second copy in your inventory).
3. Place the plain sticky jar and look at it.
4. Open Jade's config (default key: numpad 0), find the Gadomancy section, turn off "Infusion Claw owner" and "Mirrored jar network", and look at the claw and the jars again. Turn them back on.

**Expect**

- [ ] The claw shows a gray line "Owner: <your name>" under its name.
- [ ] Both mirrored jars show "Network: <two-word name>", the same name as on the item tooltip; the host's jar contents line still shows as before.
- [ ] The plain sticky jar shows no network line.
- [ ] With the toggles off, each line is gone; on again, it is back. Nothing else in Jade changes.

<sub>Already covered by automated pack tests: `claw_owner_line_and_round_trip`, `mirrored_jar_network_line_and_round_trip`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `gadomancy`).
