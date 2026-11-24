# QA: The Vessel (5d): capital, endings, grove, pond

Chapter id `phase_5d`, 28 checks. In game this is the FTB Quests chapter **QA: The Vessel (5d): capital, endings, grove, pond**; each check there has a green "Set up this check" line that builds its test site.

## 1. The Verdant Capital: the star in its sphere

Check id: `phase_5d.capital_turns`

**Steps**

1. Shader packs off. You stand three blocks from a Verdant Capital sitting on a Vessel Anchor shard.
2. Set its state by hand from where you arrived (the capital is at ~ ~1 ~3): /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:0b} for idle, {drive:2b,starvedSince:99999999L} for starved and calm, {drive:2b,starvedSince:-100000L} for starved and angry (the latter half of its grace), {drive:3b} for unwinding. feedSide 2, 3, 4, 5 are north, south, west, east; 1 is from above (a spark).
3. Watch each state for at least two breaths from two blocks away, from the side and from above, then from five blocks. Go idle, fed, starved calm, starved angry, unwinding (wait ten seconds), then fed again and keep watching for half a minute.

**Expect**

- [ ] The capital is eight small golden tetrahedra (cyan gilding, a little lichen along their edges) hovering over the shard on a faint cyan sphere: each piece is half sunk into the sphere's surface, its centre exactly on it. Four form a triforce pointing up, four one pointing down. From above, idle, it is a six-pointed star.
- [ ] It breathes in every state: the sphere and the pieces swell a little and settle back, never below the size of the state. Idle: slow, even and deep, about five breaths a minute, with a short rest at the top and a longer one at the bottom; a very faint rocking of the pieces and shiver of the whole thing that is strongest at the top of the breath and gone by the end of the rest.
- [ ] Fed: a little wider, the two triforces turning opposite ways (one turn in six seconds), a green-white beam from the fed side through the exact centre of the sphere, its pulses flowing inward. The breath is exact box breathing: four seconds in, four held, four out, four held.
- [ ] Starved, calm: the ray fades, the star returns to its idle size and slows to a crawl, the sphere dims half way to black with a violet rim. It breathes like uneasy rest, about 13 a minute, a little uneven, with a long slow sigh now and then.
- [ ] Starved, angry (the latter half of the grace): within a few seconds the breath turns deep and hard, about 16 a minute: a full inhale, a short sharp exhale, then a half-second pause.
- [ ] Unwinding: the star draws in, the rings reverse briefly then stop on a star alignment, and the six waist pieces leave their triforces: each loops over the equator and back, one after another round the waist, turning a little about its own axis one way above the equator and the other way below, while the two pole pieces keep spinning opposite ways. The star then draws in further. The sphere is a practically jet-black orb with a dark violet rim (the Vessel's colours). The breath is fast, shallow and ragged, about 43 a minute, with gasps; the pieces tremble and the whole capital jiggles roughly and never quite stops. The beam is violet with its pulses flowing back out, and purple-white crackles jump from the pieces.
- [ ] Fed again after unwinding or starving: the pieces return to their triforces, the star opens, and it takes one sigh of relief: a double inhale to its fullest and one long exhale (about ten seconds), then box breathing.
- [ ] The pieces never touch or pass through one another, in any state or while changing state, and the whole star stays inside its block.
- [ ] In the inventory and in the hand the item is the closed star (the eight pieces joined into two interlocked triforces), still, in a faint cyan sphere.

<sub>Already covered by automated pack tests: `capital_update_tag_carries_drive_side_and_time`, `capital_motion_keeps_to_its_proven_bounds`</sub>

## 2. The capital under shader packs (QA only)

Check id: `phase_5d.capital_shader_packs`

**Steps**

1. The render harness cannot load Iris, so this is checked only here. You stand three blocks from a Verdant Capital on an anchor shard. Turn on BSL and repeat the fed and unwinding states of the previous check (set them from where you arrived with /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:3b} for unwinding), by day and by night; then the same under Bliss.

**Expect**

