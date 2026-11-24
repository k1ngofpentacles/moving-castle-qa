# QA: Horizons H1: the Vat

Chapter id `horizons_h1`, 9 checks. In game this is the FTB Quests chapter **QA: Horizons H1: the Vat**; each check there has a green "Set up this check" line that builds its test site.

## 1. Incubated egg hatches a chick

Check id: `horizons_h1.egg`

**Steps**

1. You stand in front of a dispenser loaded with incubated eggs (the lever beside it fires it) and a cow.
2. Throw an incubated egg from your hotbar at the ground, then at the cow, then flip the lever.

**Expect**

- [ ] A baby chicken every time, with a puff of white particles; no adult chickens, no damage to a mob hit.

<sub>Already covered by automated pack tests: `incubated_egg_hatches_a_baby_chicken`</sub>

## 2. Warded syringe sampling

Check id: `horizons_h1.syringe`

**Steps**

1. You stand between a cow (left, close) and a zombie (right, held still) with warded syringes on your hotbar.
2. Right-click the cow with a warded syringe, then the zombie, then the air.

**Expect**

- [ ] Cow: a Blood Sample named after the cow.
- [ ] Zombie: nothing happens, the syringe is kept.
- [ ] Air: a Blood Syringe (your own blood).

<sub>Already covered by automated pack tests: `syringe_samples_passive_mob`, `syringe_ignores_hostile_and_villager`, `syringe_in_air_gives_own_blood`</sub>

## 3. Seroconverter fills an injection

Check id: `horizons_h1.seroconverter`

**Steps**

1. A Seroconverter stands in front of you, a cow beside it, and warded syringes are on your hotbar.
2. Right-click the air with a syringe for a Blood Syringe and put it in the Seroconverter; pipe essentia into it from a jar with tubes (you must bring the jar and tubes), pick aspects in the palette, wait.
3. Use the injection on yourself, then strike the cow with one.

**Expect**

- [ ] The screen reads like the original (layout, palette); aspects with no working effect are not offered.
- [ ] Effects match the research page's patterns; feel of durations and strength.

<sub>Already covered by automated pack tests: `seroconverter_fills_an_injection_from_piped_essentia`, `injection_applies_its_effects`, `deferred_only_aspects_are_hidden`</sub>

## 4. Containment focus jars a creature

Check id: `horizons_h1.containment`

**Steps**

1. A cow stands six blocks ahead; an empty soul jar and the Containment focus are on your hotbar.
2. Channel the Containment focus at the cow (about 10 s).
3. Place the jar; wand-click it.

**Expect**

- [ ] The beam and jarring effect look right; the cow ends up drawn small inside the placed jar.
- [ ] Wand click releases the cow and the jar is gone. Players, golems and bosses are refused.

<sub>Already covered by automated pack tests: `capture_makes_a_jar_with_the_creature`, `release_restores_the_creature_and_destroys_the_jar`, `containment_refuses_what_it_cannot_take`</sub>

## 5. Form the Curative Vat

Check id: `horizons_h1.vat_form`

**Steps**

1. In front of you stands the raw vat: planks ring with an Alchemical Construct centre at the base and lid, glass ring with water between.
2. Wand-click any block of it.

**Expect**

- [ ] It turns into one vat with the original lid and base art and a blue water fill; vis is taken from the wand.
- [ ] Breaking any part turns it back into the raw blocks.

<sub>Already covered by automated pack tests: `vat_forms_with_wand`, `vat_break_reverts_and_kills`</sub>

## 6. Curative mode

Check id: `horizons_h1.vat_curative`

**Steps**

1. A raw vat stands in front of you, with a hurt, poisoned cow to its right. The wand, Containment focus and soul jars are on your hotbar, and you are hungry.
2. Wand-click the vat to form it; jar the cow with the focus and load it into the vat; pipe in Victus (bring a jar and tubes), then Victus + Alkimia.
3. Empty-hand click the vat's top to climb in yourself; pipe Desiderium.

**Expect**

- [ ] Victus alone heals 2 hearts at a time; Victus with Alkimia heals 4 and clears poison and similar effects.
- [ ] You are fed, and the Desiderium is used up. The cow floats visibly in the water.

<sub>Already covered by automated pack tests: `curative_victus_alone_heals_two_hearts`, `curative_victus_with_alkimia_heals_four_hearts_and_cures`, `curative_desiderium_feeds_a_player_and_is_consumed`</sub>

## 7. Incarnation

Check id: `horizons_h1.vat_incarnation`

**Steps**

1. A raw vat stands in front of you; the wand, raw beef and nutrients are on your hotbar.
2. Wand-click the vat to form it, open its screen, put raw beef in the sample slot and nutrients in the other; pipe 4 Victus (bring a jar and tubes).

**Expect**

- [ ] A cow fades in over about 40 s; feel of the fade and the sparkles.

<sub>Already covered by automated pack tests: `incarnation_from_raw_beef`, `incarnation_from_a_sample_demands_the_infusion_costs`</sub>

## 8. Creature infusion ritual

Check id: `horizons_h1.vat_infusion`

**Steps**

1. A raw vat with the Modified Runic Matrix on its lid stands ahead; four empty arcane pedestals ring it, and a cow waits beside. On your hotbar: the wand, the Containment focus, soul jars, a Swiftness II potion and two quicksilver.
2. Wand-click the vat to form it, jar the cow and load it in, put the potion and quicksilver on the pedestals, pipe in the essentia (bring jars and tubes); wand-click the matrix.
3. Try each infusion on a cow or wolf: Thaumium Claws, Enderheart (shoot it), Shockskin (hit it), Runic Hide, Eldritch Fangs, Instilled Loyalty (sit/follow), Portability (wand-click it).

**Expect**

- [ ] The ritual looks and sounds right; instability by symmetry; breaking the matrix kills the subject.
- [ ] Each trait behaves as its research page says; feel and balance.

<sub>Already covered by automated pack tests: `full_run_quicksilver_limbs`, `trait_enderheart_blinks_from_projectiles`, `trait_shockskin_zaps_its_attacker`, `trait_runic_hide_absorbs`, `trait_eldritch_fangs_poison_the_target`, `trait_instilled_loyalty_replaces_the_ai_and_sits`, `trait_portability_jars_the_creature`, `breaking_the_matrix_kills_the_subject`</sub>

## 9. Two players

Check id: `horizons_h1.multiplayer`

**Steps**

1. You stand in front of a raw vat with the wand, Containment focus, soul jars, Seroconverter and a cow ready.
2. With a second player on LAN (they use the same staging): watch the other run the vat, jar a creature, use the Seroconverter.

**Expect**

- [ ] Both see the occupant, water, ritual and jars the same; no desync or crash.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h1`).
