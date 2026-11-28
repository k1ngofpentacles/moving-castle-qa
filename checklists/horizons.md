# QA: Thaumic Horizons

Chapter id `horizons`, 56 checks. In game this is the FTB Quests chapter **QA: Thaumic Horizons**; each check there has a green "Set up this check" line that builds its test site.

## 1. Incubated egg

Check id: `horizons.incubated_egg`

**Steps**

1. Read its research entry ("Alch Incubation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a dispenser loaded with incubated eggs (the lever beside it fires it) and a cow.
3. Throw an incubated egg from your hotbar at the ground, then at the cow, then flip the lever.

**Expect**

- [ ] A baby chicken every time, with a puff of white particles; no adult chickens, no damage to a mob hit.

<sub>Already covered by automated pack tests: `incubated_egg_hatches_a_baby_chicken`</sub>

## 2. Warded syringe, Seroconverter and potions

Check id: `horizons.syringe_seroconverter`

**Steps**

1. Read its research entry ("Essentia Injection") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand between a cow (left, close) and a zombie (right, held still) with warded syringes on your hotbar.
3. Right-click the cow with a warded syringe, then the zombie, then the air.
4. Next: A Seroconverter stands in front of you, a cow beside it, and warded syringes are on your hotbar.
5. Right-click the air with a syringe for a Blood Syringe and put it in the Seroconverter; pipe essentia into it from a jar with tubes (you must bring the jar and tubes), pick aspects in the palette, wait.
6. Use the injection on yourself, then strike the cow with one.
7. Next: You stand in front of a Seroconverter with four jars touching it: Auram, Desiderium, Potentia and Herba. Your hotbar holds four syringes.
8. Put a syringe in, select Auram (Vis Generation), Desiderium (Item Vacuum), Potentia (Static Shock) or Herba (Photosynthesis), make an injection and use it. Repeat for the others.

**Expect**

- [ ] Cow: a Blood Sample named after the cow.
- [ ] Zombie: nothing happens, the syringe is kept.
- [ ] Air: a Blood Syringe (your own blood).
- [ ] The screen reads like the original (layout, palette); aspects with no working effect are not offered.
- [ ] Effects match the research page's patterns; feel of durations and strength.
- [ ] The aspects are in the palette; Vis Generation drops primal orbs, Item Vacuum pulls items in, Static Shock zaps neighbours, Photosynthesis heals and feeds in daylight; the status icons are readable.

<sub>Already covered by automated pack tests: `syringe_samples_passive_mob`, `syringe_ignores_hostile_and_villager`, `syringe_in_air_gives_own_blood`, `seroconverter_fills_an_injection_from_piped_essentia`, `injection_applies_its_effects`, `deferred_only_aspects_are_hidden`, `potions_do_what_the_original_did`, `photosynthesis_heals_only_in_daylight`, `serconverter_has_the_vis_potions_back`</sub>

## 3. The Curative Vat

Check id: `horizons.curative_vat`

**Steps**

1. Read its research entry ("Healing Vat") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. In front of you stands the raw vat: planks ring with an Alchemical Construct centre at the base and lid, glass ring with water between.
3. Wand-click any block of it.
4. Next: A raw vat stands in front of you, with a hurt, poisoned cow to its right. The wand, Containment focus and soul jars are on your hotbar, and you are hungry.
5. Wand-click the vat to form it; jar the cow with the focus and load it into the vat; pipe in Victus (bring a jar and tubes), then Victus + Alkimia.
6. Empty-hand click the vat's top to climb in yourself; pipe Desiderium.

**Expect**

- [ ] It turns into one vat with the original lid and base art and a blue water fill; vis is taken from the wand.
- [ ] Breaking any part turns it back into the raw blocks.
- [ ] Victus alone heals 2 hearts at a time; Victus with Alkimia heals 4 and clears poison and similar effects.
- [ ] You are fed, and the Desiderium is used up. The cow floats visibly in the water.

<sub>Already covered by automated pack tests: `vat_forms_with_wand`, `vat_break_reverts_and_kills`, `curative_victus_alone_heals_two_hearts`, `curative_victus_with_alkimia_heals_four_hearts_and_cures`, `curative_desiderium_feeds_a_player_and_is_consumed`</sub>

## 4. The Incarnation Vat and two players

Check id: `horizons.incarnation_vat`

**Steps**

1. Read its research entry ("Incarnation Vat") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat stands in front of you; the wand, raw beef and nutrients are on your hotbar.
3. Wand-click the vat to form it, open its screen, put raw beef in the sample slot and nutrients in the other; pipe 4 Victus (bring a jar and tubes).
4. Next: You stand in front of a raw vat with the wand, Containment focus, soul jars, Seroconverter and a cow ready.
5. With a second player on LAN (they use the same staging): watch the other run the vat, jar a creature, use the Seroconverter.

**Expect**

- [ ] A cow fades in over about 40 s; feel of the fade and the sparkles.
- [ ] Both see the occupant, water, ritual and jars the same; no desync or crash.

<sub>Already covered by automated pack tests: `incarnation_from_raw_beef`, `incarnation_from_a_sample_demands_the_infusion_costs`</sub>

## 5. Creature infusion ritual

Check id: `horizons.creature_infusion`

**Steps**

1. Read its research entry ("Infusion Vat") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat with the Modified Runic Matrix on its lid stands ahead; four empty arcane pedestals ring it, and a cow waits beside. On your hotbar: the wand, the Containment focus, soul jars, a Swiftness II potion and two quicksilver.
3. Wand-click the vat to form it, jar the cow and load it in, put the potion and quicksilver on the pedestals, pipe in the essentia (bring jars and tubes); wand-click the matrix.
4. Try each infusion on a cow or wolf: Thaumium Claws, Enderheart (shoot it), Shockskin (hit it), Runic Hide, Eldritch Fangs, Instilled Loyalty (sit/follow), Portability (wand-click it).

**Expect**

- [ ] The ritual looks and sounds right (the Modified Matrix's floating cubes are Thaumaturge arcane stone); instability by symmetry; breaking the matrix kills the subject.
- [ ] Each trait behaves as its research page says; feel and balance.

<sub>Already covered by automated pack tests: `full_run_quicksilver_limbs`, `trait_enderheart_blinks_from_projectiles`, `trait_shockskin_zaps_its_attacker`, `trait_runic_hide_absorbs`, `trait_eldritch_fangs_poison_the_target`, `trait_instilled_loyalty_replaces_the_ai_and_sits`, `trait_portability_jars_the_creature`, `breaking_the_matrix_kills_the_subject`</sub>

## 6. Infusion Claw on the vat (with Gadomancy)

Check id: `horizons.claw_vat`

**Steps**

1. A raw vat with the Modified Runic Matrix on its lid stands ahead, four arcane pedestals ring it, a cow waits beside. On your hotbar: the wand, the Containment focus, soul jars, a Swiftness II potion, two quicksilver, an Infusion Claw, goggles, a comparator and a lever.
2. Form the vat with the wand, jar the cow and load it in, put the potion and quicksilver on the pedestals, pipe in the essentia as for a hand-started ritual.
3. Place the claw on top of the matrix, right-click it and put a second charged wand (no focus) in its slot (the kit gives one); put the comparator behind the claw and the lever on a block beside it.
4. Flip the lever on (one pulse) and watch for about 22 seconds; check the ritual's instability with the goggles against a hand-started one.
5. Run the claw again with Instilled Loyalty (on a wolf) and check whose orders the creature follows.

**Expect**

- [ ] About 14 seconds after the pulse the claw clicks the matrix and the creature infusion starts as if you had wand-clicked it; the claw's wand loses some vis of each primal.
- [ ] The ritual starts with about half the claw's usual penalty added (about 7 for an iron-capped wooden wand); staffs and better caps add less.
- [ ] The comparator gives 15 while the ritual runs and 0 when the vat is idle or standing by.
- [ ] An Instilled Loyalty creature made by the claw is loyal to the claw's owner (you).

<sub>Already covered by automated pack tests: `horizons_claw_starts_vat_infusion`, `horizons_claw_idle_vat_gives_nothing`, `horizons_claw_target_registered`, `horizons_loads_without_gadomancy`</sub>

## 7. Soul Sieve, Inspiratron and Knowledge Fragment

Check id: `horizons.soul_sieve`

**Steps**

1. Read its research entry ("Soul Extractor", "Soul Knowledge", "Soul Assembler") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Two Soul Sieves stand in front of you: one under an Inspiratron, one under a Soulforge. Soul sand and paper are on your hotbar.
3. Feed soul sand into each sieve; give the Inspiratron paper.
4. Next: Knowledge Fragments are on your hotbar.
5. Use one.

**Expect**

- [ ] Sand is used only when something above receives the soul; the Inspiratron writes Knowledge Fragments; the machines look like the original models and animate; the Soulforge and Inspiratron brains and brine are Thaumaturge's, and a forging Soulforge shows four small crackling lightning rings at its top corners (no spark particles).
- [ ] 1-2 of each primal aspect is added to your aspect pool; the message reads well.

<sub>Already covered by automated pack tests: `sieve_feeds_the_soulforge`, `sieve_drops_sand_a_full_chest_refuses`, `inspiratron_writes_fragments`, `fragment_grants_every_primal`</sub>

## 8. Containment focus, Lost Soul and soul jars

Check id: `horizons.soul_jars`

**Steps**

1. Read its research entry ("Focus Containment") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A cow stands six blocks ahead; an empty soul jar and the Containment focus are on your hotbar.
3. Channel the Containment focus at the cow (about 10 s).
4. Place the jar; wand-click it.
5. Next: A Lost Soul hovers six blocks ahead; the wand, Containment focus and empty soul jars are on your hotbar.
6. Catch it with the Containment focus and an empty soul jar.

**Expect**

- [ ] The beam and jarring effect look right; the cow ends up drawn small inside the placed jar, which is a Thaumaturge jar (its glass and lid), not clipping through the glass.
- [ ] Wand click releases the cow and the jar is gone. Players, golems and bosses are refused.
- [ ] The Lost Soul's sprite animates; the catch gives a soul jar with a soul wisp drawn inside.

<sub>Already covered by automated pack tests: `capture_makes_a_jar_with_the_creature`, `release_restores_the_creature_and_destroys_the_jar`, `containment_refuses_what_it_cannot_take`, `lost_soul_capture_gives_a_soul_jar`, `soul_jar_keeps_its_soul`</sub>

## 9. Soul Beacon and the death rule

Check id: `horizons.soul_beacon`

**Steps**

1. Read its research entry ("Clone Self") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat stands in front of you; the wand and a Soul Beacon are on your hotbar.
3. Wand-click the vat to form it, put the Soul Beacon on it and bind it; die (e.g. /kill).
4. Next: A raw vat stands ahead; the wand and a Soul Beacon are on your hotbar.
5. Form the vat, put it in standby and bind the beacon, die with /kill, wake in the vat.
6. Next, die again with no beacon.

**Expect**

- [ ] Instead of dying you wake inside the vat with health restored; the binding is used up (re-bind to use again).
- [ ] The first death applies the infusions through the rebirth; an ordinary death clears them and returns the Warped Tumor's warp.

<sub>Already covered by automated pack tests: `beacon_cancels_a_death`, `death_event_reincarnates`, `beacon_reincarnates_into_the_vat`, `rebirth_applies_and_an_ordinary_death_clears`, `warped_tumor_absorbs_and_returns_warp`</sub>

## 10. Mirrored Amulet

Check id: `horizons.mirrored_amulet`

**Steps**

1. Read its research entry ("Mirror Amulet") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A mirror stands ahead; the hand mirror is on your hotbar and you are already wearing the Mirrored Amulet in the Curios necklace slot.
3. Link the hand mirror to a mirror elsewhere (use the one ahead, or place another far away), then die with a full inventory.

**Expect**

- [ ] Your items arrive at the linked mirror (it ejects them over a few moments).

<sub>Already covered by automated pack tests: `amulet_sends_everything_through_the_mirror`</sub>

## 11. Corpse Effigy revival and standby

Check id: `horizons.corpse_effigy`

**Steps**

1. Read its research entry ("Clone Villager") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat stands in front of you; the wand, Corpse Effigies and soul jars are on your hotbar.
3. Wand-click the vat to form it, put a Corpse Effigy in the sample slot; pipe 16 Victus (bring a jar and tubes).
4. Then load a soul jar into the standby vat.

**Expect**

- [ ] The effigy body revives in the vat (pose and scale look right) and the vat stands by; a villager of the soul's profession appears and the jar comes back empty.

<sub>Already covered by automated pack tests: `effigy_revival`, `effigy_revival_waits_and_aborts`, `standby_enters_and_leaves`</sub>

## 12. Animation Powder golems and seals

Check id: `horizons.powder_golems`

**Steps**

1. Read its research entry ("Golem Powder") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Five blocks stand in a row ahead: stone, iron block, cactus (on sand), cobweb and TNT. Animation Powder is on your hotbar.
3. Use Animation Powder on each, one at a time; watch each golem for 60 s.
4. Next: A stone block stands ahead; Animation Powder and two Guard seals are on your hotbar.
5. Animate the stone, use a seal item on the temporary golem; place a matching seal in the world.
6. Sneak-click it as its owner.

**Expect**

- [ ] Each golem wears its block's textures, follows you and fights; cactus thorns, web slows; when time runs out the block is put back; the TNT golem explodes.
- [ ] Feel: speed, size, animation; the powder is used up.
- [ ] It stays, works the seal's task like a Thaumaturge golem, keeps its block skin; picking it up gives an Animated Golem item that places it back.

<sub>Already covered by automated pack tests: `powder_animates_a_block_and_is_consumed`, `stats_follow_the_type_table`, `timer_expiry_returns_the_block`, `tnt_and_detonation_golems_explode`, `cactus_thorns_and_web_slowness`, `seal_binding_makes_the_golem_permanent`, `pickup_item_round_trips`</sub>

## 13. Animation focus

Check id: `horizons.animation_focus`

**Steps**

1. Read its research entry ("Focus Animation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Focal Manipulator stands beside you and a row of blocks (stone, iron, planks, glass) ahead; the wand is on your hotbar.
3. Craft the Animation focus (research Animation focus), cast it on the blocks with Extend, Berserk and Detonation settings.

**Expect**

- [ ] Vis cost depends on the material; Extend lengthens life; Berserk attacks everything but you; Detonation explodes at the end.

<sub>Already covered by automated pack tests: `focus_charges_by_material`, `berserk_golem_attacks_everything_but_the_owner`</sub>

## 14. Chocolate Cow, Chromatic and Self-shearing Sheep

Check id: `horizons.cow_sheep`

**Steps**

1. Read its research entry ("Cow Infusion", "Sheep Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Chocolate Cow, a Chromatic Sheep and a Self-shearing Sheep stand ahead; you are weakened and carry buckets and a milk bucket.
3. Milk the cow with a bucket and drink the other milk to cure effects; watch the Chromatic Sheep for two minutes and the Self-shearing Sheep for one.

**Expect**

- [ ] The cow gives a chocolate milk bucket (a bucket item only, by decision) that cures effects like milk; the Chromatic Sheep cycles colours smoothly; the Self-shearing Sheep drops wool by itself and regrows it.
- [ ] The mobs look right and read as their originals; calves are not milked and lambs not self-shearing (accepted).

<sub>Already covered by automated pack tests: `chocolate_cow_milks_chocolate_and_the_bucket_cures`, `chromatic_sheep_cycles_and_self_shearing_sheep_shears`</sub>

## 15. Sheeder

Check id: `horizons.sheeder`

**Steps**

1. Read its research entry ("Sheeder Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Sheeder stands ahead in front of a wall; shears are on your hotbar.
3. Shear it, climb near it and hit it.

**Expect**

- [ ] It is a spider that yields wool, regrows it and climbs walls; it fights back when hit (a deliberate quirk kept from the original).

<sub>Already covered by automated pack tests: `sheeder_shears_regrows_climbs_and_fights_back`</sub>

## 16. Gold Chicken and Scholar Chicken

Check id: `horizons.chickens`

**Steps**

1. Read its research entry ("Chicken Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Gold Chicken and a Scholar Chicken stand ahead.
3. Wait for eggs; collect what they lay.

**Expect**

- [ ] The Gold Chicken lays gold nuggets or eggs with a sparkle; the Scholar Chicken lays knowledge items; sparkle rate feels fine (the gold sparkle is per tick: accepted).

<sub>Already covered by automated pack tests: `chickens_lay_their_own_products`</sub>

## 17. Ore Boar and Taintfeeder

Check id: `horizons.boar_taintfeeder`

**Steps**

1. Read its research entry ("Pig Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. An Ore Boar stands to the left, a Taintfeeder to the right beside a few blocks of taint rock; iron ore is on your hotbar.
3. Throw iron ore on the ground near the Ore Boar; watch the Taintfeeder eat the taint.

**Expect**

- [ ] The boar eats ores from up to 16 blocks away and drops purified extras; the Taintfeeder eats taint and restores the clean biome, and the taint effects do not hurt it.
- [ ] The glow strips are redrawn art: judge the look.

<sub>Already covered by automated pack tests: `ore_boar_table_eating_and_loot`, `taintfeeder_ignores_the_taint_effects`, `taintfeeder_eats_taint`</sub>

## 18. Guardian Panther and Gravekeeper

Check id: `horizons.panther_gravekeeper`

**Steps**

1. Read its research entry ("Cat Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Guardian Panther, a black-cat Guardian Panther, a Gravekeeper and a zombie stand ahead (night, easy difficulty); raw fish is on your hotbar.
3. Feed the panther and let the zombie approach; stand near the Gravekeeper with the undead around.
4. Save and quit, reload the world and look at both panthers again.

**Expect**

- [ ] The panther guards you and attacks threats; the Gravekeeper bites and its aura affects undead.
- [ ] A panther summoned or from a spawn egg wears the spotted ocelot skin; one made from a cat keeps that cat's skin (the black one here), twice a cat's size. Both keep their skin after the reload.

<sub>Already covered by automated pack tests: `guardian_panther_numbers_goals_and_food`, `guardian_panther_skin_variant_and_ocelot`, `gravekeeper_goal_fix_bite_and_aura`</sub>

## 19. Familiar, Lunar Wolf and wand charging

Check id: `horizons.wolves`

**Steps**

1. Read its research entry ("Dog Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Familiar and a Lunar Wolf stand ahead; an empty wand is on your hotbar.
3. Wait beside the creatures.

**Expect**

- [ ] The wand slowly gains vis from the creatures nearby; the mobs look right.

<sub>Already covered by automated pack tests: `familiar_and_lunar_wolf_charge_wands`</sub>

## 20. Seawolf and Nether Hound

Check id: `horizons.sea_hound`

**Steps**

1. A Seawolf swims in a pool to the left and a Nether Hound stands on land to the right.
2. Make the hound angry.

**Expect**

- [ ] The Seawolf swims and never drowns; the Nether Hound breathes fire at intervals and leaves embers only when it attacks.

<sub>Already covered by automated pack tests: `seawolf_swims_and_never_drowns`, `nether_hound_breathes_fire_on_ticks`</sub>

## 21. Endersteed and Nightmare

Check id: `horizons.horses`

**Steps**

1. Read its research entry ("Horse Infusion", "Nightmare Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A tame Endersteed and a tame Nightmare stand ahead, a lava pool lies to the right; saddles are on your hotbar.
3. Ride the Endersteed and use its blink; ride the Nightmare over the lava and use its plane shift (with and without a rider).

**Expect**

- [ ] Endersteed blinks, has sane health; the Nightmare walks on lava and carries its rider through the plane shift.
- [ ] Horses are vanilla black plus a glow (documented). Feel: jump height, blink distance, balance.

<sub>Already covered by automated pack tests: `endersteed_bonuses_and_blink`, `nightmare_body_lava_and_jump_rules`, `nightmare_plane_shift_carries_the_horse_and_any_rider`, `zombie_and_skeletal_horses_keep_their_bonuses`, `a_plain_horse_cannot_be_infused_to_a_nightmare`</sub>

## 22. Species infusions in the vat

Check id: `horizons.species_infusions`

**Steps**

1. Read its research entry ("General Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat with the Modified Runic Matrix on its lid stands ahead, with a cow, a sheep, a chicken and a pig beside it. The wand and the Thaumonomicon are on your hotbar.
3. Open the Thaumonomicon, find the species entries and craft two of them in the vat (see the research page).

**Expect**

- [ ] Every species recipe converts its creature and keeps its data (name, age, equipment).

<sub>Already covered by automated pack tests: `species_data_numbers_and_registry`, `every_species_recipe_converts_and_keeps_data`, `species_start_rules`</sub>

## 23. Self-infusion: the ritual, keys and effects

Check id: `horizons.self_infusion`

**Steps**

1. Read its research entry ("Self Infusion", "Human Infusion") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw vat with the Modified Runic Matrix on its lid stands ahead; the wand is on your hotbar.
3. Wand-click the vat, prepare a self-infusion as the research page says; enter standby with yourself as the subject.
4. Next: Open the Controls screen, category Thaumic Horizons: M, C and X are bound by default (the original shipped them unbound).
5. Press each key with no infusion.
6. Next: A stone-brick wall and a deep pool stand ahead; rotten flesh is on your hotbar.
7. Once you have the infusions: with Spider Climb walk into the wall and press C; with Amphibious swim; with Silverwood Heart eat the rotten flesh; with a potion infusion check your effects.

**Expect**

- [ ] The ritual stores the infusion in standby (it does not apply yet); the matrix and vat look right.
- [ ] Nothing happens without the matching infusion and nothing is sent.
- [ ] Spider Climb sticks to walls and toggles with C; Amphibious breathes water; the heart filters toxins and taint; the potion infusions hold their effect.
- [ ] Feel: climbing speed, swim speed, the message text.

<sub>Already covered by automated pack tests: `ritual_stores_the_infusion_in_standby`, `data_round_trips_through_save_and_sync`, `key_payloads_are_refused_without_the_infusion`, `spider_climb`, `amphibious_and_synthskin`, `silverwood_heart_filters_toxins_and_taint`, `potion_infusions`</sub>

## 24. Morphic Fingers

Check id: `horizons.morphic_fingers`

**Steps**

1. Read its research entry ("Morphic Fingers") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Planks and sticks are on your hotbar.
3. With Morphic Fingers press M, put items in the small crafting grid and craft.

**Expect**

- [ ] A workbench-like menu opens; it crafts and keeps nothing when closed.

<sub>Already covered by automated pack tests: `morphic_fingers_crafts_and_keeps_nothing`</sub>

## 25. Injector and Blast Phials

Check id: `horizons.injector`

**Steps**

1. Read its research entry ("Injector", "Blast Phial") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. An injector, injections and Blast Phials are on your hotbar; a dispenser with a lever stands to the right, aiming at a cow and a zombie.
3. Sneak and right-click the injector, load injections and phials; draw it like a bow at short and full pull; throw a phial; open the drum with an enchanted injector.
4. Put the injector in the dispenser with ammunition.

**Expect**

- [ ] The drum holds seven, rotates, fires syringes that hit and can be recovered; the phial splashes within four blocks; the enchantments survive opening the drum. Blast Phials are Thaumaturge phials with its animated liquid: red for the blood phial, the potion colour for a potion one.
- [ ] Feel: draw time, damage, the drum's look in hand.

<sub>Already covered by automated pack tests: `injector_draw_curve`, `injector_loads_fires_and_rotates`, `injector_gui_keeps_enchantments`, `syringe_hits_and_recovery`, `phial_splash_applies_effects_in_radius`, `phial_throws_and_registers`</sub>

## 26. Alchemite

Check id: `horizons.alchemite`

**Steps**

1. Read its research entry ("Alchemite") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A stone bank with ores and alchemite blocks stands nine blocks ahead (two alchemites side by side); flint and steel is on your hotbar.
3. Light one alchemite, stand well back; light the two adjacent ones.

**Expect**

- [ ] The block flashes, blasts for five blocks without fire, drops essentia crystals in place of items, chains to its neighbour.
- [ ] Feel: crystal counts.

<sub>Already covered by automated pack tests: `alchemite_ignites_blasts_and_chains`, `alchemite_node_outcomes`</sub>

## 27. Liquefaction, Disintegration and Illumination foci

Check id: `horizons.foci`

**Steps**

1. Read its research entry ("Focus Liquefaction", "Focus Disintegration", "Focus Illumination") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Focal Manipulator stands beside you; ahead are stone, ice, iron ore and gold ore blocks, items on the ground and a cow. The wand is on your hotbar.
3. Build each spell in the Focal Manipulator and cast it at the blocks, items and the cow; place light orbs and strike one.

**Expect**

- [ ] Liquefaction melts and smelts; Disintegration turns blocks and items into crystals; Illumination leaves an orb that goes when struck; each costs vis from a wand in the hotbar.
- [ ] Feel: speeds and vis costs; Illumination has no dye recipe (the colour is a setting).

<sub>Already covered by automated pack tests: `liquefaction_block_classes`, `liquefaction_ores_purity_and_nuggets`, `liquefaction_items_creatures_area_and_protection`, `disintegration_blocks_items_and_creatures`, `illumination_places_orbs`, `the_parts_work_through_real_casts`</sub>

## 28. Lens wheel, B key and Lens Case

Check id: `horizons.lens_wheel`

**Steps**

1. Read its research entry ("Lens Case") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the goggles; five lenses and the Lens Case are on your hotbar.
3. Hold B (bound by default; V belongs to the bracelets), move the mouse toward a lens and release; press Shift + B to take the lens out.
4. Right-click the Lens Case, put the lenses in; carry it in the inventory, then in the Curios belt slot, and use the wheel again.

**Expect**

- [ ] The wheel shows the lenses you carry on a ring, the highlighted one grows and is named; releasing chooses it, the old lens returns to a case or the inventory; one lens of each kind.
- [ ] A case on the belt feeds the wheel but cannot be opened there (as the original). Feel: the wheel size, the mouse release and re-grab; B no longer clashes with the bracelets' V.

<sub>Already covered by automated pack tests: `lens_storage_and_swap`, `lens_case_on_the_belt_is_used`, `goggles_in_curios_and_without_goggles`, `lens_case_menu_storage`</sub>

## 29. Illumine and Echo lenses

Check id: `horizons.lens_night`

**Steps**

1. Read its research entry ("Lens Fire", "Lens Water") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the goggles; the Illumine and Echo lenses and a night vision potion are on your hotbar. A dark stone cave with a pool stands ahead.
3. Wear Illumine: stand in the dark cave, then dive into the water. Wear Echo: dive, then surface. Drink the night vision potion with each lens and leave the water.

**Expect**

- [ ] Illumine gives night vision out of water only; Echo only under water and clears the blue tint; no potion icon appears; the real potion is never cut short; the effect does not flicker.

<sub>Already covered by automated pack tests: `night_vision_rules`</sub>

## 30. Evanescent lens

Check id: `horizons.lens_evanescent`

**Steps**

1. Read its research entry ("Lens Earth") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the goggles with the Evanescent lens and carry a pickaxe; a stone wall with ores behind its face, a chest and a torch stand ahead.
3. Look at the wall, the floor and the ores; sweep the crosshair across blocks; mine the block you look at; look at the chest and the torch.

**Expect**

- [ ] The 3 x 3 blocks on the face you look at turn clear and you see one block deeper; the clear patch follows the crosshair without flicker; mining the looked-at block works at the normal speed; chests, torches and glowing blocks stay solid; nothing changes for other players.
- [ ] Feel: re-render stutter when sweeping fast, the look of the clear frame.

<sub>Already covered by automated pack tests: `evanescent_answers_with_the_real_blocks_hardness`</sub>

## 31. Kirlian lens

Check id: `horizons.lens_kirlian`

**Steps**

1. Read its research entry ("Lens Air") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the goggles with the Kirlian lens; a stone wall stands ahead with a cow, a pig, a zombie and a skeleton hidden behind it.
3. Look at the wall in first person, then switch to third person.

**Expect**

- [ ] Living creatures show blue ripples, undead a red vortex, through the wall; nothing shows in third person; the marks scale with distance.
- [ ] Feel: strength and size of the marks (our alpha and size are tuned by eye, not the original's numbers).

## 32. Scholar's lens

Check id: `horizons.lens_scholar`

**Steps**

1. Read its research entry ("Lens Order Entropy") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the goggles with the Scholar's lens; unscanned blocks (gold, lapis, bookshelf) and a cow stand ahead.
3. Look at an unscanned block, then at the cow; keep looking for four seconds; look away halfway.
4. Look at something already scanned.

**Expect**

- [ ] A purple bar fills for four seconds with runes and ticks and the scan completes (the thaumometer message appears); looking away resets it; scanned things show their name and aspects above the crosshair.

<sub>Already covered by automated pack tests: `scholar_scan_payload_grants_the_scan`</sub>

## 33. Greatwood and Thaumium boats

Check id: `horizons.boats`

**Steps**

1. Read its research entry ("Greatwood Boat", "Thaumium Boat") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A wide water pool with a wall at its far end and a lava pool beside it lie ahead; an oak boat, the Greatwood boat, the Thaumium boat and a dispenser are on your hotbar.
3. Place each boat on water and ride it; compare speed with the oak boat; ram the wall; place the Thaumium boat on lava and ride it; use the dispenser on water.
4. Break the Thaumium boat in lava.

**Expect**

- [ ] The Greatwood boat is about 1.3 times and the Thaumium boat about 1.4 times as fast and neither breaks on impact; the Thaumium boat floats on lava, you do not burn and the fire on your screen is hidden, and its drop does not burn.
- [ ] Feel: the speed, the boat colours, the blue runes on the Thaumium boat's sides and ends.

<sub>Already covered by automated pack tests: `boats_speed_lava_and_riders`</sub>

## 34. Balanced Shard, Shard Transmutation and the Shard Mill

Check id: `horizons.balanced_shard`

**Steps**

1. Read its research entry ("Shard Trans") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a crucible over a magma block (so it is already hot) with a crafting table beside it. Your hotbar holds one essentia crystal of each primal (three of air) and one of Permutatio, plus a water bucket.
3. Craft a Balanced Shard from one crystal of each of the six primals (any order). Fill the crucible with the water bucket, then drop the shard, two more air crystals and the Permutatio crystal into it.
4. Next: You have the Greatwood and Silverwood Shard Mills and eight Balanced Shards. Hold the Greatwood mill and cycle its selection until the Balanced shard appears. Load a Balanced Shard and mill it; also try the Silverwood mill.
5. Watch the powder and the cycling through all seven kinds.

**Expect**

- [ ] The shard crafts; the crucible gives a crystal of the chosen primal and uses the shard up; the shard icon looks like six colours of one crystal.
- [ ] Only the Greatwood mill offers and takes the Balanced shard; the Silverwood does not. Loading consumes the shard.
- [ ] The powder is a pale aura-coloured dust and does nothing else (as in the original).
- [ ] Judge this call: the cycling order and the colour.

<sub>Already covered by automated pack tests: `balanced_shard_is_shapeless_from_six_primal_crystals_and_tagged`, `shard_transmutation_outputs_the_right_crystal`, `stand_ins_are_replaced_by_the_balanced_shard`, `shard_mill_balanced`</sub>

## 35. Vis Dynamo and Essentia Dynamo

Check id: `horizons.dynamos`

**Steps**

1. Read its research entry ("Vis Dynamo", "Essentia Dynamo") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a Vis Dynamo with a Vis Relay four blocks to its side, and hold a full unfocused wand.
3. Hold right mouse on the dynamo with the wand, then right-click it empty-handed and switch some primals off.
4. Next: You stand in front of an Essentia Dynamo two blocks up, with a tube under it running down to a jar of fire essentia, and a Vis Relay beside it.
5. Watch the dynamo (a consumer on the relay is up to you): one unit should run it for about a second, the ring spinning while it burns.

**Expect**

- [ ] The ring rises and spins while held and the relay beam links; the menu has six aspect tags that grey when off; an off primal is not drawn from the wand; a focused wand casts instead (documented limit).
- [ ] One unit runs it for about a second at 12 cV per tick split over the primals; the ring spins while it burns; it takes the next unit only in the last second.

<sub>Already covered by automated pack tests: `vis_dynamo_hold_costs_and_output`, `vis_dynamo_hold_event_needs_an_aimed_unfocused_wand`, `essentia_dynamo_numbers`</sub>

## 36. Node Monitor

Check id: `horizons.node_monitor`

**Steps**

1. Read its research entry ("Node Monitor") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a small node with a Node Monitor on its east face and a redstone lamp beside the monitor. Your hotbar holds a full wand and one spare monitor.
3. Try the spare monitor on a block with no node (it should refuse). Drain one aspect with the wand to 1 point, then to 0, and watch the monitor and lamp.

**Expect**

- [ ] The monitor refuses a block with no node; at 1 point (or 0) its screen flips amber and the lamp lights within a second; it goes out when the aspect recovers.

<sub>Already covered by automated pack tests: `node_monitor_signals_at_one_point_or_nothing`</sub>

## 37. Ethereal Shard

Check id: `horizons.ethereal_shard`

**Steps**

1. Read its research entry ("Ethereal Shard") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand before a Vis Dynamo, a Vis Relay and an Ethereal Shard in a row, three blocks apart. Your hotbar holds a full wand and eight air crystals.
3. Right-click the shard with the crystals, hold the wand on the dynamo to feed the relay, wait, then tap the shard with the wand; finally break it.

**Expect**

- [ ] Capacity rises by 4 per crystal and the stack is used up; it fills 1 point per 100 cV drawn; the wand taps it like a node; breaking it drops the shard and capacity / 4 crystals per aspect.

<sub>Already covered by automated pack tests: `ethereal_shard_capacity_tapping_and_drops`, `ethereal_shard_fills_from_a_relay`</sub>

## 38. The planar rift: look, sound and hunger

Check id: `horizons.planar_rift`

**Steps**

1. Read its research entry ("Planar Rift") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand on an open pad with the creative Planar Vortex in slot 1 and the ordinary one in slot 2.
3. Place the creative one a few blocks ahead and stand back. Then place the ordinary one beside it (it grows for about 2.5 seconds, then turns hungry: leave the area).
4. Next: You stand ten or so blocks behind a patch of cobblestone with a few apples dropped beyond it, holding the ordinary Planar Vortex.
5. Walk up, place the vortex against the cobblestone, then back off about ten blocks and watch for about twenty seconds. See what is left.

**Expect**

- [ ] The creative rift is a black disc with a bright rim and a slowly turning halo, calm blue, with a low steady hum every three seconds; the ordinary one flickers red once it is hungry; both give off full light and cannot be walked into or broken in survival.
- [ ] Everything within fifteen blocks is pulled toward it, harder the closer it is; anything touching it is hurt; nearby soft blocks (dirt, stone, wood) are torn out and drop items; after about twenty seconds with no attenuator it collapses in a burst and is gone.

<sub>Already covered by automated pack tests: `recipes_and_research_are_loaded`, `rift_numbers_are_the_originals`, `rift_grows_eats_and_collapses_on_time`, `hungry_rift_pulls_hurts_and_spares_creative_players`</sub>

## 39. Vortex attenuators and nodes

Check id: `horizons.attenuators`

**Steps**

1. Read its research entry ("Vortex Stabilizer") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of an ordinary Planar Vortex floating head height, ringed by six powered Vortex Attenuators (one on each side, a redstone block behind each).
3. Watch the beams and that the rift stays calm. Break one attenuator (it should hunger again; rebuild or restage). Throw a stone into the rift, then right-click the rift with the wand.
4. Next: You stand before a hungry node eight blocks ahead and a stone block three blocks ahead in line with it. Your hotbar holds two attenuators and two redstone blocks.
5. Place an attenuator on the stone block's far (node-facing) side so its muzzle faces the node, then power it with a redstone block beside it. Remove the power, then break it, and watch the node.

**Expect**

- [ ] Each powered attenuator shows a pale-blue beam to the rift; with six the pulling stops and the rift stays open indefinitely; with five it is hungry again; unpowering or breaking one lets it hunger. A wand click on the rift does nothing when nothing is stored (void crafting arrives in a later cycle).
- [ ] The node stops pulling while the beam holds it and the beam is visible; when the attenuator is powered off, broken, or its chunk unloads, the node is hungry again. Two attenuators on one node keep it calm until both are gone.

<sub>Already covered by automated pack tests: `six_attenuators_hold_a_rift_stable`, `dispatcher_claims_items_only_when_stable`, `wand_click_pops_stored_items_one_at_a_time`, `attenuator_holds_a_hungry_node_normal_and_gives_it_back`</sub>

## 40. Transduction Amplifier and the fourth amplifier

Check id: `horizons.amplifier`

**Steps**

1. Read its research entry ("Transduction Amplifier") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of an energized node floating just above the ground, with two cows nearby. Your hotbar holds three transduction amplifiers and three redstone blocks.
3. Fix one amplifier to a side of the node and power it with a redstone block. Add a second, then a third, with free air around and the cows in view.
4. Next: You stand eight blocks back from an energized node with four unpowered amplifiers on its four sides and a bedrock block two blocks above it. Your hotbar holds four redstone blocks.
5. Power the amplifiers one at a time with the redstone blocks (place each against the back of an amplifier, from a distance), the fourth last, then watch.

**Expect**

- [ ] With one amplifier the node's vis total and refill rise by ten per aspect; with two, bolts of sparks hit living things within ten blocks about every 2.5 seconds; with three, now and then flux gas or goo appears in the air around it; removing an amplifier takes its ten back.
- [ ] The node turns into a planar vortex about a second after the fourth is powered; the four amplifiers stay in place while the rift grows (about two and a half seconds), then it eats every block in the 5x5x5 around it at once, bedrock included (the amplifiers, the transducer above), and is hungry until held.

<sub>Already covered by automated pack tests: `amplifier_boost_follows_the_signal_and_the_block`, `fourth_amplifier_makes_the_rift_with_the_compound_aspects`</sub>

## 41. Wisp essence

Check id: `horizons.wisp_essence`

**Steps**

1. Read its research entry ("Wisp Spawn") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a wisp hanging in the air five blocks ahead (it will not move) and an arcane workbench. Your hotbar holds two wisp spawn eggs, an Ethereal Shard and a sword.
3. Kill the wisp and look at what it drops. Open the Horizons creative tab and find the Ethereal Essence of each aspect.
4. Craft the Planar Conduit at the workbench with any kind of essence on the four edges (you need the other parts: or just try an essence in the grid). Place the Ethereal Shard and right-click it with a stack of essence of one aspect, then break the shard.

**Expect**

- [ ] The wisp drops one Ethereal Essence of its own aspect (and no essentia crystal); every essence is a grey wisp tinted by its aspect colour, named with the aspect.
- [ ] The conduit accepts any essence and not an essentia crystal. The shard takes the whole stack (4 capacity per essence) and not crystals; breaking it drops the essences back (capacity / 4 per aspect).

<sub>Already covered by automated pack tests: `a_wisp_drops_wisp_essence_of_its_aspect`, `wisp_essence_is_tagged_and_the_conduit_and_shard_take_it`, `ethereal_shard_capacity_tapping_and_drops`</sub>

## 42. Wisp swarm from salis mundus

Check id: `horizons.wisp_swarm`

**Steps**

1. Read its research entry ("Wisp Spawn") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival six blocks from a creative planar vortex, holding 64 salis mundus (stand back: wisps attack).
3. Throw 2 salis mundus into the rift and look at the wisps' colours. Then throw in 8 more, then keep throwing salt while watching the count of wisps near the rift (about 32 within 32 blocks stops it).

**Expect**

- [ ] Each grain makes between one and four wisps at the rift, so 2 grains give 2 to 8. Their aspects are drawn from the rift's own aspects (a creative rift may hold none: the wisps then pick as wild ones do).
- [ ] The rift takes one grain per item per half second, not the whole stack at once. While 32 or more wisps are within 32 blocks it takes no grain at all and the salt waits in the box; kill some wisps and it resumes (the limit is wispCap in the planar config).

<sub>Already covered by automated pack tests: `salis_mundus_makes_one_to_four_wisps_per_grain_of_the_rifts_aspects`, `the_wisp_cap_pauses_the_salt`</sub>

## 43. Making a pocket plane and walking in and out

Check id: `horizons.planar_theory`

**Steps**

1. Read its research entry ("Planar Theory", "Pocket Plane") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of two stable (creative) rifts. Slot 1 holds a primordial pearl already renamed "Anvil Plane"; slot 2 holds an unnamed pearl.
3. Throw (Q) the named pearl into the left rift and the unnamed one into the right rift. Then run /thaumichorizons plane list to read the two plane names.
4. Open the Pocket Plane research entry in the Horizons tab.
5. Next: You stand two blocks from the rift of a freshly made forge plane (made by /thaumichorizons plane preset forge).
6. Walk into the rift. Look around the arrival pad. Walk into the vortex in the middle of the pad.
7. Go back in, then break (creative) the origin rift from outside. Walk into the vortex again.
8. Next: You stand two blocks from the rift of the huge plane (radius 127).
9. Walk in, then walk and fly across the plane edge to edge, and note whether the game stutters when new chunks appear. Leave and come back.

**Expect**

- [ ] The pearl is used up whole in a small blast and the rift now makes a plane: a rift that has made one stops taking void-craft items. The research entry reads as the original's three pages with a note on how to enter and leave.
- [ ] The first plane carries the pearl's anvil name; the second the name of whoever threw the pearl with 's Pocket Plane after it (use /thaumichorizons plane list to read them).
- [ ] You arrive on a five by five pad of arcane stone beside a glowing vortex, with open air above, a few seconds after generation starts; there is a short pause the first time while chunks draw themselves.
- [ ] The vortex returns you to the rift's block; you are not sent straight back in (a short cooldown).
- [ ] With the origin rift gone the vortex still works and sends you to your respawn point with a message, never leaves you stuck.
- [ ] The plane is radius 127. Entering takes a moment while the chunks near the pad draw; afterwards new chunks appear without long freezes, and the plane looks the same after leaving and returning (nothing regenerates differently).

<sub>Already covered by automated pack tests: `pearl_handler_claims_only_the_pearl_and_waits_for_the_dimension`, `record_codec_and_saved_data_round_trip`, `transfer_targets_and_safe_exit`, `paint_shell_pad_and_nothing_outside_the_radius`, `paint_is_deterministic_by_seed_and_independent_of_order`, `weight_table_is_valid_and_feeds_the_formulas`</sub>

## 44. The plane's world and blocks

Check id: `horizons.plane_world`

**Steps**

1. Read its research entry ("Pocket Plane") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival mode in front of a row of blocks: the Planar Boundary, Dust, Brain and the six Infused Stones (air, earth, fire, water, order, entropy). A strip of Dust lies behind the row. Your hotbar holds a diamond pickaxe and a silk touch pickaxe.
3. Break the Infused Stones with the diamond pickaxe, then break one again after placing it back with the silk touch pickaxe. Walk through the Dust strip.
4. Next: You stand two blocks from the rift of a forge plane.
5. Walk in and walk to the edge, look up and across, look at the light and the fog, dig down a little, find a cave. Use the exit vortex to come back, then run /thaumichorizons plane visit storm (and later charnel) and look around those the same way.

**Expect**

- [ ] The Planar Boundary is a deep violet void with slow motes drifting upward (animated); Dust is a pale sandy block a little shorter than a full block; Brain is a pink folded block; each Infused Stone is grey stone with flecks in its primal's colour (yellow air, green earth, orange fire, blue water, white order, dark purple entropy).
- [ ] The Boundary cannot be broken in survival. An Infused Stone drops one to three essentia crystals of its primal with the diamond pickaxe and itself with silk touch. Walking in Dust is clearly slowed. Brain drops two or three brains.
- [ ] Every block has a name in its own colour set (Air Infused Stone and so on) and an item in the Horizons creative tab.
- [ ] Each plane is a hollow sphere: land in the lower half, open air above, a thin dark violet shell all round with no gaps. There is no sun, moon or stars, a dark indigo fog, and light that never goes fully black (ambient glow).
- [ ] forge: a desert of sand over stone over netherrack, with ore pockets and crystal clusters in caves. storm: grass, flowers and saplings with snow on top (its recipe is cold taiga), a few animals. charnel: a bed of flesh with brain clumps, an eerie biome, rings of ancient stone just inside the shell.
- [ ] Biome colours (grass, sky tint at the horizon of the fog, water) match the biome each plane names in the chat when created.

<sub>Already covered by automated pack tests: `dimension_jsons_parse_against_the_registries`, `every_block_the_generator_can_place_exists`, `radius_colour_noise_life_biome_are_the_originals`, `layer_stack_of_the_three_recipes`, `paint_is_deterministic_by_seed_and_independent_of_order`, `creature_points_are_capped_and_inside_the_plane`, `qa_presets_make_ordinary_planes`</sub>

## 45. The plane's features, crystals and potion effects

Check id: `horizons.plane_features`

**Steps**

1. Read its research entry ("Pocket Plane") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival in front of an Eye Cluster, a Bone and a Lump of Flesh, with three spikes beyond them: a metal one on the grass, a wooden one under a stone slab and a toothed one on a stone wall. Your hotbar holds a diamond pickaxe and a Fortune III one.
3. Break each of the three blocks (with and without Fortune; place them again from the drops). Walk into each spike, then break the block a spike stands on.
4. Next: You stand in front of a row of the sixteen dye Crystals, white to black, and a small stone room beyond it with a Deep Crystal inside (door straight ahead).
5. Look at the Crystals (place a few more of one colour side by side to check for seams) and at the Deep Crystal in the dark room.
6. Next: You stand two blocks from the rift of a charnel plane.
7. Walk in, then walk or fly across the plane: the surface, the ravine, the caves. Look for the Primordial Fossil ribs in the boundary wall (make more planes with /thaumichorizons plane preset forge and storm and look at each).
8. Break a Primordial Fossil: the research entry Primordial Fossils appears in the Horizons tab.
9. Next: You stand in survival two blocks from the rift of a forge plane. (/thaumichorizons plane list shows each plane's effects; presets storm and charnel have other aspects. The Motion and Travel and Weapon or Flight cases need real nodes and are not staged.)
10. Walk in and watch your effect icons for five seconds, walk out through the exit vortex and keep watching for fifteen.

**Expect**

- [ ] The Eye Cluster is a purple-pink block with staring eyes and drops three to five spider eyes; the Bone is pale bone and drops three to five bones; the Lump of Flesh is a red-pink lump and drops rotten flesh (the original dropped bones, a copy slip).
- [ ] A spike is the original's cone (a metal, a wooden and a toothed one) that points away from the block it is placed on, on any of the six sides; it hurts like a cactus (one point, with the usual hit pause) when you stand in it, and drops itself when the block behind it goes.
- [ ] Each crystal is a faceted translucent block in its dye colour (white to black), neighbouring crystals of one colour show no seams. The Deep Crystal glows (light 15) and its texture shimmers slowly.
- [ ] Eyes, bone piles, a ribcage or two, pink lumps of flesh, pale dust drifts and rings of teeth (a maw) lie on the ground in a density that reads as dressing, not clutter; one narrow ravine cuts the ground. Caves hold toothed spikes on their floors and ceilings, eyes, bone beds and geodes.
- [ ] The fossil is dark with green veins, breathes smoke from its exposed faces and looks like part of something larger coming out of the wall; nothing stands within a few blocks of the arrival crater.
- [ ] A storm plane shows crystal spires in colours that match its aspects, and crystal geodes with Deep Crystal in the lower caves; a forge plane shows metal spike patches and a ravine. On a plane whose top layer is water the features stand on the lake floor.
- [ ] Inside a plane the effects of its aspects appear within five seconds and stay while you are in it (Motion and Travel together give Speed II, one alone Speed I; Weapon gives Strength, Flight Jump Boost, Tool Haste, Armor Resistance, Heal Regeneration), without particles.
- [ ] Fifteen seconds after you leave through the vortex they are gone. Nothing runs while nobody is in the plane.

<sub>Already covered by automated pack tests: `block_drops_and_the_flesh_fix`, `spikes_hurt_mount_on_any_solid_side_and_dust_drags`, `features_follow_their_drivers_in_the_three_recipes`, `nothing_lands_near_the_pad_or_at_the_shell`, `fossils_follow_their_chance_and_stay_inside_the_shell`, `ravines_cut_the_ground_and_lake_floors_get_features`, `features_are_deterministic_and_paint_into_chunks`, `effects_rule_speed_two_with_motion_and_travel`</sub>

## 46. Meat and Mercurial Slimes

Check id: `horizons.slimes`

**Steps**

1. Read its research entry ("Pocket Plane") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival on easy, holding a sword and the two slime spawn eggs, two blocks from the rift of a charnel plane (it holds flesh).
3. Use both eggs here, fight a large slime of each and look at the pieces. Then walk into the plane and look for Meat Slimes on the ground (run /thaumichorizons plane preset forge and visit that rift for Mercurial Slimes).

**Expect**

- [ ] The Meat Slime is a red-pink slime and the Mercurial Slime a silver one; both behave and split as vanilla slimes do (the pieces are their own kind) and drop nothing. Their landing puffs are red dust and snow shards.
- [ ] Planes with Flesh, Slime or Hunger hold some Meat Slimes, planes with Metal, Poison, Exchange or Mechanism some Mercurial Slimes, in the numbers of the creature cap (100 mobs of all kinds).

<sub>Already covered by automated pack tests: `slimes_split_without_drops_and_the_plan_spawns_them`</sub>

## 47. Planar clouds and their rain: looks and weather sync

Check id: `horizons.clouds_look`

**Steps**

1. Read its research entry ("Planar Clouds") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival in front of two rows of the ten cloud blocks, in the creative tab order (Mundane, Plasma, Thunder, Acid, Alloy, Tumorous, Vis, Glyph, Spore, Animus); the second row repeats the first.
3. Walk through them. Try to break one in survival, then in creative. Stand inside a Plasma Cloud, an Alloy Cloud and an Acid Cloud for a few seconds each.
4. Next: You stand in creative two blocks from the rift of a storm plane.
5. Walk in, look up from the ground, then fly up to the clouds. Come back and run /thaumichorizons plane preset forge and charnel for the other two recipes.
6. Next: You stand in creative with rain on. Seven blocks above the grass ahead hang a Mundane, a Plasma, an Acid, an Alloy, a Tumorous and a Spore Cloud in a row, and further east (the part of the pad that was turned into a snowy biome) another Mundane Cloud.
7. Watch the rain for ten seconds, then walk close and look up the columns from below. Compare the snow column in the east.
8. Next: You stand in creative on a clear day, two blocks from the rift of a storm plane; a Cloud floats seven blocks up behind it.
9. Walk into the plane, run /weather rain and then /weather clear (from inside it), and watch the planar clouds. Leave and come back while it rains; the Overworld cloud outside rains with the weather too.

**Expect**

- [ ] Ten different soft clouds (white, ember, dark storm, green, grey metal, red-pink, violet, white-gold, pale green, yellow), animated; the glowing ones (Plasma, Alloy, Vis, Glyph, Animus) light their surroundings. You walk straight through them; neighbouring clouds of one kind show no seams between them. They cannot be broken in survival.
- [ ] Plasma and Alloy set you on fire for six seconds; Acid hurts you one point a hit (dissolve damage); the rest do nothing.
- [ ] Flat two-layer cloud blobs, five to nine blocks across and ragged at the edge, hang high in the plane, well inside the boundary; a storm plane shows white clouds and dark Thunderclouds and pale-green Spore Clouds, a forge plane ember Plasma and grey Alloy clouds, a charnel plane red Tumorous and white-gold Glyph clouds. They read as clouds from the ground, not as floating blocks.
- [ ] Plasma, Thunder, Acid and Animus clouds may sit anywhere, over the arrival pad too (a design answer): look for one and judge whether that is fair to arrive under.
- [ ] While it rains, each cloud drops a one-block-wide column of rain to the first block under it, scrolling downward and glowing (additive): blue for the Mundane Cloud, embers for Plasma, green for Acid, dark grey for Alloy, red for Tumorous, pale green for Spore; violet for Vis, white for Glyph, yellow for Animus. A cloud directly above another has no column. No column shows when it is not raining. In a cold biome the column is snow.
- [ ] Frame rate does not suffer with many clouds in view.
- [ ] The planar rain starts within a moment of the overworld rain and stops when it clears; on re-entering or joining while it rains, the columns are already there. In the Overworld itself a placed cloud rains with the weather too.

<sub>Already covered by automated pack tests: `clouds_paint_into_air_only_and_are_registered_blocks`, `contact_fire_acid_and_spore_cows`, `cloud_kinds_follow_the_three_recipes`, `bodies_count_altitude_and_shell`, `the_controller_runs_only_while_it_rains`</sub>

## 48. What clouds do and shed

Check id: `horizons.clouds_effects`

**Steps**

1. Read its research entry ("Planar Clouds") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand with rain on in front of a row of targets with a cloud above each: under Mundane Clouds farmland, a cauldron and dirt with a fire on top; under Plasma Clouds leaves, ice, grass and planks; under Acid Clouds leaves and grass; a cow under a Spore Cloud and an Enderman under a Cloud (neither moves).
3. Wait half a minute and watch each target.
4. Next: You stand with rain on in front of a row of seven clouds seven blocks up, left to right: Thunder, Alloy, Tumorous, Vis, Glyph, Spore (over grass) and Animus (over a stone block). Your hotbar holds a full wand for the vis orbs.
5. Wait a few minutes and watch what each sheds (keep away from the Animus golem).

**Expect**

- [ ] Mundane rain wets farmland, fills a cauldron to the top and puts out fire on the block it falls on; the Enderman takes damage and the burning player or mob is put out. In a cold biome it lays a layer of snow on solid blocks instead.
- [ ] Plasma and Alloy turn leaves and plants into fire, ice into water, grass into dirt and light flammable blocks into fire; stone is left alone. Acid removes leaves and plants and turns grass into dirt, and hurts what stands under it. The Spore Cloud turns a cow into a mooshroom with a puff.
- [ ] Thundercloud: lightning strikes the ground below every minute or so (not the whole sky). Alloy: nuggets (gold, silver, copper, tin, lead, quicksilver, mostly iron) that cannot be destroyed by fire or lava. Tumorous: raw beef, pork, chicken or fish and mostly Unidentifiable Meat (food; cooks in a furnace). Vis: a glowing aspect orb of a primal (collect it with a wand). Glyph: small experience orbs. Spore: grass gets flowers, saplings (also Greatwood and Silverwood), Shimmerleaf, Vishroom, dirt turns to grass or mycelium, sand gets cacti, farmland crops. Animus: lightning that turns the block it strikes into a berserk golem for a minute, which attacks you; the stone block is gone while it lasts.

<sub>Already covered by automated pack tests: `default_clouds_wet_farmland_fill_cauldrons_and_put_out_fire`, `plasma_and_alloy_melt_acid_dissolves`, `contact_fire_acid_and_spore_cows`, `drops_spores_bolts_and_the_animus_golem`, `spore_clouds_plant_the_blocks_below`, `drop_timers_tables_and_columns`</sub>

## 49. Lifting a cloud with a wand

Check id: `horizons.cloud_pickup`

**Steps**

1. Read its research entry ("Planar Clouds") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival with a Cloud block placed three blocks ahead, a Cloud item dropped at your feet, and a full wand in slot 1 and an empty one in slot 2. Pocket Plane is done; Planar Clouds is not.
3. Pick up the cloud item and look in the research book (Planar Clouds, Wild weather). Then right-click the placed cloud with the full wand, then with the empty wand. Place the item again. Check the wand's Aer before and after.

**Expect**

- [ ] Picking up any cloud item unlocks Planar Clouds (once Pocket Plane is done), three pages about the ten kinds. Right-clicking a cloud with a wand costs 100 Aer vis (a little more with some caps) and leaves an item that cannot be destroyed; an empty wand does nothing and says so. The item places like a block and the placed cloud rains and works like a generated one.

<sub>Already covered by automated pack tests: `the_wand_lifts_a_cloud_for_100_aer_once_the_research_is_done`, `picking_up_a_cloud_item_unlocks_the_research`</sub>

## 50. Keystone, frame and opening a gateway

Check id: `horizons.gateway_open`

**Steps**

1. Read its research entry ("Planar Keystone") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand two blocks from the rift of a forge plane with two blank keystones.
3. Walk into the rift. Use a blank keystone on a block that is not the vortex at the centre, then on the vortex. Read the imprinted keystone's name and tooltip.
4. Run /thaumichorizons plane preset storm, go in there too and imprint the second keystone: the two should differ in tint.
5. Next: You stand in front of a finished gateway frame five blocks ahead (the Keystone Receptacle top middle) and, two blocks ahead, the rift of a forge plane. Slot 1 holds a blank keystone.
6. Open the research Planar Gateways and compare its gateway page with the frame. Walk into the rift and imprint the keystone on the exit vortex, come back out.
7. Right-click the receptacle with the imprinted keystone. Take it out with an empty hand and put it back.
8. Next: You stand in front of a gateway frame with its receptacle and, two blocks ahead, the rift of a forge plane. Your hotbar holds an empty wand, a full wand and a blank keystone.
9. Imprint the keystone on the plane's exit vortex (walk through the rift), come back and slot it in the receptacle. Right-click the receptacle with the empty wand (should refuse), then with the full wand.
10. Try again with one wrong frame block (break a frame block first). Watch the vis, the frame and the sound when it opens.
11. Next: You stand in front of a gateway frame and a forge plane's rift. Your hotbar holds a full wand and a blank keystone.
12. Imprint the keystone in the plane, slot it in the receptacle and open the gateway. Stand a few blocks from it and watch it; step through.

**Expect**

- [ ] Only the exit vortex imprints. A blank keystone reads Blank Planar Keystone with no tooltip and no tint; an imprinted one reads Planar Keystone with the plane's name below and the keystone art tinted in the plane's colour.
- [ ] Two planes give two colours.
- [ ] The research page shows the same frame. The receptacle is an open iron-bound cube; with a keystone slotted a tinted cube shows in its middle, in the plane's colour; the keystone comes back to your hand.
- [ ] Too little vis: a message, nothing changes and nothing is drawn; same for a wrong frame block. With enough vis 250 of every primal is drawn (a little more or less depending on the cap), the frame blocks turn into carved gateway blocks, a violet portal fills the middle and the wand sound plays.
- [ ] The portal looks like a vanilla portal sheet with portal particles; the frame blocks show carved corner and edge art. Opening plays the wand sound, closing the craft-fail sound.

<sub>Already covered by automated pack tests: `imprint_accepts_only_a_planes_exit_vortex`, `the_plane_key_round_trips_and_names_the_stack`, `frame_x_aligned_is_recognised_and_one_wrong_block_fails`, `frame_z_aligned_is_recognised`, `the_keystone_goes_in_comes_out_and_drops_when_the_receptacle_breaks`, `the_research_entry_and_recipes_are_in_the_jar`, `the_cost_is_250_of_every_primal_and_a_short_wand_loses_nothing`, `converting_and_closing_replace_every_cell`, `a_gateway_with_no_plane_loaded_changes_nothing_and_costs_nothing`</sub>

## 51. Walking through, four gateways, closing and a second player

Check id: `horizons.gateway_use`

**Steps**

1. Read its research entry ("Planar Keystone") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a gateway frame with its receptacle and, two blocks ahead, the rift of a forge plane. Your hotbar holds a full wand and a blank keystone.
3. Imprint the keystone in the plane, slot it in the receptacle and open the gateway with the wand. Walk into the open gateway, look around where you arrive, then walk back into the plane's portal.
4. Rebuild the frame turned the other way (X and Z) and repeat.
5. Next: You stand in front of one gateway frame with its receptacle and a forge plane's rift two blocks ahead. Your hotbar holds a full wand, five blank keystones, three more receptacles and the frame blocks for three more frames.
6. Imprint the keystones on the plane's exit vortex, open this gateway, build and open three more with keystones of that plane, then try a fifth. In the plane walk round to see the four portals.
7. Next: You stand in front of a gateway frame with its receptacle and a forge plane's rift two blocks ahead. Your hotbar holds a full wand, a blank keystone and a spare receptacle.
8. Imprint the keystone, slot it, open the gateway. Take the keystone out with an empty hand. Reopen it and break the receptacle. Reopen with the spare receptacle and break one frame block. Each time watch the plane's portal.
9. Open it once more, stand in the plane at its portal while a frame cell is removed (/setblock a frame block to air from outside), and walk into the portal.
10. Next: You stand in front of a gateway frame and a forge plane's rift. Host a LAN game and have a second player join (they need the gateway research too).
11. Imprint the keystone in the plane, slot it, open the gateway, and have the second player look at the keystone (give them one), at the receptacle holding it, and walk through the gateway.

**Expect**

- [ ] You arrive inside a 3x3 portal on the edge of the plane, facing inward, with a short open alcove ahead (a deviation: the original had you stand with your head in the shell). Stepping out and back into that portal returns you to the receptacle's gateway, in the middle of the portal, facing out. No bouncing back and forth.
- [ ] Both frame alignments work.
- [ ] The fifth refuses with a message and draws no vis. The plane shows four portals, one on each side; each takes you to its own gateway.
- [ ] Every way closes it: frame blocks return to Advanced Alchemical Construct and Ancient Stone, the portal is gone, the craft-fail sound plays, the keystone drops or returns, and the plane's portal becomes solid boundary again.
- [ ] A portal left open after the frame is gone sends you to the plane's arrival pad with a message and seals itself; the slot is free again.
- [ ] The second player sees the plane's name and colour on the keystone and the tinted cube in the receptacle (the original showed white and no name on any client but the host).

<sub>Already covered by automated pack tests: `plane_side_portals_sit_on_the_matching_side_with_boundary_behind`, `four_slots_open_and_the_fifth_is_refused`, `breaking_a_frame_block_closes_the_gateway`, `a_stale_slot_is_not_live`, `the_plane_key_round_trips_and_names_the_stack`</sub>

## 52. Void putty out of a rift, and a repair

Check id: `horizons.void_putty`

**Steps**

1. Read its research entry ("Void Putty") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a creative planar vortex (always stable) with a crafting table beside you. Your hotbar holds 8 void ingots, a full wand, a damaged enchanted diamond sword, a damaged iron pickaxe, a fresh diamond pickaxe and a stick.
3. Throw the 8 void ingots in so they land inside the 3x3x3 box around the rift. Wait a second, then click the rift with the wand.
4. Put the damaged diamond sword and the putty in the crafting table, nothing else. Then try the sword with the stick added, the damaged pickaxe and sword together with putty, and the undamaged diamond pickaxe with putty.

**Expect**

- [ ] The ingots vanish; one click pops all 8 putty (one stored stack per click), with the chime. The putty shows the boiling purple blob icon.
- [ ] Sword plus putty gives the sword at full durability, sharpness still on and its name kept; every putty in the grid is used up. The other grids give nothing.

<sub>Already covered by automated pack tests: `void_ingots_become_stored_putty_popped_one_stack_per_click`, `putty_repair_matches_one_damaged_item_plus_putty_only`, `research_recipes_and_tag_are_in_the_jar`</sub>

## 53. Balanced Crystal Cluster

Check id: `horizons.balanced_crystal_cluster`

**Steps**

1. Read the "Crystal Wand" research entry: its recipe pages show the Balanced Crystal Cluster infusion (Balanced Shard at the centre, wheat seeds and Salis Mundus, the six primals, vitreus and vinculum).
2. Clusters are on your hotbar; a dark stone room lies ahead. Place one on the floor, one on a wall and one on the ceiling. Watch them for a while.
3. Break one by hand, one with a pickaxe, and one by removing the block it sits on.

**Expect**

- [ ] Each cluster points away from the face it sits on, glows faintly (about a torch half-way) and gives off sparks in the six primal colours.
- [ ] Breaking one drops one essentia crystal of each of the six primals; with its support gone it breaks too.
- [ ] Feel: it reads as a crystal cluster beside the host's seven, with all six primals in it.

<sub>Already covered by automated pack tests: `balanced_cluster_block_item_tags_light_and_drops`, `balanced_cluster_infusion_recipe`, `crystal_wand_recipe_takes_the_balanced_cluster_tag`</sub>

## 54. Crystalline wand

Check id: `horizons.crystal_wand`

**Steps**

1. Read its research entry ("Crystal Wand") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a creative planar vortex with an arcane workbench beside you. Your hotbar holds an Inert Crystal Wand, a full wand and a Vis Relay.
3. Drop (Q) the Inert Crystal Wand into the rift and click the rift with the full wand. Read the new wand's tooltip and vis bars.
4. Craft something that costs vis at the arcane workbench with it. Then hold it in a node's aura (or place the relay near it and put it on a vis charger), and wait. Look at it held in first and third person.

**Expect**

- [ ] A Crystalline Wand with 250 vis of each of the six primals. Crafting spends vis from it as from any wand (the 0.9 cap discount applies).
- [ ] Nothing refills it: not the node, not a charger, not a relay, not anything else.
- [ ] A pale pink rod with a pale cap.

<sub>Already covered by automated pack tests: `an_inert_wand_comes_back_as_a_crystalline_wand_with_250_of_each_primal`, `crystal_wand_store_ignores_increases_and_applies_decreases`</sub>

## 55. Voidling: follows, warns and turns guardian

Check id: `horizons.voidling`

**Steps**

1. Read its research entry ("Void Golem") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in survival on easy in front of a creative planar vortex. Your hotbar holds two golem animation powders, a golem seal, a golem bell and two zombie spawn eggs.
3. THROW one powder (drop it with Q) so it lands in the rift's box. Walk away and around, then fight a zombie with the voidling near.
4. Try the seal and the bell on it. Leave the game running for about ten minutes and watch the chat. Look at it beside an ordinary powder golem (make one by dropping the second powder away from the rift).
5. Next: You stand in survival in front of a creative planar vortex, holding two golem animation powders.
6. Throw a powder into the rift to make a voidling, then run /data merge entity @e[type=thaumichorizons:powder_golem,limit=1,sort=nearest] {pg_void_count:3} to skip the warnings. Wait (on average four minutes; stand a little way off).
7. Quit and reload the world with a voidling at count 2 (merge pg_void_count:2) and check it carries on.

**Expect**

- [ ] A dark golem with hearts and the wand sound appears. It starts following you from 16 blocks away, never expires and fights monsters; it takes no seal and the bell does nothing to it. Powder that is simply dropped by a dispenser, or that nobody threw, stays where it is.
- [ ] On average every four minutes or so a chat line: One of your golems is acting strangely; has begun softly chanting; then the italic purple hollow laughter.
- [ ] It is a Thaumaturge golem (the same shape as the host's golems, walking and idling like them) in dark void metal with black eyes (no glow); the ordinary golem is the block it came from. If you stand beside a hungry planar rift (fewer than six attenuators) with a voidling, the rift does not pull or hurt it, while an ordinary powder golem is dragged in.
- [ ] The voidling bursts in portal particles and smoke with a thump, and an Eldritch Guardian stands where it was; the guardian stays within about 32 blocks of that spot.
- [ ] The counter is saved: the reloaded voidling is still a voidling.

<sub>Already covered by automated pack tests: `golem_powder_makes_a_voidling_for_its_thrower_and_a_stranger_powder_is_left`, `a_hungry_rift_leaves_a_voidling_alone_and_pulls_a_normal_golem`, `a_voidling_follows_from_sixteen_blocks`, `voidling_counter_is_a_step_function_of_age_and_roll`, `voidling_turns_into_a_guardian_on_the_fourth_step_and_saves_its_count`</sub>

## 56. The Teleological Recombinator

Check id: `horizons.recombinator`

**Steps**

1. Read its research entry ("Recombinator") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a small node with a Teleological Recombinator directly above it and a redstone block in your hotbar.
3. Look at it from the side and from three-quarters, then the item in your hand. Put the redstone block beside the recombinator and watch the pearl and the space under it for about five seconds. Take the block away again.
4. Next: You stand in front of a node holding Ordo and Perditio, with a Recombinator above it, and a second node a few blocks to the side and slightly lower holding only Ignis. Your hotbar has a wand and a redstone block.
5. Scan the first node with the wand (or the thaumometer), then put the redstone block next to the Recombinator and wait about half a minute, scanning both nodes now and then. Remove the block when you are done.
6. Next: You stand in front of a node holding only Ordo, with a Recombinator above it, and a second node holding Ignis a few blocks to the side that sits on a Node Stabilizer.
7. Power the Recombinator with the redstone block and wait about twenty seconds; scan both nodes. Then put a lever on the stabilizer's neighbour block, or a redstone block beside the stabilizer, and wait again.

**Expect**

- [ ] Idle: a metal plate on top with four claws hanging under it holding a dark pearl, a small cap under the pearl; the item icon matches. Powered: the pearl starts to bob, gently at first and then by about two pixels, and after about two and a half seconds a crackling white lightning ring plays round the pearl and a few sparks drift down toward the node. Unpowered: the bobbing, ring and sparks fade out within about two and a half seconds and then everything is still.
- [ ] After a warm-up of about two and a half seconds, white-blue bolts jump from the second node to the first now and then (not every second, since it looks at a random nearby block); each bolt turns one Ordo into Potentia or one Perditio into Gelum in the first node and takes one Ignis out of the second; the first node's list gains compounds while the second node's Ignis falls. When the redstone is removed it stops.
- [ ] While the stabilizer is unpowered the second node is never drained and no bolts jump to the first (the first node stays Ordo only); once the stabilizer has a redstone signal the node is no longer locked and the fusing into Potentia starts.

<sub>Already covered by automated pack tests: `recombinator_warms_up_then_attempts_at_the_interval`, `recombinator_merges_and_respects_the_lock`, `recombinator_merge_arithmetic`, `recombinator_candidate_passes_prefer_primals`, `recombinator_idle_cases_do_nothing`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons`).