- [ ] The gold pieces are lit and shadowed like any block and cast shadows; with a labPBR pack the gold shines and the lichen does not.
- [ ] The sphere is a faint translucent glow round the pieces, not an opaque disc; dark with a violet rim when unwinding. Its shadow, if the pack casts one, may be a disc: say if that is distracting.
- [ ] The ray is bright (it should glow or bloom like a beacon beam), with its cleats still visible.
- [ ] Each crackle keeps its white core and violet fringe. The dark outline round it may be softer than without shaders, but it must darken, not brighten or tint, what is behind it.

## 3. The mana pond's surface (the chart)

Check id: `phase_5d.pond_sheen`

**Steps**

1. Shader packs off. A sheet of mana pond is sunk into the ground in front of you (7 by 5 blocks). Look at it; for the pond of a tier 3 or 4 grove, look at it in the grove checks as well.
2. Watch it for half a minute by day, then /time set midnight.

**Expect**

- [ ] A still, pale blue surface that reads as one sheet of water: thin veins of light wander across it and run over block borders, with paler and deeper zones several blocks wide. No pattern repeats from block to block and nothing drifts in one direction.
- [ ] It moves slowly (the whole picture comes round in 16 seconds) and never jumps.
- [ ] Sparkles are rare: two or three small stars rise from one spot, then nothing for 6 to 14 seconds. Now and then a single faint glint shows on a vein.
- [ ] It glows at night (light level 12).
- [ ] Say what you would turn up or down: the zones, the veins and the sparkle events are separate dials.

<sub>Already covered by automated pack tests: `pond_is_placed_at_tier_3_and_4_and_not_without_botania`</sub>

## 4. The pond in its livingrock mound

Check id: `phase_5d.pond_shape`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground at least 6 blocks deep: stand on open ground first). Wait a minute.
2. Look at the pool in the middle of the hollow from the rim, from the crater floor beside it and from above. Press Again two or three times in different places.

**Expect**

- [ ] 13 blocks of mana at one height in a basin of Botania livingrock: a low outcrop one block above the crater floor, the water level with its top, no side of the water open.
- [ ] The pool is round-ish and varies from crater to crater (the roundest shape is the commonest, a third of them, the others a little longer); the rock rim is wider and uneven, mostly 2 to 3 blocks, with slabs and stairs weathering its outline.
- [ ] Moss and cracks creep up from the grass: mossy and cracked livingrock bricks, moss carpet, moss blocks and tongues of turf are densest where the stone meets the grass and thin out toward the water; none touch the water. Small plants grow on the lower slope and beside the stone.
- [ ] No sapling or tree stands on the mound.
- [ ] Say if it reads too tidy or too mossy: rim width, the shares of stairs, slabs, bricks and moss are separate dials.

<sub>Already covered by automated pack tests: `pond_shape_is_a_rough_circle_of_13`, `pond_is_level_in_a_livingrock_mound`, `pond_mound_rule_ring_rim_and_edge_stones`</sub>

## 5. The pond under shader packs (QA only)

Check id: `phase_5d.pond_shader_packs`

**Steps**

1. The render harness cannot load Iris, so this is checked only here. A sheet of mana pond is sunk into the ground in front of you. Turn on BSL and look at it by day and at night; then the same under Bliss, Noble, Revelation and Solas.

**Expect**

- [ ] The surface shows on all 13 blocks, pale blue and translucent: not black, not invisible, no missing tile, not replaced by the pack's own water.
- [ ] The veins still run across block borders (no grid) and still move (the texture animates); nothing flickers from 30 blocks away.
- [ ] It glows at night and lights the ground round it; the rising sparkles show.
- [ ] Name any pack where one of these fails.

## 6. The grove kills the Taint Seed

Check id: `phase_5d.seed_death`

**Steps**

1. A Taint Seed six blocks ahead is already being killed by the grove (twelve seconds, the roots break the ground within three). Watch from where you stand; press Again to replay it, and fly out to about 32 blocks before pressing Again to watch it from far away.
2. For the real thing, finish a rite with three or four Verdant Capitals and wait at the crater until the grove has finished spreading (see the Teaser check).

**Expect**

