# QA: Phase 8: Assistant Seal, Golem Bydlo and the Balanced Shard

Chapter id `phase_8`, 11 checks. In game this is the FTB Quests chapter **QA: Phase 8: Assistant Seal, Golem Bydlo and the Balanced Shard**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumicconcilium:seal_assistant`, `thaumaturge:golem_bell`, `thaumicconcilium:golem_bydlo_spawn_egg`, `thaumicconcilium:shard_mill`, `thaumicconcilium:aura_core`, `thaumichorizons:blood_syringe`, `thaumichorizons:vat_matrix`, `minecraft:pig_spawn_egg`, `minecraft:cow_spawn_egg`, `minecraft:zombie_spawn_egg`, `minecraft:stone`, `minecraft:bedrock`

## 1. Assistant seal: a golem jars a pig from a blood sample

Check id: `phase_8.assistant_jar_pig`

**Steps**

1. A fenced pen lies ahead with a pig and a cow inside and a stone block at its near edge. Your hotbar has the Assistant seal, golem bell, Pig blood sample, a claw golem, soul jars and a Provider seal.
2. Place the Assistant seal on the stone block, open it with the golem bell and put the Pig blood sample in one filter slot (nine slots).
3. Place the golem near the seal and supply empty soul jars (a Provider seal with jars, or have a jar in its hands).
4. Wait up to a minute or two, watching the golem.

**Expect**

- [ ] The golem walks to the pig (not the cow), strikes it, and when the blow would kill it a soul jar holding the pig drops at the golem; the pig is gone.
- [ ] With no empty jar in reach the golem asks for one and does nothing else; a jar kit and a Provider fixes it.
- [ ] Judge this call: the walk, the hit and the jarring read clearly, and the golem does not stand idle.

<sub>Already covered by automated pack tests: `assistant_hunt_filter`, `assistant_jars_when_damage_reaches_health_else_hits`</sub>

## 2. Assistant seal: Order (weakened only) and Entropy (hostile too)

Check id: `phase_8.assistant_settings`

**Steps**

1. The pen ahead holds a full-health pig, a hurt pig and a still zombie (it is night); your hotbar has the seal, bell, Zombie blood sample, a claw golem and soul jars.
2. Place the Assistant seal on the stone block and open its GUI: read the Order and Entropy toggles. Put the Zombie sample in a filter slot and leave Entropy off, with the golem placed nearby.
3. Turn Entropy on and watch again. Turn Order on and watch with the full-health pig, then with the hurt one.
4. Try a wither or a player nearby, with samples of them if you can make one.

**Expect**

- [ ] Entropy off: hostile creatures are left alone; on: the zombie is hunted and jarred.
- [ ] Order on: only weakened prey is taken; a full-health pig is ignored until it is hurt.
- [ ] Your tamed pets, players, Thaumaturge golems and bosses are never jarred.
- [ ] Judge this call: the toggle names and descriptions in the GUI read sensibly.

<sub>Already covered by automated pack tests: `assistant_order_and_entropy_settings`, `assistant_hunt_filter`</sub>

## 3. Assistant seal: research and recipe

Check id: `phase_8.assistant_recipe`

**Steps**

1. The Assistant seal research is done and you hold a Thaumonomicon. In the Concilium tab find the Assistant seal entry (after Aura Core, the Butcher and Provider seals and Horizons' Containment focus). Read it and the infusion page.

**Expect**

- [ ] The entry appears and reads sensibly; the infusion shows a Butcher seal centre, a Provider seal stand-in, the Containment focus and two blood syringes.
- [ ] Judge this call: the Provider seal standing in for the original's Alchemy core (decision pending).

<sub>Already covered by automated pack tests: `assistant_registered_with_recipe_and_research`</sub>

## 4. Golem Bydlo: made in the vat from a Thaumaturge

Check id: `phase_8.bydlo_vat_chain`

**Steps**

1. A raw Curative Vat frame (planks, glass, water, alchemical constructs and a vat matrix on top) stands four blocks ahead; you have a wand, a Thaumonomicon, Thaumaturge spawn eggs, a blood syringe and a soul jar. Form and fill the vat (see the Horizons chapter).
2. Read the Brain Littering and Buff Golem entries and their infusion pages.
3. Load a Thaumaturge (spawn one) and run the Brain Littering infusion to make a Mad Thaumaturge, then Buff Golem to make a Golem Bydlo.
4. Afterwards try the vat on the Bydlo itself.

**Expect**

- [ ] Each infusion turns the creature into the next; its name and health stay; the Bydlo has 90 health.
- [ ] The Bydlo is refused by the vat afterwards.
- [ ] Judge this call: the recipe pages and ingredients read clearly in the research UI.

<sub>Already covered by automated pack tests: `bydlo_chain_converts_through_the_vat_and_keeps_data`, `bydlo_vat_refusal_and_chain_inputs`, `bydlo_stats_and_vat_refusal`</sub>

## 5. Golem Bydlo: the iron and brass model, standing and walking

Check id: `phase_8.bydlo_look`

**Steps**

1. A Golem Bydlo stands five blocks ahead. Look at it from the front, the side and the back, in daylight and in a dark place (/time set night to try).
2. Push it or lead it to make it walk; watch the legs, arms and body.

**Expect**

- [ ] A tall iron golem with brass plates, a furnace slit on the chest, a boiler hump on the back and long gauntlets to the knee; the head sits between the shoulder plates.
- [ ] The walk swings the legs and arms in opposition, with a heave in the body; it never freezes in a T pose.
- [ ] Judge this call: proportions against the original (ours swings less wide), and the texture.

<sub>Already covered by automated pack tests: `bydlo_stats_and_vat_refusal`</sub>

## 6. Golem Bydlo: riding

Check id: `phase_8.bydlo_ride`

**Steps**

1. A Golem Bydlo stands four blocks ahead, and beyond it a one-block step and then a two-block step of stone. Right-click the Bydlo with an empty hand to mount it. Walk it over the one-block step and the two-block step. Dismount and mount again, and try with a second player on LAN.

**Expect**

- [ ] You sit behind its shoulders and the camera feels right; the golem walks where you steer, climbs a full block while ridden, and one rider only.
- [ ] The arms are carried forward while ridden, not frozen; no model pokes through your legs.
- [ ] Judge this call: seat height, camera and steering feel.

<sub>Already covered by automated pack tests: `bydlo_ride_and_step_height`</sub>

## 7. Golem Bydlo: Excavation focus mines 5x5

Check id: `phase_8.bydlo_excavation`

**Steps**

1. A Golem Bydlo stands four blocks ahead and a stone wall with a bedrock block in it beyond; you have a wand and an Excavation (Break) focus. Socket the focus into the wand, ride the Bydlo and left-click the stone wall, then the part with bedrock.
2. Click rapidly several times.

**Expect**

- [ ] A 5x5 plane of the clicked face breaks, one layer deep, dropping items; bedrock and anything a protection mod forbids stay.
- [ ] A short cooldown (about a third of a second) limits the rate; no vis is spent.
- [ ] Judge this call: the speed and the sound and look of the swing.

<sub>Already covered by automated pack tests: `bydlo_excavation_respects_break_event`, `bydlo_commands_read_the_focus_and_keep_the_cooldown`</sub>

## 8. Golem Bydlo: Wrath Attraction punches

Check id: `phase_8.bydlo_wrath`

**Steps**

1. A Golem Bydlo stands four blocks ahead with still pigs and zombies beyond it; your wand has the Wrath Attraction focus. Ride the Bydlo, move in among them (plus a tamed wolf or another player on LAN if you want to test sparing), and left-click the air or an enemy.

**Expect**

- [ ] Everything living around the golem takes 10 to 24 damage and is flung up a little; you, the other player, tamed pets and your allies are not hurt.
- [ ] Both arms rise in a punch pose.
- [ ] Judge this call: the damage range and the feel of the punch.

<sub>Already covered by automated pack tests: `bydlo_punch_damage_range_and_friends_spared`, `bydlo_commands_read_the_focus_and_keep_the_cooldown`</sub>

## 9. Shard Mill: grinds the Horizons Balanced Shard

Check id: `phase_8.shard_mill_balanced`

**Steps**

1. You have the Greatwood and Silverwood Shard Mills and eight Balanced Shards. Hold the Greatwood mill and cycle its selection until the Balanced shard appears. Load a Balanced Shard and mill it; also try the Silverwood mill.
2. Watch the powder and the cycling through all seven kinds.

**Expect**

- [ ] Only the Greatwood mill offers and takes the Balanced shard; the Silverwood does not. Loading consumes the shard.
- [ ] The powder is a pale aura-coloured dust and does nothing else (as in the original).
- [ ] Judge this call: the cycling order and the colour.

<sub>Already covered by automated pack tests: `shard_mill_balanced`</sub>

## 10. Aura Core: infused with four Balanced Shards

Check id: `phase_8.aura_core_balanced`

**Steps**

1. An infusion altar stands seven blocks ahead with the Primal Charm in the centre and four Balanced Shards and eight thaumium ingots on its ring pedestals; creative jars of every aspect stand behind it to supply the essentia (the infusion recipe costs auram, praecantatio, alienis and vacuos). Open the Aura Core research and check its infusion page, then run the infusion.
2. Then swap the shards for essentia crystals (a few are in your hotbar) and try again.

**Expect**

- [ ] The recipe asks for four Balanced Shards; essentia crystals no longer work.
- [ ] The research text already mentions balanced shards.
- [ ] Judge this call: the recipe page shows the shards clearly.

<sub>Already covered by automated pack tests: `aura_core_recipes`</sub>

## 11. Wisp essence recipes

Check id: `phase_8.wisp_recipes`

**Steps**

1. The four entries are researched and you hold a Thaumonomicon and some wisp essences. With Thaumic Horizons installed open the research pages of the Taint Animation, Ethereal Manipulator and Ring of Blustering Light foci and of the Thaumdrum, and infuse one of them.

**Expect**

- [ ] Each page shows the recipe with wisp essences of the listed aspects (not essentia crystals); the infusion accepts them. Without Horizons the pages show the crystal recipe instead.

<sub>Already covered by automated pack tests: `other_mods_use_wisp_essence_when_horizons_is_loaded`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_8`).
