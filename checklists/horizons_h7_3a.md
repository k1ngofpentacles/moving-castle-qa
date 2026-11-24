# QA: Horizons H7-3a: the plane's features

Chapter id `horizons_h7_3a`, 5 checks. In game this is the FTB Quests chapter **QA: Horizons H7-3a: the plane's features**; each check there has a green "Set up this check" line that builds its test site.

## 1. The feature blocks

Check id: `horizons_h7_3a.feature_blocks`

**Steps**

1. You stand in survival in front of an Eye Cluster, a Bone and a Lump of Flesh, with three spikes beyond them: a metal one on the grass, a wooden one under a stone slab and a toothed one on a stone wall. Your hotbar holds a diamond pickaxe and a Fortune III one.
2. Break each of the three blocks (with and without Fortune; place them again from the drops). Walk into each spike, then break the block a spike stands on.

**Expect**

- [ ] The Eye Cluster is a purple-pink block with staring eyes and drops three to five spider eyes; the Bone is pale bone and drops three to five bones; the Lump of Flesh is a red-pink lump and drops rotten flesh (the original dropped bones, a copy slip).
- [ ] A spike is the original's cone (a metal, a wooden and a toothed one) that points away from the block it is placed on, on any of the six sides; it hurts like a cactus (one point, with the usual hit pause) when you stand in it, and drops itself when the block behind it goes.

<sub>Already covered by automated pack tests: `block_drops_and_the_flesh_fix`, `spikes_hurt_mount_on_any_solid_side_and_dust_drags`</sub>

## 2. Crystals and the Deep Crystal

Check id: `horizons_h7_3a.crystals`

**Steps**

1. You stand in front of a row of the sixteen dye Crystals, white to black, and a small stone room beyond it with a Deep Crystal inside (door straight ahead).
2. Look at the Crystals (place a few more of one colour side by side to check for seams) and at the Deep Crystal in the dark room.

**Expect**

- [ ] Each crystal is a faceted translucent block in its dye colour (white to black), neighbouring crystals of one colour show no seams. The Deep Crystal glows (light 15) and its texture shimmers slowly.

<sub>Already covered by automated pack tests: `block_drops_and_the_flesh_fix`</sub>

## 3. Features of a charnel plane

Check id: `horizons_h7_3a.plane_features`

**Steps**

1. You stand two blocks from the rift of a charnel plane.
2. Walk in, then walk or fly across the plane: the surface, the ravine, the caves. Look for the Primordial Fossil ribs in the boundary wall (make more planes with /thaumichorizons plane preset forge and storm and look at each).
3. Break a Primordial Fossil: the research entry Primordial Fossils appears in the Horizons tab.

**Expect**

- [ ] Eyes, bone piles, a ribcage or two, pink lumps of flesh, pale dust drifts and rings of teeth (a maw) lie on the ground in a density that reads as dressing, not clutter; one narrow ravine cuts the ground. Caves hold toothed spikes on their floors and ceilings, eyes, bone beds and geodes.
- [ ] The fossil is dark with green veins, breathes smoke from its exposed faces and looks like part of something larger coming out of the wall; nothing stands within a few blocks of the arrival crater.
- [ ] A storm plane shows crystal spires in colours that match its aspects, and crystal geodes with Deep Crystal in the lower caves; a forge plane shows metal spike patches and a ravine. On a plane whose top layer is water the features stand on the lake floor.

<sub>Already covered by automated pack tests: `features_follow_their_drivers_in_the_three_recipes`, `nothing_lands_near_the_pad_or_at_the_shell`, `fossils_follow_their_chance_and_stay_inside_the_shell`, `ravines_cut_the_ground_and_lake_floors_get_features`, `features_are_deterministic_and_paint_into_chunks`</sub>

## 4. Meat and Mercurial Slimes

Check id: `horizons_h7_3a.slimes`

**Steps**

1. You stand in survival on easy, holding a sword and the two slime spawn eggs, two blocks from the rift of a charnel plane (it holds flesh).
2. Use both eggs here, fight a large slime of each and look at the pieces. Then walk into the plane and look for Meat Slimes on the ground (run /thaumichorizons plane preset forge and visit that rift for Mercurial Slimes).

**Expect**

- [ ] The Meat Slime is a red-pink slime and the Mercurial Slime a silver one; both behave and split as vanilla slimes do (the pieces are their own kind) and drop nothing. Their landing puffs are red dust and snow shards.
- [ ] Planes with Flesh, Slime or Hunger hold some Meat Slimes, planes with Metal, Poison, Exchange or Mechanism some Mercurial Slimes, in the numbers of the creature cap (100 mobs of all kinds).

<sub>Already covered by automated pack tests: `slimes_split_without_drops_and_the_plan_spawns_them`</sub>

## 5. Potion effects of a plane

Check id: `horizons_h7_3a.plane_effects`

**Steps**

1. You stand in survival two blocks from the rift of a forge plane. (/thaumichorizons plane list shows each plane's effects; presets storm and charnel have other aspects. The Motion and Travel and Weapon or Flight cases need real nodes and are not staged.)
2. Walk in and watch your effect icons for five seconds, walk out through the exit vortex and keep watching for fifteen.

**Expect**

- [ ] Inside a plane the effects of its aspects appear within five seconds and stay while you are in it (Motion and Travel together give Speed II, one alone Speed I; Weapon gives Strength, Flight Jump Boost, Tool Haste, Armor Resistance, Heal Regeneration), without particles.
- [ ] Fifteen seconds after you leave through the vortex they are gone. Nothing runs while nobody is in the plane.

<sub>Already covered by automated pack tests: `effects_rule_speed_two_with_motion_and_travel`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_3a`).