- [ ] Eight roots break the ground in a ring and arch over the seed within three seconds; the seed lashes five times, faster each time, with its own tentacle sound, and the roots flinch and tighten; six clusters of leaves burst out one after another; the seed dies, a column of green-gold motes rises, and the whole mound sinks into the ground.
- [ ] In the real ending the seed cannot be killed early, its column turns to grove and the mana pond appears within a second of the mound sinking.
- [ ] From 32 blocks the roots and the mote column can be made out. Say if this should read more strongly at a distance.
- [ ] The timing feels right: not rushed, not dragging; the seed's own death flash under the leaves is not distracting.
- [ ] With BSL and with Bliss (QA only, no harness): roots and leaves are lit and shadowed, the motes show.

<sub>Already covered by automated pack tests: `grove_kills_the_seed_over_twelve_seconds_then_paints_its_column`, `seed_death_skips_a_missing_seed_and_resumes_after_load`, `doomed_seed_dies_when_the_last_ring_closes`</sub>

## 7. Teaser: the Vessel's ending

Check id: `phase_5d.teaser`

**Steps**

1. You are staged where you stand: open flat ground, difficulty easy. Set your shader pack and start your own recorder first (the game does not film itself).
2. Tick this box, then claim a reward: the first runs the tier 4 ending (four capitals), the second tier 3 (three). The crater is cut under your feet and you are moved to its edge; the rite is on its last unit and finishes at once.
3. Fly or walk around by hand while the real ending plays: the swell, the dark, the wisp and the burst, the grove spreading, the trees growing, three to five wild Taint Seeds eaten by roots in the background.

**Expect**

- [ ] The real finale, painter, growth and roots run as in a played rite (the tier 4 grove is 70 or more blocks across: give it about 2 to 3 minutes), with the seeded Taint Seeds strangled by roots after the light returns.
- [ ] Tier 3 differs only in three capitals and about three in four seeds rooted.

<sub>Already covered by automated pack tests: `staging_finishes_a_tier_4_rite_and_seeds_the_grove`, `staging_finishes_a_tier_3_rite_and_seeds_the_grove`</sub>

## 8. Craft and place the Verdant Capital

Check id: `phase_5d.capital_craft`

**Steps**

1. You have The Green Translation research and three Verdant Capitals (the infusion itself is covered by the recipe test: it needs the jar node catalyst and the two Botania runes, silverwood and greatwood saplings, gold, quicksilver and a mana diamond). A Subdued Vessel hangs five blocks ahead with its four anchors round it; one lone anchor stands three blocks behind you.
2. Place a capital on one of the Vessel's anchor shards, then on another block (the grass), then on the lone anchor.

**Expect**

- [ ] It places only on an anchor shard; on any other block it vanishes (drops back).
- [ ] Without a Subdued Vessel it refuses.
- [ ] Broken, it drops itself.

<sub>Already covered by automated pack tests: `capital_infusion_recipe_is_loaded`, `capital_places_only_on_a_subdued_shard`</sub>

## 9. Feeding, starving and unwinding

Check id: `phase_5d.capital_feeding`

**Steps**

1. A Verdant Capital stands three blocks ahead on an anchor shard, with a creative Botania mana pool three blocks to its left. You have two sparks, a spreader and a wand of the forest.
2. Feed the capital with a spark between the pool and it (or with the spreader) and note how long one spreader keeps it fed.
3. Stop feeding. Wait past the grace (6000 ticks, or lower the config).

**Expect**

- [ ] Fed: the star opens, counter-rotates, the beam runs through the centre. One spreader should not keep it fed for long.
- [ ] Starved: spin slows, sphere darkens; past the grace it unwinds with purple crackles and a unit is refunded.

<sub>Already covered by automated pack tests: `capital_is_a_mana_receiver_and_spark_socket`, `capped_anchor_spends_mana_a_tick_and_gives_no_warp_or_spill`, `starved_capital_pauses_unwinds_refunds_and_shows_its_drive`</sub>

## 10. Heartstone partners count

Check id: `phase_5d.capital_heartstone`

**Steps**

