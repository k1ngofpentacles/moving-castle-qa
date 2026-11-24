# QA: Horizons H7-3b: the planar clouds

Chapter id `horizons_h7_3b`, 7 checks. In game this is the FTB Quests chapter **QA: Horizons H7-3b: the planar clouds**; each check there has a green "Set up this check" line that builds its test site.

## 1. The ten cloud blocks

Check id: `horizons_h7_3b.cloud_blocks`

**Steps**

1. You stand in survival in front of two rows of the ten cloud blocks, in the creative tab order (Mundane, Plasma, Thunder, Acid, Alloy, Tumorous, Vis, Glyph, Spore, Animus); the second row repeats the first.
2. Walk through them. Try to break one in survival, then in creative. Stand inside a Plasma Cloud, an Alloy Cloud and an Acid Cloud for a few seconds each.

**Expect**

- [ ] Ten different soft clouds (white, ember, dark storm, green, grey metal, red-pink, violet, white-gold, pale green, yellow), animated; the glowing ones (Plasma, Alloy, Vis, Glyph, Animus) light their surroundings. You walk straight through them; neighbouring clouds of one kind show no seams between them. They cannot be broken in survival.
- [ ] Plasma and Alloy set you on fire for six seconds; Acid hurts you one point a hit (dissolve damage); the rest do nothing.

<sub>Already covered by automated pack tests: `clouds_paint_into_air_only_and_are_registered_blocks`, `contact_fire_acid_and_spore_cows`</sub>

## 2. Clouds from the ground

Check id: `horizons_h7_3b.clouds_in_the_plane`

**Steps**

1. You stand in creative two blocks from the rift of a storm plane.
2. Walk in, look up from the ground, then fly up to the clouds. Come back and run /thaumichorizons plane preset forge and charnel for the other two recipes.

**Expect**

- [ ] Flat two-layer cloud blobs, five to nine blocks across and ragged at the edge, hang high in the plane, well inside the boundary; a storm plane shows white clouds and dark Thunderclouds and pale-green Spore Clouds, a forge plane ember Plasma and grey Alloy clouds, a charnel plane red Tumorous and white-gold Glyph clouds. They read as clouds from the ground, not as floating blocks.
- [ ] Plasma, Thunder, Acid and Animus clouds may sit anywhere, over the arrival pad too (a design answer): look for one and judge whether that is fair to arrive under.

<sub>Already covered by automated pack tests: `cloud_kinds_follow_the_three_recipes`, `bodies_count_altitude_and_shell`</sub>

## 3. The rain of each kind

Check id: `horizons_h7_3b.rain_look`

**Steps**

1. You stand in creative with rain on. Seven blocks above the grass ahead hang a Mundane, a Plasma, an Acid, an Alloy, a Tumorous and a Spore Cloud in a row, and further east (the part of the pad that was turned into a snowy biome) another Mundane Cloud.
2. Watch the rain for ten seconds, then walk close and look up the columns from below. Compare the snow column in the east.

**Expect**

- [ ] While it rains, each cloud drops a one-block-wide column of rain to the first block under it, scrolling downward and glowing (additive): blue for the Mundane Cloud, embers for Plasma, green for Acid, dark grey for Alloy, red for Tumorous, pale green for Spore; violet for Vis, white for Glyph, yellow for Animus. A cloud directly above another has no column. No column shows when it is not raining. In a cold biome the column is snow.
- [ ] Frame rate does not suffer with many clouds in view.

## 4. The rain follows the overworld

Check id: `horizons_h7_3b.rain_sync`

**Steps**

1. You stand in creative on a clear day, two blocks from the rift of a storm plane; a Cloud floats seven blocks up behind it.
2. Walk into the plane, run /weather rain and then /weather clear (from inside it), and watch the planar clouds. Leave and come back while it rains; the Overworld cloud outside rains with the weather too.

**Expect**

