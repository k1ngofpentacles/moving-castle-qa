# QA: Flesh, Peeler and the Crimson Dagger (5b)

Chapter id `phase_5b`, 16 checks. In game this is the FTB Quests chapter **QA: Flesh, Peeler and the Crimson Dagger (5b)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumicconcilium:crimson_dagger`, `minecraft:shield`

## 1. Ethereal no-clip, with a second player watching (LAN)

Check id: `phase_5b.ethereal_lan`

**Steps**

1. You wear the full Pontifex Robe in survival; a stone wall stands 5 blocks ahead, a stone ceiling 6 blocks overhead and a pig beside you. Open the world to LAN and let a second player join (it is not staged for them). Press L (or run /thaumicconcilium qa ethereal on).
2. Fly into and through the stone wall, up through the ceiling, and down below the floor. Sneak to descend. The second player watches you the whole time.
3. Try breaking a block, hitting the pig and using an item while ethereal, then /thaumicconcilium qa flesh 0 and check your health bar. Step off the pad edge into the void.

**Expect**

- [ ] You pass through walls with no stutter or rubber-banding for you, and the second player sees you pass through walls too (no snapping back, no being pushed out).
- [ ] No block overlay when your head is inside stone. Damage and healing do nothing. Each action you take gains flesh and the maximum hearts shrink.
- [ ] Falling into the void does not hurt you: you can fall forever (deliberate, a PvP blink). Switching the robe toggle off ends the state.

<sub>Already covered by automated pack tests: `ethereal_flight_and_idle`, `ethereal_damage_and_heal`, `flesh_gain_rules`, `flesh_max_health_modifier`, `respawn_rule`, `robe_toggle_on_state`, `state_round_trip`</sub>

## 2. Ethereal Shackles: projectile and the chained hand

Check id: `phase_5b.chained_hand`

**Steps**

1. A Crimson Paladin stands 11 blocks ahead and will cast at you; you are armed in survival (the robe is in your hotbar).
2. Watch the shackles fly, then look at your own hand while chained, and wait it out (5 seconds).
3. Wear the robe and turn the toggle on (L): the chained hand shows for a moment there too.

**Expect**

- [ ] The thrown shackles spin as they fly. While chained your hand is the shackled arm with a chain, blue haze rising as the timer runs out, and you cannot break, place or attack.
- [ ] The hand returns cleanly when the chain ends, with no leftover or flicker.

<sub>Already covered by automated pack tests: `chained_blocks_and_counts_down`</sub>

## 3. Dagger: raise, stun and stab (feel and animation)

Check id: `phase_5b.dagger_feel`

**Steps**

1. You wear iron armour with a shield and hold the dagger; Death Gaze is on you. A Paladin, an Archer, a Ranger and a Thaumaturge Knight stand 8 blocks ahead (they will advance; the Pontifex spawn egg is in your hotbar).
2. Right-click the dagger: a short raise (0.75 s). Hold it raised, looking at each mob and then the Pontifex if you spawn it.
3. Release after a complete raise and stab straight away with left-click. Try stabbing again straight after, and a third time inside a second.
4. Pending the dagger animation (D8): note how the raise, the point and the stab read in first and third person.

**Expect**

- [ ] The raise feels quick but deliberate. Knights, Clerics and Archers freeze in place and stop attacking while the gaze holds them; Paladins and Rangers are slowed; the Pontifex is unaffected.
- [ ] The stab follows the release within a beat and hits fast for small damage. Spamming has an obvious rhythm (the raise is the stab's cooldown).
- [ ] Animation: the poses read clearly and match the chosen option once D8 is merged (pending merge).

<sub>Already covered by automated pack tests: `trunk_dagger_data`, `trunk_raise_stun_slow_tiers`, `trunk_bleed_requires_raise`</sub>

## 4. Bleed and Crimson Blood

Check id: `phase_5b.dagger_bleed`

**Steps**

1. You hold the dagger and a diamond sword; three Crimson Archers that stand still and a pig are 4 blocks ahead. Stab the left Archer once, then twice more inside the 3-second window. Watch its health and the effect icon. Let it bleed out, and kill the middle one by a stab.
2. Hit the right Archer with the sword to the death, and the pig with the dagger.

**Expect**

- [ ] Each stab adds a counter up to 3; at the window's end the target takes 1 damage per counter, one burst per window, not a drip.
- [ ] A cultist killed by the dagger or by the bleed drops exactly 1 Crimson Blood. A sword kill or the pig drops none.

<sub>Already covered by automated pack tests: `trunk_bleed_stacks_and_window`, `trunk_blood_from_bleed_kill`, `trunk_blood_from_dagger_kill_only`</sub>

## 5. Self-cut for LP (Neo Vitae)

Check id: `phase_5b.dagger_selfcut`

**Steps**

1. You hold the dagger and an Ara Vitae stands 4 blocks ahead. Open it to see its LP, then sneak + right-click with the dagger several times. Then walk more than 8 blocks away (to the pad edge) and try the same.

**Expect**

- [ ] Each cut costs 1 health point and adds LP at Neo Vitae's own self-sacrifice rate, with a short cooldown. Out of range it only shows an action-bar hint.

<sub>Already covered by automated pack tests: `trunk_self_cut_gate`</sub>

## 6. Enchanted: sacrifice damage

Check id: `phase_5b.dagger_enchanted`

**Steps**

1. You hold the dagger and a diamond sword; two zombies that stand still are 5 blocks ahead. With Enchanted in the pack, stab one and hit the other with the sword and compare the hit and the bleed message. (No Enchanted-specific mob is staged: swap in one by hand if you have one.)

**Expect**

- [ ] The hit and the bleed read as Enchanted's sacrifice damage (death message, mod effects). Damage scales with the swing cooldown and nothing sweeps or crits.

<sub>Already covered by automated pack tests: `trunk_dagger_hit_damage_type`</sub>

## 7. Flesh Crucible: sip and smelt

Check id: `phase_5b.crucible_flesh`

**Steps**

1. A Flesh Crucible stands 3 blocks ahead and you hold Mad Thaumaturge, pig and zombie spawn eggs; you have flesh 0. Stand in the crucible with flesh 0: nothing happens.
2. Give yourself flesh (/thaumicconcilium qa flesh 10), then stand in the empty crucible: nothing. Spawn a Mad Thaumaturge beside it and push or lead it into the crucible to smelt it: it vanishes, the block stays a Flesh Crucible and its store gains 2 (up to 64).
3. Stand in the filled crucible with flesh: each tick sips 1. Also drop a pig and a zombie into an empty crucible.

**Expect**

- [ ] If a store can be had: while you have flesh and the store has aspect, every tick costs 1 flesh and 1 aspect with a gore sound, and your health bar regrows as the flesh falls.
- [ ] A smelt leaves the Flesh Crucible in place with 2 more aspect (faithful, checked in the 1.7.10 game); it never turns into a reactor. Other creatures take 1 damage about twice a second. A powered crucible does nothing.

<sub>Already covered by automated pack tests: `crucible_sip`, `crucible_smelt_and_cap`, `crucible_burns_others`, `crucible_recipe_present`, `trunk_smelt_fills_and_stays`, `trunk_sip_every_tick`, `trunk_damage_once_per_ten_ticks`</sub>

## 8. Material Peeler: summon, touch and burst

Check id: `phase_5b.peeler_summon`

**Steps**

1. A chained rift over a hex stands 5 blocks ahead; you hold Primordial Life and the robe pieces. Throw one Primordial Life into the rift by hand, then wait for the rift to collapse.
2. Walk into the Peeler; then wear the full Pontifex Robe with the toggle on and walk into it again.
3. Break one hex block under it, and wait.

**Expect**

- [ ] The Peeler appears where the rift collapses, two blocks above the hex, and stays put, solid. An ambient sound plays now and then.
- [ ] Touching it toggles you ethereal with nausea about every second; with the robe toggle on you are not affected. With the hex broken it bursts, tainting the ground around it.

<sub>Already covered by automated pack tests: `bursts_without_hex`, `survives_above_hex`, `touch_flips_ethereal`, `primordial_life_route`, `note_resolves_to_research`</sub>

## 9. Peeler of Matter: the whiter rim

Check id: `phase_5b.peeler_rim`

**Steps**

1. A Peeler of Matter hangs above a hex 6 blocks ahead, standing in for the real summon. Look at it from close and far, against sky, a cave wall (dig one) and at dusk (/time set night). Walk around it. If you use Iris, try a shader pack as well.

**Expect**

- [ ] A pale halo wraps the starry cube, near white-blue over daylight sky; the core is dark with stars. The glow is smooth (it has no glitter, by decision).
- [ ] No flicker, no square edges, and nothing breaks under a shader pack.

## 10. Crimson Raid spell and Crimson Initiation

Check id: `phase_5b.raid_spell`

**Steps**

1. You wear the full Pontifex Robe; a wand, two blank foci, the dagger and a stick are in your hotbar; a focal manipulator stands ahead to the right and two still Mad Thaumaturges ahead to the left. In the manipulator, inscribe a focus with the Crimson Raid part (complexity 22, so it needs an advanced focus or better: use the best one the manipulator accepts). Cast it at a block, then cast again at once, then with one robe piece removed.
2. Stand clear and watch the portal and its cultists. Wait for it to end (about 20 seconds).
3. Initiation: in the full robe, right-click a Mad Thaumaturge with the dagger several times, with the stick, and with an empty hand.

**Expect**

- [ ] A Lesser Crimson Portal opens at the impact point and its cultists attack everyone but you; the second cast does nothing while the first portal lives; a partial robe does nothing but spend the cast. The portal vanishes quietly after about 20 seconds.
- [ ] The dagger converts a Mad Thaumaturge into a Crimson Knight, Cleric or Paladin (roughly a third each), equipped. The stick and the empty hand do not.

<sub>Already covered by automated pack tests: `raid_needs_robe_and_one_portal`, `raid_portal_despawns`, `initiation_needs_blade_and_robe`</sub>

## 11. The Offertory: the chain, the offerings and the drain

Check id: `phase_5b.offertory_rite`

**Steps**

1. An infusion altar stands 7 blocks ahead: matrix over a centre pedestal, ring of pedestals around it. The Crimson Rites, a zombie brain, 2 tallow, a phial, a bone, a void sword and rotten flesh are in your hotbar; creative jars of every aspect stand behind the altar and supply the essentia it needs (humanus, ordo, vinculum). Put the Rites in the centre and a ring of brain, tallow x2, phial, bone and void sword on the pedestals. Do not put any offering out yet.
2. Right-click the matrix to begin. Watch the chain, your health and the action bar. Within the first 40 ticks keep rotten flesh ready; when the matrix demands an offering, place it on a free pedestal in the ring and keep going.
3. Run it again and miss one demand on purpose; then again, and let your health fall to the floor; then again, and walk 12 blocks away.
4. Pending merge (D1-c2): offerings are strictly human flesh (Crimson Blood, zombie brain, rotten flesh, fleshy derivatives); beef, pork and spider eyes are refused.

**Expect**

- [ ] A chain rises from the matrix, binds you at the chest and pulls you back if you walk past 6 blocks; you lose about 1 HP per second, never through armour. The demanded item floats above the matrix; a met demand eats the offering, flicks the chain to its pedestal and pauses the drain.
- [ ] A missed demand bites 5 HP and doubles the drain; at the health floor the chain snaps with a reason on the action bar and you get Weakness I. You never die from the ritual itself (mobs and lava still can).
- [ ] Success: the dagger appears and the Rites is spent. Failure: the Rites drops back and is reusable.
- [ ] Putting an offering out before the start stops the recipe. A rite with another ring, or no session, never starts the minigame.

<sub>Already covered by automated pack tests: `minigame_opens_for_the_dagger_and_binds_the_starter`, `minigame_not_for_another_infusion`, `minigame_not_for_a_wrong_ring`, `minigame_offering_before_the_start_blocks_the_recipe`, `minigame_drains_the_binder_only_and_demands_at_40`, `minigame_offering_is_eaten_and_pauses_the_drain`, `minigame_wrong_and_ring_items_are_not_eaten_and_a_miss_bites`, `minigame_snaps_at_the_health_floor`, `minigame_snaps_when_the_player_is_far`, `minigame_ritual_damage_never_kills_but_mobs_and_lava_land`, `minigame_hard_gate_returns_the_rites`, `minigame_saved_data_round_trip`, `minigame_offering_tag_and_recipe_data`</sub>

## 12. The Offertory: helpers and golems

Check id: `phase_5b.offertory_golems`

**Steps**

1. The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it) with the offering items in your hotbar (a second player must join over LAN; it is not staged). Run the rite and have the helper place the offerings while you stay bound. Try a golem with a seal on a pedestal if you have one. Then let the chain snap and see whether the helper can take over.

**Expect**

- [ ] A helper's offerings count; golems can serve the pedestals once the craft has begun. On a snap the chain does not pass to the helper (helpers assist only).
- [ ] The chain, the icon above the matrix and the flick read the same for the second player.

## 13. The Offertory: the Yank (pending merge: D1-c2)

Check id: `phase_5b.offertory_yank`

**Steps**

1. The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it) with the offering items in your hotbar. Run the rite on this moderately stable altar and wait for a native instability event. Watch for the telegraph about a second before it, then see where you end up.

**Expect**

- [ ] A clear telegraph (about 20 ticks) warns of the Yank; then you are pulled to the altar and fully Chained for 3 seconds (first-person shackles, no item use). Helpers or golems have to serve the pedestals meanwhile.
- [ ] The drain keeps its pace; the Yank alone never kills you.

## 14. The Offertory: a snap opens a Crimson Raid, and the champion (pending merge: D1-c2)

Check id: `phase_5b.offertory_snap_raid`

**Steps**

1. The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it); you are in survival with armour and the offering items. Run the rite and let the chain snap on purpose (let your health fall to the floor). Take stock of the room.
2. Fight the raid: cultists and a Crimson Paladin champion with a boss bar. Let the raid kill you before you hold the dagger, then again while you hold it.
3. Win once: kill the champion and take the dagger from the pedestal.

**Expect**

- [ ] The snap still completes the rite: the dagger lies on the pedestal and a hostile persistent raid opens in the room, with the champion and its boss bar.
- [ ] If the raid kills the binder before or while they hold the dagger, the champion takes it and drops it guaranteed when it dies. A raid that is beaten leaves the dagger with the winner.
- [ ] Raid and champion survive a world restart, and nothing ticks when no rite is running.

## 15. Crimson Plating: the Gilded Cult Plate

Check id: `phase_5b.plating_recipe`

**Steps**

1. The infusion altar stands 7 blocks ahead, with creative jars of every aspect behind it; you hold an iron block, 2 Crimson Blood and 4 gold nuggets. Open the Crimson Initiation research page and read the plating entry. Build the infusion: iron block in the centre, the blood and nuggets on the ring; the jars behind the altar supply the essentia (metallum 64, victus 32, praemunio 32).
2. Run it. Then press Again (which resets research) and try it without the research.

**Expect**

- [ ] The recipe shows on the research page with its ring and costs; the infusion runs at low instability (2) and yields 9 Crimson Plating; the item and its tooltip read well.
- [ ] Without Crimson Initiation the recipe will not run.

## 16. Cult gear aspects and the interpreter

Check id: `phase_5b.cult_aspects`

**Steps**

1. You are in creative with every item to check in your inventory. Scan, or open the aspect view, for: Thaumaturge's crimson blade, Crimson Rites, a captain helm and chest, a ranger helm, chest and legs, and our dagger, Crimson Blood and Crimson Plating. Also the crimson plank, crimson stem and the crimson cult banner.
2. Glance at the other mods' crimson items.

**Expect**

- [ ] The cult items show cult aspects (humanus, alienis, aversio, a little metallum) and no wood or herba. The blade is metal-and-menace, not wood.
- [ ] Crimson planks and stems keep their plant aspects. The crimson banner may still read as wood (known miss, Aspect Interpreter 1.8.0).

<sub>Already covered by automated pack tests: `items_have_aspects`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_5b`).