1. A Verdant Capital stands three blocks ahead on an anchor shard (the Heartstone pair and the second player are not staged).
2. With a Heartstone pair linked, finish the rite with the partner offline (see the Teaser check), then have them log in.

**Expect**

- [ ] The partner is counted at the ending and is paid (mote, research) on login.

<sub>Already covered by automated pack tests: `placer_and_heartstone_partner_are_participants`, `offline_partner_counts_and_is_owed_a_mote`, `registry_records_heartstone_ids_on_login`</sub>

## 11. Endings at tiers 0 to 4

Check id: `phase_5d.endings_tiers`

**Steps**

1. You are staged where you stand and the tier 4 ending (four capitals) has been started: you are moved to the crater's edge. Tier 3: press Again at a new spot and run /thaumicconcilium qa finale 3 instead of the staged one. Tiers 0 to 2 need a played rite (the command takes 3 or 4 only).
2. Run the rite at 0, 1, 2, 3 and 4 capitals and compare the endings.

**Expect**

- [ ] Taint pulses run in full at every tier, including a rite run only by capitals.
- [ ] Tier 0: an accelerated seed and its children spread past the crater. Tier 1: a bound seed, taint held near the rim. Tier 2: a seed that starves. Tiers 3 and 4: no seed at the centre.
- [ ] Second mote chances rise with tier; tier 4 removes permanent warp (3 solo, 1 with a partner), once per Vessel.
- [ ] Research The Glade arrives for every tier 3 and 4 participant, online and on next login; none at tiers 0 to 2.

<sub>Already covered by automated pack tests: `pulses_are_full_at_every_capital_count`, `mixed_rite_finishes_records_the_capital_count_and_drops_the_capitals`, `tier0_accelerated_seed_and_children`, `tier1_bound_spreads_to_the_rim_and_no_further`, `tier2_starving_seed_has_no_reserve`, `tiers_3_and_4_doomed_seed_has_no_reserve_and_a_grove_job`, `tier4_warp_three_solo_one_each_for_a_pair`, `tiers_3_and_4_grant_the_glade_to_every_participant_tiers_0_to_2_do_not`, `an_offline_participant_gets_the_glade_on_login`</sub>

## 12. Roots strangle Taint Seeds

Check id: `phase_5d.roots`

**Steps**

1. You are staged where you stand and the tier 3 ending (three capitals) has been started, with wild Taint Seeds seeded in the grove. Press Again somewhere else and run /thaumicconcilium qa finale 4 for tier 4.
2. Watch the seeds in the fight and in the grove.

**Expect**

- [ ] Seeds are strangled at about 0/25/50/75/100 percent by capital count; at tier 4 every seed in the grove is rooted. At most 3 sequences at once nearby.

<sub>Already covered by automated pack tests: `root_chance_by_capitals_and_the_overlap_rule`, `tier4_roots_every_seed_in_the_grove`, `tier3_roots_about_three_in_four`, `no_more_than_the_cap_play_at_once_near_each_other`</sub>

## 13. The finale: blindness, wisp, white-out

Check id: `phase_5d.finale_sight`

**Steps**

1. You are staged where you stand and the tier 4 ending has been started (you are moved to the crater edge). Watch it from outside; to see it from inside the swollen Vessel, press Again and walk into the crater at once. Use a second player over LAN if you can.
2. Also run the ending at tiers 0 to 2 (played rite) and at 3 (/thaumicconcilium qa finale 3).

**Expect**

- [ ] Tiers 0 to 2: about 8 s of full Blindness and Darkness inside; nothing outside; no light, no flash.
- [ ] Tiers 3 and 4 inside: dark while the crater is painted, then a shadowy view with a faint wisp from the pond, pulsing and bursting. Outside: the Vessel shifts violet to cyan, then a white-out of 1 to 2 s. Insiders see before outsiders.
- [ ] Sight returns well before the roots begin (about 20 s). Logging out or reloading mid-finale ends the Vessel at once and sight returns.

