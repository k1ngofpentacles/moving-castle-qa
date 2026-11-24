# QA: Horizons H7-2: the pocket plane

Chapter id `horizons_h7_2`, 5 checks. In game this is the FTB Quests chapter **QA: Horizons H7-2: the pocket plane**; each check there has a green "Set up this check" line that builds its test site.

## 1. The plane's blocks

Check id: `horizons_h7_2.plane_blocks`

**Steps**

1. You stand in survival mode in front of a row of blocks: the Planar Boundary, Dust, Brain and the six Infused Stones (air, earth, fire, water, order, entropy). A strip of Dust lies behind the row. Your hotbar holds a diamond pickaxe and a silk touch pickaxe.
2. Break the Infused Stones with the diamond pickaxe, then break one again after placing it back with the silk touch pickaxe. Walk through the Dust strip.

**Expect**

- [ ] The Planar Boundary is a deep violet void with slow motes drifting upward (animated); Dust is a pale sandy block a little shorter than a full block; Brain is a pink folded block; each Infused Stone is grey stone with flecks in its primal's colour (yellow air, green earth, orange fire, blue water, white order, dark purple entropy).
- [ ] The Boundary cannot be broken in survival. An Infused Stone drops one to three essentia crystals of its primal with the diamond pickaxe and itself with silk touch. Walking in Dust is clearly slowed. Brain drops two or three brains.
- [ ] Every block has a name in its own colour set (Air Infused Stone and so on) and an item in the Horizons creative tab.

<sub>Already covered by automated pack tests: `dimension_jsons_parse_against_the_registries`, `every_block_the_generator_can_place_exists`</sub>

## 2. A pearl makes a plane

Check id: `horizons_h7_2.pearl_makes_a_plane`

**Steps**

1. You stand in front of two stable (creative) rifts. Slot 1 holds a primordial pearl already renamed "Anvil Plane"; slot 2 holds an unnamed pearl.
2. Throw (Q) the named pearl into the left rift and the unnamed one into the right rift. Then run /thaumichorizons plane list to read the two plane names.
3. Open the Pocket Plane research entry in the Horizons tab.

**Expect**

- [ ] The pearl is used up whole in a small blast and the rift now makes a plane: a rift that has made one stops taking void-craft items. The research entry reads as the original's three pages with a note on how to enter and leave.
- [ ] The first plane carries the pearl's anvil name; the second the name of whoever threw the pearl with 's Pocket Plane after it (use /thaumichorizons plane list to read them).

<sub>Already covered by automated pack tests: `pearl_handler_claims_only_the_pearl_and_waits_for_the_dimension`, `record_codec_and_saved_data_round_trip`</sub>

## 3. Walking in and out

Check id: `horizons_h7_2.arrival_and_exit`

**Steps**

1. You stand two blocks from the rift of a freshly made forge plane (made by /thaumichorizons plane preset forge).
2. Walk into the rift. Look around the arrival pad. Walk into the vortex in the middle of the pad.
3. Go back in, then break (creative) the origin rift from outside. Walk into the vortex again.

**Expect**

- [ ] You arrive on a five by five pad of arcane stone beside a glowing vortex, with open air above, a few seconds after generation starts; there is a short pause the first time while chunks draw themselves.
- [ ] The vortex returns you to the rift's block; you are not sent straight back in (a short cooldown).
- [ ] With the origin rift gone the vortex still works and sends you to your respawn point with a message, never leaves you stuck.

<sub>Already covered by automated pack tests: `transfer_targets_and_safe_exit`, `paint_shell_pad_and_nothing_outside_the_radius`</sub>

## 4. The world inside

Check id: `horizons_h7_2.world_look`

**Steps**

1. You stand two blocks from the rift of a forge plane.
2. Walk in and walk to the edge, look up and across, look at the light and the fog, dig down a little, find a cave. Use the exit vortex to come back, then run /thaumichorizons plane visit storm (and later charnel) and look around those the same way.

**Expect**

- [ ] Each plane is a hollow sphere: land in the lower half, open air above, a thin dark violet shell all round with no gaps. There is no sun, moon or stars, a dark indigo fog, and light that never goes fully black (ambient glow).
- [ ] forge: a desert of sand over stone over netherrack, with ore pockets and crystal clusters in caves. storm: grass, flowers and saplings with snow on top (its recipe is cold taiga), a few animals. charnel: a bed of flesh with brain clumps, an eerie biome, rings of ancient stone just inside the shell.
- [ ] Biome colours (grass, sky tint at the horizon of the fog, water) match the biome each plane names in the chat when created.

<sub>Already covered by automated pack tests: `radius_colour_noise_life_biome_are_the_originals`, `layer_stack_of_the_three_recipes`, `paint_is_deterministic_by_seed_and_independent_of_order`, `creature_points_are_capped_and_inside_the_plane`, `qa_presets_make_ordinary_planes`</sub>

## 5. The biggest plane

Check id: `horizons_h7_2.big_plane_hitch`

**Steps**

1. You stand two blocks from the rift of the huge plane (radius 127).
2. Walk in, then walk and fly across the plane edge to edge, and note whether the game stutters when new chunks appear. Leave and come back.

**Expect**

- [ ] The plane is radius 127. Entering takes a moment while the chunks near the pad draw; afterwards new chunks appear without long freezes, and the plane looks the same after leaving and returning (nothing regenerates differently).

<sub>Already covered by automated pack tests: `paint_is_deterministic_by_seed_and_independent_of_order`, `weight_table_is_valid_and_feeds_the_formulas`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_2`).
