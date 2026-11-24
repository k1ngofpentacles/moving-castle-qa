# QA: Horizons H5: tools, foci, lenses and boats

Chapter id `horizons_h5`, 10 checks. In game this is the FTB Quests chapter **QA: Horizons H5: tools, foci, lenses and boats**; each check there has a green "Set up this check" line that builds its test site.

## 1. Injector and Blast Phials

Check id: `horizons_h5.injector`

**Steps**

1. An injector, injections and Blast Phials are on your hotbar; a dispenser with a lever stands to the right, aiming at a cow and a zombie.
2. Sneak and right-click the injector, load injections and phials; draw it like a bow at short and full pull; throw a phial; open the drum with an enchanted injector.
3. Put the injector in the dispenser with ammunition.

**Expect**

- [ ] The drum holds seven, rotates, fires syringes that hit and can be recovered; the phial splashes within four blocks; the enchantments survive opening the drum.
- [ ] Feel: draw time, damage, the drum's look in hand.

<sub>Already covered by automated pack tests: `injector_draw_curve`, `injector_loads_fires_and_rotates`, `injector_gui_keeps_enchantments`, `syringe_hits_and_recovery`, `phial_splash_applies_effects_in_radius`, `phial_throws_and_registers`</sub>

## 2. Alchemite

Check id: `horizons_h5.alchemite`

**Steps**

1. A stone bank with ores and alchemite blocks stands nine blocks ahead (two alchemites side by side); flint and steel is on your hotbar.
2. Light one alchemite, stand well back; light the two adjacent ones.

**Expect**

- [ ] The block flashes, blasts for five blocks without fire, drops essentia crystals in place of items, chains to its neighbour.
- [ ] Feel: crystal counts.

<sub>Already covered by automated pack tests: `alchemite_ignites_blasts_and_chains`, `alchemite_node_outcomes`</sub>

## 3. Liquefaction, Disintegration, Illumination

Check id: `horizons_h5.foci`

**Steps**

1. A Focal Manipulator stands beside you; ahead are stone, ice, iron ore and gold ore blocks, items on the ground and a cow. The wand is on your hotbar.
2. Build each spell in the Focal Manipulator and cast it at the blocks, items and the cow; place light orbs and strike one.

**Expect**

- [ ] Liquefaction melts and smelts; Disintegration turns blocks and items into crystals; Illumination leaves an orb that goes when struck; each costs vis from a wand in the hotbar.
- [ ] Feel: speeds and vis costs; Illumination has no dye recipe (the colour is a setting).

<sub>Already covered by automated pack tests: `liquefaction_block_classes`, `liquefaction_ores_purity_and_nuggets`, `liquefaction_items_creatures_area_and_protection`, `disintegration_blocks_items_and_creatures`, `illumination_places_orbs`, `the_parts_work_through_real_casts`</sub>

## 4. Lens wheel, B key and Lens Case

Check id: `horizons_h5.lens_wheel`

**Steps**

1. You wear the goggles; five lenses and the Lens Case are on your hotbar.
2. Hold B (bound by default; V belongs to the bracelets), move the mouse toward a lens and release; press Shift + B to take the lens out.
3. Right-click the Lens Case, put the lenses in; carry it in the inventory, then in the Curios belt slot, and use the wheel again.

**Expect**

- [ ] The wheel shows the lenses you carry on a ring, the highlighted one grows and is named; releasing chooses it, the old lens returns to a case or the inventory; one lens of each kind.
- [ ] A case on the belt feeds the wheel but cannot be opened there (as the original). Feel: the wheel size, the mouse release and re-grab; B no longer clashes with the bracelets' V.

<sub>Already covered by automated pack tests: `lens_storage_and_swap`, `lens_case_on_the_belt_is_used`, `goggles_in_curios_and_without_goggles`, `lens_case_menu_storage`</sub>

## 5. Illumine and Echo lenses