<sub>Already covered by automated pack tests: `tier0_blinds_for_8_seconds_without_light_or_flash`, `tier1_blinds_for_8_seconds_without_light_or_flash`, `tier2_blinds_for_8_seconds_without_light_or_flash`, `tier3_paints_the_crater_under_cover`, `tier4_roots_wait_for_sight_after_the_painted_crater`, `unfinished_crater_collapses_at_the_timeout`, `a_vessel_loaded_in_dying_ends_at_once_and_returns_sight`</sub>

## 14. Breath and tremble: judge the feel

Check id: `phase_5d.capital_breath`

**Steps**

1. You stand three blocks from a Verdant Capital sitting on an anchor shard.
2. Watch it across idle, fed, starved, angry, unwinding and fed again; set the states from where you arrived (the capital is at ~ ~1 ~3): /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:0b} for idle, {drive:2b,starvedSince:99999999L} for starved and calm, {drive:2b,starvedSince:-100000L} for starved and angry (the latter half of its grace), {drive:3b} for unwinding. feedSide 2, 3, 4, 5 are north, south, west, east; 1 is from above (a spark).

**Expect**

- [ ] Calm and slow when fed or idle, anger in the latter half of the grace, ragged panic when unwinding, one sigh of relief when fed again.
- [ ] At full compaction the pieces cross the equator and pirouette; the orb is near black with a faint violet rim.

<sub>Already covered by automated pack tests: `capital_motion_keeps_to_its_proven_bounds`</sub>

## 15. The grove: biome and radius

Check id: `phase_5d.grove_biome`

**Steps**

1. A tier 4 grove of radius 70 is being painted where you stand (staged here, on real ground: stand on open ground first). Watch for a few minutes, then press Again elsewhere and run /thaumicconcilium qa grove 3 12; or watch a real ending.

**Expect**

- [ ] The grove biome shows (sky, colours, magical forest spawns); radius 70 to 120 at tier 4 (by the rite's burden), about the crater plus 2 at tier 3.
- [ ] Taint does not restore over it; nodes inside do not drift to the taint.

<sub>Already covered by automated pack tests: `tier3_paints_grove_hollow_and_bare_pond`, `tier4_soil_and_step_timing`, `tainted_column_decays_then_paints_and_restore_returns_grove`, `pure_node_leaves_grove_as_grove`</sub>

## 16. Grove flora and nodes

Check id: `phase_5d.grove_flora`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground: stand on open ground first).
2. Walk the grove after painting; look in shade for mushrooms.

**Expect**

- [ ] Botania flowers, double flowers, mushrooms in shade, meadow flowers, grass and fern, Thaumaturge flora and mana pods; about one node a chunk at most.
- [ ] Without Dynamic Trees or Botania: no breakage, the pure ending.

<sub>Already covered by automated pack tests: `flora_rules_plan_and_job_record`, `tier4_flora_counts_saplings_landmarks_and_bare_pond`, `tier3_without_botania_has_landmark_and_two_plus_one_saplings`, `saplings_are_thaumaturge_blocks_without_dynamic_trees`, `shade_mushrooms_under_a_roof_and_nodes_at_most_one_per_chunk`</sub>

## 17. Trees grow in front of you

Check id: `phase_5d.grove_trees`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground: stand on open ground first), with an axe in your hand slot.
2. Stay in the finished grove for a game day; chop a landmark and let it fall; /thaumicconcilium qa landmark false 0 0 ~ ~ ~4 shows a variant.

**Expect**

- [ ] Landmarks grow in visible stages, dense apex at the centre, small saplings at the edge; young landmarks mature a stage a game day.
- [ ] All 8 greatwoods and 10 silverwoods look right, fall and drop like ordinary Dynamic Trees; silverwood trunks fatten toward 3.

<sub>Already covered by automated pack tests: `every_landmark_variant_grows_in_stages_to_the_one_shot_tree`, `landmark_entries_follow_the_falloff_the_gates_and_the_day`, `saplings_become_trees_by_bounded_pulses`, `every_landmark_variant_is_a_valid_living_tree`, `twig_leaves_survive_random_ticks_and_growth_oak`</sub>

## 18. The ripple: does the growth look good?

Check id: `phase_5d.grove_ripple`

**Steps**

