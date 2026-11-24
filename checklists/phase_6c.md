# QA: The Brightest One and subspace (6c)

Chapter id `phase_6c`, 13 checks. In game this is the FTB Quests chapter **QA: The Brightest One and subspace (6c)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:white_bed`, `minecraft:shield`

## 1. Attuning an aura core

Check id: `phase_6c.core_attune`

**Steps**

1. You stand near a terra crystal cluster with a mix of blocks around it (stone, ore, water, a log, a flower, leaves, sand). A charged wand and a blank aura core are in your inventory.
2. Toss the blank aura core a block or two from the cluster.
3. Strike the cluster with the wand and watch and listen for about 25 seconds.

**Expect**

- [ ] The cluster is used up and a stream of dust runs from it to the core; the core cannot be picked up while it works.
- [ ] Three motes of colour then orbit the core in a shrinking ring, and a sound marks the end. A new coloured core drops, tuned to the cluster's primal and showing in its tooltip.
- [ ] On bare ground with nothing to scan the attuning does not finish; the core stays blank.

<sub>Already covered by automated pack tests: `aura_core_recipes`, `aura_core_attunes_earth`, `aura_core_fails_on_bare_ground`</sub>

## 2. Cleaning a core in the crucible

Check id: `phase_6c.core_clean`

**Steps**

1. You stand in front of a boiling crucible full of water, with an attuned (air) aura core in your inventory. The crucible holds no aspects: add the ones the cleaning recipe needs (see the Aura Core page in the book) first.
2. Drop the attuned core into the crucible.

**Expect**

- [ ] The core turns back into a blank aura core (one recipe per type), consuming the crucible's water as with any crucible recipe.
- [ ] The aura core's research page in the Thaumic Concilium tab shows the infusion recipe and the six cleaning recipes.

<sub>Already covered by automated pack tests: `aura_core_recipes`</sub>

## 3. Using the Gem of Rifts opens a rift

Check id: `phase_6c.gem_use`

**Steps**

1. You stand on open ground with the plain QA wand in slot 1 and the Gem of Rifts in slot 2.
2. Hold the Gem of Rifts and hold the use key (right-click) with no other rift within 16 blocks.
3. Keep holding to see the fast spin, then release. Try it again with the wand taken out of the hotbar.

**Expect**

- [ ] The gem spins up while held; after the first charge an interdimensional rift appears and the wand pays perditio 10 and aer 10. Without vis in the hotbar nothing opens.
- [ ] A second use within 16 blocks of the first rift does nothing. The rift grows from size 5 to 50 over a few seconds, shows lightning and teleports nothing by itself.
- [ ] Left alone, it collapses by shrinking and vanishes without taint, fibres or warp, and hurts nobody.

<sub>Already covered by automated pack tests: `gem_recipes`, `interdimensional_rift_life`</sub>

## 4. Crossing into the Causal Bouillon

Check id: `phase_6c.cross_in`

**Steps**

1. You stand on open ground with the plain QA wand, the Gem of Rifts and a white bed.
2. Note your x and z (F3). Open a rift with the gem and, holding the gem, step into it.
3. Look at the sky and fog, then look down. Try placing the white bed and sleeping, and walk about.

**Expect**

- [ ] You arrive in the Causal Bouillon at the same x and z, on the surface (y 4) of a flat Void Reality floor with air below it at y 0 (a safe landing, no suffocating).
- [ ] The sky is a fixed noon with no sun or moon and no weather, the fog and ambient ash read as a void, and the world has no day cycle.
- [ ] Beds cannot be used and set no spawn; the dimension is otherwise empty.

<sub>Already covered by automated pack tests: `bouillon_data`, `subspace_landing`, `subspace_crossing`</sub>

## 5. Leaving: inflate x10, deflate /10, cast dimension, Nether

Check id: `phase_6c.cross_out`

**Steps**

1. You stand on open ground with the plain QA wand, the Gem of Rifts, two Terra-cast Gems and a few netherrack, a crafting table to your right.
2. Open a rift and step in holding the gem (you arrive in the Bouillon), then walk to about x 100 z 100, open a rift with the gem and step in: you return to the overworld.
3. Repeat, but first shift + swing (left-click while sneaking) with the gem to flip it to deflates, then step out.
4. Craft a cast onto the Rift Gem with a Terra-cast Gem bound in the Nether (use the gem on a Nether block there), cycle casts with shift + use, select the Nether and step out again.

**Expect**

- [ ] Default (inflates space): you arrive at x and z times 10, on a safe surface (not inside rock) in the overworld.
- [ ] Deflates: you arrive at x and z divided by 10.
- [ ] With a Nether cast selected you arrive in the Nether in a safe air pocket below the roof, at the scaled x and z. The gem's tooltip shows the mode and the selected cast.

<sub>Already covered by automated pack tests: `subspace_maths`, `subspace_landing`, `subspace_crossing`</sub>

## 6. Terra gem absorbs a block

Check id: `phase_6c.terra_absorb`

**Steps**

1. You stand in front of a row of dirt, stone, sand, gravel and a chest, with the plain QA wand in slot 1 and the Terra-cast Gem in slot 2.
2. Hold the gem and use it on each block, including the chest (a block you may not edit, such as spawn protection, you must find yourself).
3. Hold the gem and check its tooltip.

**Expect**

- [ ] Each earthy block is removed with no drop; the gem becomes bound to the current dimension and costs terra 10 and aer 10 of vis.
- [ ] A chest (or any block with contents) is refused and not deleted; protected blocks are refused.

<sub>Already covered by automated pack tests: `terra_gem_absorbs`</sub>

## 7. Crafting adds a cast to the Rift Gem

Check id: `phase_6c.cast_craft`

**Steps**

1. You stand in front of a crafting table with the plain QA wand, the Gem of Rifts, two Terra-cast Gems and an inert one; a block of dirt is on your right.
2. Use a Terra-cast Gem on the dirt to bind it to this dimension (bind one in another dimension if you can reach one).
3. In the crafting grid, put the Gem of Rifts and the bound Terra-cast Gem.
4. Repeat with an empty terra gem and with a second gem after 16 casts.

**Expect**

- [ ] The result is the Rift Gem with the terra gem's dimension added as a cast; the terra gem is used up.
- [ ] An unbound (full or inert) terra gem matches nothing, and 16 casts is the limit.

<sub>Already covered by automated pack tests: `terra_gem_crafting`, `gem_recipes`</sub>

## 8. Held rendering, both hands and third person

Check id: `phase_6c.gem_held`

**Steps**

1. All four gems and an item frame are in your hotbar.
2. Hold each gem in the main hand, then in the off hand. Press F5 and look at them in third person, in sun and in shade; drop one and put one in an item frame.
3. Compare the Terra-cast Gem's glass in third person with the Gem of Rifts.

**Expect**

- [ ] In first person the active gems hover in the hand with a slow spin (fast while using) and the arm sways; the off hand is the mirror image, and the cast stone shows inside the Rift Gem when a cast is selected.
- [ ] Third person shows the gem held at the hand and lit like the rest of the body; dropped gems stand upright about half a block wide, the frame shows the pyramid.
- [ ] Known uncertainty: the Terra-cast Gem's glass reads orange-brown in third person where the original read green. Judge whether it is acceptable.

## 9. Summoning the Brightest One

Check id: `phase_6c.boss_summon`

**Steps**

1. You stand in front of a built chained rift (an ancient stone ring with a jar node above it), with two wisps hovering nearby and the QA wand (wisp launcher focus) in your hand. You have the Brightest One research.
2. Channel at a wisp to reel it in, then release near the rift so the charged wisp flies into the chained rift.
3. Repeat with a player who lacks the research if you can.

**Expect**

- [ ] The rift turns interdimensional and starts to collapse; at the end the Brightest One appears at size 0 and grows to full size.
- [ ] Without the research the charged wisp does nothing to the chained rift.

<sub>Already covered by automated pack tests: `brightest_chained_rift_summon`, `brightest_save_load`</sub>

## 10. Its four attack sets

Check id: `phase_6c.boss_attacks`

**Steps**

1. The Brightest One (ignis) hangs ten blocks ahead of you; you have the QA wand (wisp launcher), a shield and survival mode.
2. Fight it from range and from the shield. Each charged wisp that reaches it changes its aspect (ignis, aer, vacuos, tenebrae): watch the halo colour and its attacks in each state.

**Expect**

- [ ] Ignis: fire (embers) thrown at you. Aer: lightning and wind. Vacuos: pulls and crushes. Tenebrae: shadowbeams (hitscan) and darkness.
- [ ] Each attack set is readable, dodgeable and not overwhelming for the pack's level. The halo is a soft translucent disc, full colour at the centre, half at about a third of the way out, gone by about 0.6 of its size, in the aspect's colour.

<sub>Already covered by automated pack tests: `brightest_attacks_ignis`, `brightest_attacks_aer`, `brightest_attacks_vacuos`, `brightest_attacks_tenebrae`, `brightest_shadowbeam_and_ember`</sub>

## 11. Damage immunity and the short circuit

Check id: `phase_6c.boss_immune`

**Steps**

1. The Brightest One hangs ten blocks ahead of you; you have the QA wand (wisp launcher), a sword, a bow and survival mode.
2. Hit it with weapons, arrows and spells.
3. Launch charged wisps into it (channel the wisp launcher at wisps near you, it summons some, and let go aimed at the boss).

**Expect**

- [ ] Nothing hurts it: a hit only makes the attacker its target.
- [ ] Each charged wisp that reaches it short-circuits it: it changes aspect and loses 1 of 15 health; at 0 it dies (the sky returns to normal).

<sub>Already covered by automated pack tests: `brightest_ignores_damage`, `brightest_short_circuit_and_death`</sub>

## 12. Darkened sky and pink boss bar

Check id: `phase_6c.boss_atmosphere`

**Steps**

1. The Brightest One hangs still ten blocks ahead of you.
2. Look at the sky and the top of the screen; go far away (leave the pad through the glass if you wish); kill it.

**Expect**

- [ ] A pink boss bar with the sky darkened (as with the Wither or Ender Dragon) while it fights, returning to normal once it is gone or you are far away.

## 13. Drops, Primordial Life and peaceful despawn

Check id: `phase_6c.boss_drops`

**Steps**

1. A Brightest One at 1 health hangs ten blocks ahead of you (one charged wisp kills it) and a second still one hangs ten blocks behind; you have the QA wand (wisp launcher).
2. Kill the first with a short circuit and collect the drops, once. Then set difficulty to peaceful (/difficulty peaceful) with the second one alive.
3. Open the Primordial Life research in the Thaumic Concilium tab.

**Expect**

- [ ] Drops once: 2 essentia of its aspect and a Primordial Life; the research can then be completed (the item is now obtainable).
- [ ] On peaceful the Brightest One despawns.

<sub>Already covered by automated pack tests: `brightest_short_circuit_and_death`, `brightest_peaceful_despawn`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_6c`).