Check id: `horizons_h5.night_vision`

**Steps**

1. You wear the goggles; the Illumine and Echo lenses and a night vision potion are on your hotbar. A dark stone cave with a pool stands ahead.
2. Wear Illumine: stand in the dark cave, then dive into the water. Wear Echo: dive, then surface. Drink the night vision potion with each lens and leave the water.

**Expect**

- [ ] Illumine gives night vision out of water only; Echo only under water and clears the blue tint; no potion icon appears; the real potion is never cut short; the effect does not flicker.

<sub>Already covered by automated pack tests: `night_vision_rules`</sub>

## 6. Evanescent lens

Check id: `horizons_h5.evanescent`

**Steps**

1. You wear the goggles with the Evanescent lens and carry a pickaxe; a stone wall with ores behind its face, a chest and a torch stand ahead.
2. Look at the wall, the floor and the ores; sweep the crosshair across blocks; mine the block you look at; look at the chest and the torch.

**Expect**

- [ ] The 3 x 3 blocks on the face you look at turn clear and you see one block deeper; the clear patch follows the crosshair without flicker; mining the looked-at block works at the normal speed; chests, torches and glowing blocks stay solid; nothing changes for other players.
- [ ] Feel: re-render stutter when sweeping fast, the look of the clear frame.

<sub>Already covered by automated pack tests: `evanescent_answers_with_the_real_blocks_hardness`</sub>

## 7. Kirlian lens

Check id: `horizons_h5.kirlian`

**Steps**

1. You wear the goggles with the Kirlian lens; a stone wall stands ahead with a cow, a pig, a zombie and a skeleton hidden behind it.
2. Look at the wall in first person, then switch to third person.

**Expect**

- [ ] Living creatures show blue ripples, undead a red vortex, through the wall; nothing shows in third person; the marks scale with distance.
- [ ] Feel: strength and size of the marks (our alpha and size are tuned by eye, not the original's numbers).

## 8. Scholar's lens

Check id: `horizons_h5.scholar`

**Steps**

1. You wear the goggles with the Scholar's lens; unscanned blocks (gold, lapis, bookshelf) and a cow stand ahead.
2. Look at an unscanned block, then at the cow; keep looking for four seconds; look away halfway.
3. Look at something already scanned.

**Expect**

- [ ] A purple bar fills for four seconds with runes and ticks and the scan completes (the thaumometer message appears); looking away resets it; scanned things show their name and aspects above the crosshair.

<sub>Already covered by automated pack tests: `scholar_scan_payload_grants_the_scan`</sub>

## 9. Greatwood and Thaumium boats

Check id: `horizons_h5.boats`

**Steps**

1. A wide water pool with a wall at its far end and a lava pool beside it lie ahead; an oak boat, the Greatwood boat, the Thaumium boat and a dispenser are on your hotbar.
2. Place each boat on water and ride it; compare speed with the oak boat; ram the wall; place the Thaumium boat on lava and ride it; use the dispenser on water.
3. Break the Thaumium boat in lava.

**Expect**

- [ ] The Greatwood boat is about 1.3 times and the Thaumium boat about 1.4 times as fast and neither breaks on impact; the Thaumium boat floats on lava, you do not burn and the fire on your screen is hidden, and its drop does not burn.
- [ ] Feel: the speed, the boat colours.

<sub>Already covered by automated pack tests: `boats_speed_lava_and_riders`</sub>

## 10. Recipes and research

Check id: `horizons_h5.recipes`

**Steps**

1. An Arcane Workbench stands beside you; the Thaumonomicon is on your hotbar.
2. Open the Thaumonomicon, Thaumic Horizons tab, and follow the Arcane Lenses, Lens Case and boat entries; craft one of each.

**Expect**

- [ ] The entries sit where the original had them, read well, and each recipe crafts.

<sub>Already covered by automated pack tests: `lens_recipes_and_tags_exist`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h5`).