1. You are staged where you stand (open ground) and the tier 4 ending has been started: you are moved to the crater's lip. Open F3 and look at the server tick time while it grows, then watch it again from about 60 blocks out (press Again for a second run).
2. Once, go far away (past your view distance) while it grows, and come back.

**Expect**

- [ ] The meadow spreads outward at one steady speed (a ring every 4 s); the trees rise a little behind it in small steps, never popping in whole; the whole forest stands about 2 to 3 minutes after sight returns.
- [ ] Leaves never drop and regrow while trees grow (no 'seasons').
- [ ] No lasting stutter. One short hitch the first time a node or hero is placed in a session is known (a one-time warm-up).
- [ ] Trees nobody could see are simply grown when you come back.

<sub>Already covered by automated pack tests: `a_full_size_grove_paints_its_hill`, `an_unloaded_waiting_chunk_never_blocks_a_loaded_one`, `tier4_soil_and_step_timing`, `a_finale_tree_grows_in_small_steps_then_on_to_its_cap`</sub>

## 19. Grove trees grow on to their caps

Check id: `phase_5d.grove_natural_growth`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground). You carry two greatwood saplings.
2. In the finished grove, /tick sprint 72000 (three game days), then look again.
3. Plant a greatwood seed in the grove and one outside it; /tick sprint 72000 again.

**Expect**

- [ ] Heroes keep growing toward 40; the hill's trees grow to their caps (26 beside the heroes, never under 19 at the edge), on the same shapes, never off them.
- [ ] The seed planted in the grove grows into a grove greatwood that stops at 19; the one outside is an ordinary Thaumaturge greatwood.

<sub>Already covered by automated pack tests: `natural_growth_follows_the_template_to_the_cap`, `a_finale_tree_grows_in_small_steps_then_on_to_its_cap`, `thaumaturge_saplings_in_a_grove_become_glade_trees`, `natural_growth_of_each_species_reaches_its_class_height`</sub>

## 20. Seeds of the grove's trees

Check id: `phase_5d.grove_lineage`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground).
2. Break leaves of a grove tree until seeds drop; leave some on the ground for a few minutes; pick others up.

**Expect**