- [ ] The planar rain starts within a moment of the overworld rain and stops when it clears; on re-entering or joining while it rains, the columns are already there. In the Overworld itself a placed cloud rains with the weather too.

<sub>Already covered by automated pack tests: `the_controller_runs_only_while_it_rains`</sub>

## 5. What the rain does

Check id: `horizons_h7_3b.cloud_effects`

**Steps**

1. You stand with rain on in front of a row of targets with a cloud above each: under Mundane Clouds farmland, a cauldron and dirt with a fire on top; under Plasma Clouds leaves, ice, grass and planks; under Acid Clouds leaves and grass; a cow under a Spore Cloud and an Enderman under a Cloud (neither moves).
2. Wait half a minute and watch each target.

**Expect**

- [ ] Mundane rain wets farmland, fills a cauldron to the top and puts out fire on the block it falls on; the Enderman takes damage and the burning player or mob is put out. In a cold biome it lays a layer of snow on solid blocks instead.
- [ ] Plasma and Alloy turn leaves and plants into fire, ice into water, grass into dirt and light flammable blocks into fire; stone is left alone. Acid removes leaves and plants and turns grass into dirt, and hurts what stands under it. The Spore Cloud turns a cow into a mooshroom with a puff.

<sub>Already covered by automated pack tests: `default_clouds_wet_farmland_fill_cauldrons_and_put_out_fire`, `plasma_and_alloy_melt_acid_dissolves`, `contact_fire_acid_and_spore_cows`</sub>

## 6. What the clouds shed

Check id: `horizons_h7_3b.cloud_drops`

**Steps**

1. You stand with rain on in front of a row of seven clouds seven blocks up, left to right: Thunder, Alloy, Tumorous, Vis, Glyph, Spore (over grass) and Animus (over a stone block). Your hotbar holds a full wand for the vis orbs.
2. Wait a few minutes and watch what each sheds (keep away from the Animus golem).

**Expect**

- [ ] Thundercloud: lightning strikes the ground below every minute or so (not the whole sky). Alloy: nuggets (gold, silver, copper, tin, lead, quicksilver, mostly iron) that cannot be destroyed by fire or lava. Tumorous: raw beef, pork, chicken or fish and mostly Unidentifiable Meat (food; cooks in a furnace). Vis: a glowing aspect orb of a primal (collect it with a wand). Glyph: small experience orbs. Spore: grass gets flowers, saplings (also Greatwood and Silverwood), Shimmerleaf, Vishroom, dirt turns to grass or mycelium, sand gets cacti, farmland crops. Animus: lightning that turns the block it strikes into a berserk golem for a minute, which attacks you; the stone block is gone while it lasts.

<sub>Already covered by automated pack tests: `drops_spores_bolts_and_the_animus_golem`, `spore_clouds_plant_the_blocks_below`, `drop_timers_tables_and_columns`</sub>

## 7. Lifting a cloud with a wand

Check id: `horizons_h7_3b.cloud_pickup`

**Steps**

1. You stand in survival with a Cloud block placed three blocks ahead, a Cloud item dropped at your feet, and a full wand in slot 1 and an empty one in slot 2. Pocket Plane is done; Planar Clouds is not.
2. Pick up the cloud item and look in the research book (Planar Clouds, Wild weather). Then right-click the placed cloud with the full wand, then with the empty wand. Place the item again. Check the wand's Aer before and after.

**Expect**

- [ ] Picking up any cloud item unlocks Planar Clouds (once Pocket Plane is done), three pages about the ten kinds. Right-clicking a cloud with a wand costs 100 Aer vis (a little more with some caps) and leaves an item that cannot be destroyed; an empty wand does nothing and says so. The item places like a block and the placed cloud rains and works like a generated one.

<sub>Already covered by automated pack tests: `the_wand_lifts_a_cloud_for_100_aer_once_the_research_is_done`, `picking_up_a_cloud_item_unlocks_the_research`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_3b`).
