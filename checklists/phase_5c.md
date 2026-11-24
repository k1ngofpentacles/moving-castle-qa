# QA: The Vessel (5c)

Chapter id `phase_5c`, 24 checks. In game this is the FTB Quests chapter **QA: The Vessel (5c)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:shield`

## 1. Feeding a tamed rift: every route

Check id: `phase_5c.sink_feed`

**Steps**

1. You stand four blocks from a lesser hex (Barrier Stone centre) holding a tamed rift. Only a lesser hex is a sink: a full hex tames a rift but never takes burden. You carry 10 temporary and 10 normal warp, a thaumometer, Wrath Cages (they carry warp) and a flux goo bucket.
2. Sneak and use the hex with nothing in hand: with the temporary warp first, then clear it (/thaumaturge warp remove temporary 10) and use it with only normal warp.
3. Throw a Wrath Cage onto the hex; pour the flux goo within four blocks. (Not staged: pushing vitium from a Vis Condenser, and standing in a flux aura for a few minutes. Try them by hand if you want those routes.)
4. Hold the thaumometer on the hex now and then to see the rift's size.

**Expect**

- [ ] Each route makes the rift grow (25 up to 75 as the burden nears the threshold); warp is taken temporary first, then normal, never permanent; thrown warp items vanish.
- [ ] The rift eats no blocks while the hex holds it; a wild rift nearby still does.
- [ ] The conversion rates feel about right: roughly three evenings of an active workshop to a break, not one hour and not ten.

<sub>Already covered by automated pack tests: `routes_f1_f2_f3_w1`, `route_w2_item`, `growth_eats_nothing`, `wild_rift_still_eats`, `chained_rift_unchanged`</sub>

## 2. The hex cracks as it fills

Check id: `phase_5c.sink_cracks`

**Steps**

1. You stand four blocks from a tamed lesser hex, with a stack of Wrath Cages. Throw them onto it and look at the ring stones at a third, two thirds, and past the threshold.

**Expect**

- [ ] Three crack states appear on the ring stones, readable at a glance, the last once the hex is strained. A strained hex still transmutes.
- [ ] The look is acceptable as a placeholder (it is retextured runes, not final art).

<sub>Already covered by automated pack tests: `crack_states`, `strained_still_works`</sub>

## 3. A strained hex breaks on the next chunk load

Check id: `phase_5c.sink_break_load`

**Steps**

1. A tamed lesser hex stands four blocks ahead on the ground where you were (staged here, not on a pad: the break cuts a crater of about 14 blocks round it, so stand on open ground first).
2. Throw Wrath Cages onto it until it is past its threshold, then save and quit to the title screen and reload the world (or fly far away and back).
3. Stand near it when it loads.

**Expect**

- [ ] The hex and its rift are gone for good (nothing is put back). After the six-second break a blast crater lies round the spot, four anchor blocks stand on its floor 8 to 12 blocks out, and a dormant Vessel hangs three blocks above the middle.
- [ ] Nobody who fed it is left out: every online contributor is carried to the edge of the arena.

<sub>Already covered by automated pack tests: `break_on_reload`, `pure_rules`</sub>

## 4. A hex in a chunk that never unloads leaks, then breaks when everyone sleeps

Check id: `phase_5c.sink_leak_sleep`

**Steps**

1. It is night and a tamed lesser hex stands four blocks ahead on the ground where you were (staged here: the break cuts a crater of about 14 blocks, so stand on open ground first). You carry a bed and a stack of Wrath Cages.
2. Strain the hex with the cages, keep feeding past its threshold and watch the aura flux in the chunk.
3. Once the flux that leaked out passes a few hundred, place the bed and sleep through the night with every player in it.

**Expect**

- [ ] A strained hex returns about 150 percent of what it is fed as aura flux, and nothing breaks until the leak passes its hidden second threshold and everyone sleeps.
- [ ] Sleeping before that threshold changes nothing.

<sub>Already covered by automated pack tests: `leak_returns_150_percent`, `break_on_sleep`, `sleep_below_leak_threshold_keeps_hex`</sub>

## 5. Contributors are pulled in from any dimension

Check id: `phase_5c.sink_teleport`

**Steps**

1. A tamed lesser hex stands four blocks ahead on the ground where you were (staged here: the break cuts a crater, so stand on open ground first). You carry Wrath Cages.
2. With a friend (LAN), both feed the same hex. Send the friend to the Nether, or the Causal Bouillon, before the break.
3. Let it break.

**Expect**

- [ ] The friend is taken out of their dimension to a safe spot at the arena edge (15 blocks out), not into rock or lava, and the arena is the overworld one.

## 6. An absent contributor pays when they log in

Check id: `phase_5c.sink_absent`

**Steps**

1. A tamed lesser hex stands four blocks ahead on the ground where you were (staged here: the break cuts a crater, so stand on open ground first). You carry Wrath Cages.
2. A friend feeds the hex, then logs off. Strain it with the cages yourself and let it break while they are away. They log in.
3. Compare with a friend who fed more or less.

**Expect**

- [ ] They get temporary warp in proportion to their share of the burden, a warp event fires at once, and a message tells them something has come due. It happens once.
- [ ] Their research book shows the field note The Vessel (unfinished).

<sub>Already covered by automated pack tests: `absent_debt_paid`, `note_three_appears_at_the_break_and_completes_at_the_subdue`</sub>

## 7. Waking the Vessel and leaving it

Check id: `phase_5c.fight_wake`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel hanging over the middle, with its four anchors round it. Walk in.
2. Once it is awake, fight a while, then walk well away (more than 48 blocks: break through the glass rim, or use /gamemode creative to fly out) for a minute or more and come back.

**Expect**

- [ ] Within 16 blocks it wakes with a swell and a rumble; a boss bar appears. Its starting Mass grows with the players near it (8 solo).
- [ ] Left alone it goes dormant and keeps its Mass; coming back wakes it where it was.

<sub>Already covered by automated pack tests: `pull_nothing_when_dormant`, `dormancy_keeps_state_and_wake_restores`, `start_mass_counts_players_within_48`</sub>

## 8. The pull: fair, never rubber-banding

Check id: `phase_5c.fight_pull`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a shield, the ancient stone, a sword and a bow.
2. Wake it by walking in. Walk straight out from it at 4, 8 and 12 blocks, then jump near it. Do it again with a second player on LAN watching you.
3. Stand on a path of the stone from the kit (place it yourself), and use the shield.

**Expect**

- [ ] Walking out at 4 blocks is hard but possible; jumping near it is clearly a mistake. The pull is smooth on your own screen, and the watcher sees you move without snapping back.
- [ ] Weapons and arrows do not hurt it; arrows and items that reach it feed it. It eats only taint blocks and loose plants, never ordinary terrain.

<sub>Already covered by automated pack tests: `pull_pure_rules`, `pull_item_gains_accel`, `pull_on_player_factors`, `weapons_do_nothing_kill_works`, `horizon_eats_and_feeds`, `horizon_hurts_never_kills_and_throws`, `eating_gain_cap_per_window`</sub>

## 9. Drawing at the anchors, clots and the bat-back

Check id: `phase_5c.fight_draw_clots`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword and a shield.
2. Wake it and use the wand on an anchor. Hold still at the anchor while the tether builds (two draws, then it cools).
3. When a clot winds up at you, hit it back with your sword toward the hole. Miss one on purpose.
4. Draw at all four anchors, then do the whole fight alone and, if you can, with two others.

**Expect**

- [ ] Each draw takes Mass off; an anchor cools after two draws and shows it. The clot's wind-up is readable (it grows, a ring closes) and the bat-back is hittable. A batted clot staggers the Vessel: no pull for four seconds and drawing goes twice as fast.
- [ ] A missed clot leaves goo and costs you the tether when it hits. Players who drew or batted count as participants.

<sub>Already covered by automated pack tests: `tether_forms_draws_and_drops_mass`, `tether_two_draws_cool_the_anchor`, `tether_breaks_on_leaving_and_loses_progress`, `clot_batted_staggers_and_doubles_draw`, `clot_miss_leaves_goo_and_counts`, `clot_hit_hurts_and_breaks_tether`, `participants_by_swarm_damage_and_presence_rule`</sub>

## 10. Phases, the gulp and how long it takes

Check id: `phase_5c.fight_phases`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword, a bow, a shield and the ancient stone.
2. Wake it and fight it from full Mass down. Notice the swarms at the middle phase and the swell before the gulp in the last.
3. Note how long the whole fight took solo, and with three.

**Expect**

- [ ] The phases change at the memo's Mass; swarms appear (never more than three). The gulp swells for three seconds, so there is time to reach a stone or an anchor before the pull triples.
- [ ] A solo fight takes some minutes, not seconds and not an hour; three players is quicker but still a fight. Anything wildly off is a balance note.

<sub>Already covered by automated pack tests: `phases_switch_and_spin_up_spawns_swarms`, `gulp_swells_then_pulls_and_stagger_cancels`</sub>

## 11. An airship near the Vessel (Sable)

Check id: `phase_5c.fight_airship`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel (creative, so you can fly). The airship is not staged: bring a Create airship on Sable physics within 16 blocks of the Vessel once it is awake, with and without a crew aboard. Also park one and leave it.

**Expect**

- [ ] The ship is drawn toward it without tumbling wildly (a slow turn is fine); crew aboard are not pulled off the deck; a parked ship is not thrown.
- [ ] A dormant Vessel does not touch it.

<sub>Already covered by automated pack tests: `sable_impulse_function_and_caps`, `sable_ship_near_moves_toward_the_hole_far_does_not`</sub>

## 12. How the Vessel looks in each state

Check id: `phase_5c.look_states`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel. Look at it in daylight and again at night (/time set night), walk round it and see the disc edge-on.
2. Walk in to wake it and look at it feeding, in spin-up and in collapse (fight a while). The quiescent state is staged by the Draining check below: look at it there.

**Expect**

- [ ] A black core with a ring; the accretion haze reads as a tilted disc whose near half passes in front. The sky dims near it while it feeds, and it is readable but not a screen-filler.
- [ ] Quiescent it is smaller and quiet, with four light ribbons running from the anchors to the hole. The vignette and dim violet bar show only near it.

## 13. Your tether, first and third person

Check id: `phase_5c.look_tether`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand. Wake it by walking in and draw from an anchor.
2. Look at the ribbon in first person, then switch to third person (F5) and look at it from behind and from the side, and from a second player's view.

**Expect**

- [ ] First person: it starts at the wand hand and ends at the hole. Third person (the harness could not measure it, the body hides it): it still leaves the hand, stays violet rather than washed white, and does not cut through your body strangely. A friend's tether looks the same from outside.

## 14. The anchors: broken pieces of the hex, and the break

Check id: `phase_5c.look_shards`

**Steps**

1. A lesser hex stands six blocks ahead on the ground where you were (staged here, on real ground: the break carves a crater of about 14 blocks), with a chest of diamonds and a block of obsidian beside it inside the crater radius. You carry a wand and an anchor item (look at it in the hotbar).
2. Standing where you arrived, run /thaumicconcilium qa vessel ~ ~-1 ~6 breaking and watch the six seconds: with Sable in the pack the hex itself lifts off as a sub-level; use breaking_standin instead of breaking to see the version without Sable (restage first).
3. Try to wake the Vessel during the sequence (walk up to it), then look at the crater and where the four anchors landed.
4. Walk onto an anchor (no jump needed), draw from each of the four with the wand, and watch the glyphs and the hovering shard as an anchor is used up, cools and is tethered. Look again at night. Stage it again for a second break.

**Expect**

- [ ] The break: the Vessel shows only its ring and a thin haze while the hex rises into it (2 s), spins up with its runes lit (2 s) and cracks, runes whitening, with beams of white light (1 s). Then it bursts: streaks of light and glyphs fly out, the black closes, four shards tumble out along arcs and the anchors form exactly where they land, with dust and a thud. The Vessel does not wake until they are down. The hex is gone for good.
- [ ] The blast hurts and throws outward anything within the crater radius, hardest near the middle (armour and Blast Protection help), and nothing beyond it. The crater: carved as a ring spreading from the centre in under two seconds, never at the landing spots first, wider than the farthest anchor (about 14 blocks), a shallow bowl about 4 deep in the middle with a ragged edge and a low mound of the broken material (1 to 2 high) on its rim. Nothing drops from the destroyed blocks, but the chest spills its items; obsidian and tougher blocks are left standing.
- [ ] The four anchors stand in a rough circle round the hex: about a quarter turn apart and at about the same distance (8 to 12 blocks).
- [ ] Each anchor is a jagged, tilted piece of the hex itself: the same dark stone with an empty carved rune and a crack, no paint or glow on it; the four of one Vessel differ, and another Vessel shows another set (eight shapes in all). The top is half a block high: you step onto it.
- [ ] The runes leave the stone as glyphs that rise, sway, flicker and turn as they fade: a steady violet stream at two charges, a sparse one at one charge, only a small orange ember now and then (and smoke, an ember crack) while cooling, quick white glyphs while someone draws.
- [ ] A small stone shard hovers above each anchor, bobbing and turning slowly like an item on an infusion pedestal, each at its own height and rhythm; it spins faster while tethered, lies on the stone while cooling, rises above your head while you stand there, and the ribbon starts at it. The item reads as a rock with a shard, not a cube.

<sub>Already covered by automated pack tests: `a_vessels_four_anchors_carry_four_distinct_shapes`, `anchor_spokes_form_a_rough_circle`, `break_sequence_lands_four_anchors_on_the_radial_spots`, `interrupted_break_finishes_at_once_on_load`, `sable_break_holds_the_hex_and_leaves_no_sub_level`, `the_burst_carves_a_crater_with_a_rim`, `a_crater_cut_short_is_finished_on_load`, `a_full_hex_never_becomes_a_sink`</sub>

## 15. Darkness, then Blindness, near the hole

Check id: `phase_5c.look_darkness`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with its anchors 8 to 12 blocks round it.
2. Walk in to wake it and approach slowly, then walk away; stand at the anchors (8 to 12 out).
3. Check the same near the Vessel while it is still dormant (before you walk in) and, from the Draining check, a quiescent one.

**Expect**

- [ ] Inside about 8 blocks the world dims (Darkness); inside about 4 you go blind (Blindness); the anchors stay readable; both end a few seconds after you step back.
- [ ] A dormant or quiescent Vessel never darkens you. The halo and the edge vignette still show. It feels like a warning, not a punishment.

<sub>Already covered by automated pack tests: `darkness_and_blindness_follow_the_radii_while_active`, `no_darkness_when_dormant_or_subdued`</sub>

## 16. Sounds, boss bar, and with shaders

Check id: `phase_5c.look_sound_shaders`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword, a bow and a shield. Sound on.
2. Play through a wake, a gulp, a stagger, an anchor cooling and becoming ready, and a horizon throw.
3. Repeat the wake and the quiescent view with a shader pack (Iris) on, if you use one.

**Expect**

- [ ] Every event has a sound and the hum changes with the state; none is harsh, subtitles read sensibly.
- [ ] With shaders the core and ribbons still draw (this has never been tried).

## 17. The rite needs the research

Check id: `phase_5c.rite_locked`

**Steps**

1. You stand five blocks from a quiescent Vessel with its four anchors round it. You have none of the research (the staging reset it) and carry a wand.
2. Use the wand on one of the four anchors.
3. Then get Drawing It Out: it needs The Vessel note (subdue a Vessel, or /thaumicconcilium qa research) and Thaumaturge's eldritch research (Unlock Eldritch, which needs the Void Seed). Try again after only one of the two.

**Expect**

- [ ] Without it the anchor tells you that you do not know how to draw from it and nothing happens, even with only one of the two researches.
- [ ] Drawing It Out appears in the Thaumic Concilium tab, right of the Hex of Predictability, once its parents are done; it costs warp 3 to learn.

<sub>Already covered by automated pack tests: `drain_needs_the_research`</sub>

## 18. Draining it, one unit at a time

Check id: `phase_5c.rite_drain`

**Steps**

1. You stand five blocks from a quiescent Vessel with its four anchors round it, and have Drawing It Out. Use the wand on an anchor and hold the wand in your hand next to it.
2. Wait through one unit (about a minute), then up to five. Try the other three anchors with a friend.
3. Check your warp (thaumonomicon or /thaumaturge warp info) before and after.

**Expect**

- [ ] A tether runs from the anchor to the hole. Each full minute the Vessel's charge drops by one of 20 and you gain 1 temporary warp; at every fifth unit 1 normal warp as well. Four anchors together drain it faster; a full drain by one person takes about 20 minutes.
- [ ] The pace feels like a slow rite you can do between other jobs, not a chore.

<sub>Already covered by automated pack tests: `each_unit_gives_warp_every_fifth_normal`, `rite_pure_rules`</sub>

## 19. Pausing and resuming, across a save

Check id: `phase_5c.rite_pause`

**Steps**

1. You stand five blocks from a quiescent Vessel with its four anchors round it, and have Drawing It Out.
2. Start a drain with the wand on an anchor, wait half a unit, then put the wand away (or walk away). Save and quit, reload, and go back to the anchor (staging again would rebuild it: do not press Again).

**Expect**

- [ ] The tether lets go at once. The charge and the unit's progress are kept; using the wand again carries on where it was. Nothing runs while nobody drains (no particles, no fibre growth, no goo).

<sub>Already covered by automated pack tests: `pause_and_resume_keep_charge_across_save_and_load`</sub>

## 20. While it drains the world answers

Check id: `phase_5c.rite_taint`

**Steps**

1. You stand five blocks from a quiescent Vessel with its four anchors round it, with a wand and a thaumometer (the pad is only 25 blocks wide, so the ring is cut off at its edge).
2. Drain for several units with the wand on an anchor. Watch the ring around the Vessel as units pass (fly up and out for a view), and the anchor you are using.
3. Pause the drain and wait a few minutes.

**Expect**

- [ ] Taint fibres and a blight spread outward from the Vessel in a ring that widens from about 8 to 24 blocks as units pass; goo spills at the anchor you are using.
- [ ] As soon as you pause, no new fibre appears, and the blight stops being held by the Vessel (it starts to wither at its own pace).
- [ ] The spread is dramatic but does not lag the game.

<sub>Already covered by automated pack tests: `taint_origin_and_pulses_only_while_draining`</sub>

## 21. The last unit leaves a Taint Seed

Check id: `phase_5c.rite_seed`

**Steps**

1. You stand five blocks from a quiescent Vessel (charge 20, no missed clots) with its four anchors round it, with a wand and a sword; difficulty is easy so the seed can spawn.
2. Drain it to the end with the wand (about 20 minutes alone, quicker with a friend on the other anchors). Do the same once after a fight where you let several clots land (fight_phases stages one).
3. Kill the seed and wait a few minutes.

**Expect**

- [ ] The Vessel is gone; a Taint Seed stands where it hung: a plain one for a clean fight, a Prime Taint Seed from a score of 12 (one point per missed clot, one per 15 goo spills at the anchors), with more health and reserve the higher the score. It lives until you kill it.
- [ ] When it dies the blight around it withers.
- [ ] The four anchor shards crumble into rubble particles with a stone-break sound as the last unit drains, and their blocks are gone.

<sub>Already covered by automated pack tests: `last_unit_leaves_a_plain_seed_and_removes_the_vessel`, `many_missed_clots_leave_a_prime_seed`, `seed_scale_follows_clots_and_goo`</sub>

## 22. Motes for everyone who took part

Check id: `phase_5c.rite_motes`

**Steps**

1. You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, sword, bow, shield and ancient stone.
2. Subdue it with a friend (both draw or bat clots). Have one more friend who fed the hex stand near for ten seconds, and one who took part log out before the end.
3. Fill your inventory completely with stone before Mass reaches zero in one run.
4. Compare motes with each other over a few fights.

**Expect**

- [ ] At Mass 0 every participant gets a Primordial Mote in the inventory (dropped at the feet if full), about one in ten gets a second. The player who logged out gets theirs on login. Someone who did nothing gets nothing.
- [ ] The field notes The Vessel (completed) and Primordial Mote appear.

<sub>Already covered by automated pack tests: `motes_reach_every_participant_online_full_and_offline`, `second_mote_rolls_at_ten_percent_seeded`</sub>

## 23. The Flesh Crucible becomes craftable

Check id: `phase_5c.rite_flesh`

**Steps**

1. You have the Material Peeler and Quicksilver Crucible research, and the whole Flesh Crucible infusion kit: three motes, the Quicksilver Reactor (the catalyst), a Nether Shard, three Crimson Plating and Bright Nitor.
2. Build an infusion altar yourself (the pad is empty) and set up the Flesh Crucible infusion from the research page.

**Expect**

- [ ] The infusion accepts the three motes with the other components and makes a Flesh Crucible; nothing else blocks it.

<sub>Already covered by automated pack tests: `flesh_crucible_needs_only_motes_and_its_research`</sub>

## 24. The field notes: when they appear and how they read

Check id: `phase_5c.notes_book`

**Steps**

1. You have no research (reset) and stand on the ground where you were, with a tamed lesser hex four blocks ahead (staged here: the break carves a crater, so stand on open ground first) and Wrath Cages.
2. Finish the Hex of Predictability research (the staging cannot grant it without the note appearing early); feed the hex past a quarter of its threshold; let it break; subdue the Vessel; receive a mote.
3. Open the Thaumic Concilium tab after each and read the new entry, then read all five once more in order.

**Expect**

- [ ] Rifts That Hold arrives with the hex research (warp 1); What It Keeps once a hex you fed passes a quarter; The Vessel appears at the first break and completes at the first subdue; Drawing It Out when its parents are done; Primordial Mote with the first mote.
- [ ] They sit in one row, right of the hex entry, with the book's lines drawn sensibly. The prose reads as dry notes growing uneasy and the rules are stated plainly.

<sub>Already covered by automated pack tests: `note_one_comes_with_the_hex_research_and_on_login`, `note_two_when_a_hex_you_fed_passes_a_quarter`, `note_three_appears_at_the_break_and_completes_at_the_subdue`, `note_three_completes_on_login_for_a_participant_who_was_away`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_5c`).