- [ ] Seeds left lying plant themselves and grow as grove trees (the hill's caps).
- [ ] Picked-up seeds are plain Thaumaturge seeds: they stack with ordinary ones and grow ordinary trees outside a grove.

<sub>Already covered by automated pack tests: `a_finale_trees_own_seeds_plant_its_lineage`</sub>

## 21. No decay while the pond has mana

Check id: `phase_5d.grove_no_decay`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with an axe and two spreaders.
2. Watch the grove's trees over a game day (/tick sprint 24000): leaves, twigs.
3. Chop one tree down; then drain the pond completely (spreaders) and watch another day.

**Expect**

- [ ] With mana in the pond, no leaf drops and no twig rots in the grove.
- [ ] A chopped tree's leaves still clear. Once the pond is empty and no node is left, leaves and twigs decay as anywhere else.

<sub>Already covered by automated pack tests: `a_living_grove_keeps_its_leaves_and_twigs`</sub>

## 22. The grove's own trees look and drop as Thaumaturge's

Check id: `phase_5d.grove_species_look`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with an axe.
2. Look at a grove tree's bark, leaves and sapling up close; point Jade at them.
3. Chop one: check the drops. With Sable Trees, watch it fall. Fly away until Voxy draws the grove as far terrain.

**Expect**

- [ ] Bark, rings, leaves and saplings look like Thaumaturge's greatwood and silverwood (leaves take the grove's magical forest tint, as Thaumaturge's own do there).
- [ ] Jade names them Greatwood/Silverwood Tree, Leaves, Sapling. Drops are Thaumaturge's logs, sticks and seeds.
- [ ] Falling with Sable Trees and far rendering with Voxy behave as for other Dynamic Trees trees.

<sub>Already covered by automated pack tests: `the_grove_families_and_species_exist_with_the_deeper_signal`, `template_sets_are_whole_parent_closed_and_in_the_signal_depth`</sub>

## 23. Growth boost

Check id: `phase_5d.grove_growth`

**Steps**

1. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with wheat seeds and saplings.
2. Plant wheat and saplings inside and outside the grove; wait.

**Expect**

- [ ] Crops and trees inside outgrow those outside by about a quarter.

<sub>Already covered by automated pack tests: `crops_in_the_grove_grow_a_quarter_faster`, `trees_in_the_grove_get_the_extra_step_by_mixin`</sub>

## 24. The pond draws mana, then breaks nodes

Check id: `phase_5d.pond_mana_draw`

**Steps**

1. A tier 3 grove of radius 12 with its mana pond is painted where you stand (staged here, on real ground), with a Botania mana pool, a spreader and a bucket.
2. Place the mana pool or hold the spreader touching a pond block; check the water by bucket and walking in.

**Expect**

- [ ] The water does not flow, cannot be bucketed, does not push.
- [ ] At tier 4 the pond starts with 1,000 mana per point of the rite's burden (about 0.34 to 0.6 M) from the moment it stands; tier 3 by its chunks and nodes.
- [ ] A touching pool or held spreader draws mana; past the residual it drains vis from grove nodes, then breaks the weakest node into a rift that spreads taint and pushes the grove back. Only a held spreader draws; nothing otherwise.

<sub>Already covered by automated pack tests: `fluid_does_not_flow_and_cannot_be_bucketed`, `residual_is_sized_by_chunks_and_nodes`, `draws_past_the_residual_drain_node_vis_fullest_first`, `overdraw_breaks_the_weakest_node_into_a_rift_each_step`, `rift_size_scales_with_node_capacity_within_the_clamp`, `spreader_beside_the_pond_fills_from_the_ledger`, `pool_beside_the_pond_gets_nothing`, `nothing_runs_without_draws`, `a_tier_four_pond_is_sized_by_the_burden`</sub>

## 25. Lexicon and research text

Check id: `phase_5d.lexicon_research`

**Steps**

1. You have the Botania lexicon and the Thaumonomicon, and the research up to The Glade.
2. Open the Botania lexicon (Misc) and Thaumonomicon: The Green Translation and The Glade.

**Expect**

- [ ] The lexicon lists the Verdant Capital under Misc and names our tab. The Green Translation states the quarter-per-capital root chance and the endings; The Glade matches.

## 26. Save and quit mid-ending

Check id: `phase_5d.save_load`

**Steps**

1. You are staged where you stand and the tier 4 ending has been started: you are moved to the crater's edge.
2. Save and quit mid-finale and mid-painting; reload. (Mid-rite: the Vessel checks of the previous chapter stage a rite.) Press Again to run it once more.

**Expect**

- [ ] All three resume (the finale ends at once with sight returned, by design).

<sub>Already covered by automated pack tests: `buffer_placer_drive_timer_and_progress_survive_save_and_load`, `aftermath_survives_save_and_load`, `job_resumes_after_save_and_load`, `a_strangle_survives_a_save_and_a_load`, `seed_death_skips_a_missing_seed_and_resumes_after_load`</sub>

## 27. Multiplayer over LAN

Check id: `phase_5d.multiplayer`

**Steps**

1. Host from your game and have a friend join first, standing nearby, then press Again: the tier 4 ending starts where you stand and you are moved to the crater's edge.

**Expect**

- [ ] Capital animation syncs, flash and blindness are per player, the Glade note arrives, roots show.

<sub>Already covered by automated pack tests: `capital_update_tag_carries_drive_side_and_time`</sub>

## 28. Airships over the grove

Check id: `phase_5d.airship_painter`

**Steps**

1. A tier 4 grove of radius 70 is being painted where you stand (staged here, on real ground).
2. Fly a Sable airship over the grove and crater while it paints (the airship is not staged).

**Expect**

- [ ] The airship is unharmed by the painter; no hitch while the grove paints; idle cost nil afterwards.

<sub>Already covered by automated pack tests: `plot_chunks_are_skipped_and_a_plot_hex_gets_no_job`, `finished_jobs_and_empty_levels_cost_nothing`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_5d`).
