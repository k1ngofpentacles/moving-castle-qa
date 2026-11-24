# QA: Phase 8-4: Protobody, Protolimbs, Solid Void

Chapter id `phase_8_4`, 5 checks. In game this is the FTB Quests chapter **QA: Phase 8-4: Protobody, Protolimbs, Solid Void**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumicconcilium:protobody`, `thaumaturge:wand`

## 1. Protobody: how it looks in the hand, on the ground and in the hotbar

Check id: `phase_8_4.protobody_look`

**Steps**

1. You have a Protobody and a Solid Void block in the hotbar.
2. Look at it in your hand (first person), then press F5 to see it in third person, drop it (Q) and look at it on the ground, then pick it up again.

**Expect**

- [ ] A small upright figure of the end portal's starfield (a vanilla humanoid shape), not a flat icon, in every view including the hotbar slot.
- [ ] On the ground it lies as a normal item entity and can be picked up after about two seconds.
- [ ] Judge this call: size and angle in hand, whether the figure reads as a body.

<sub>Already covered by automated pack tests: `protobody_drop_becomes_custom_entity`</sub>

## 2. Protobody: the infusion and its polishment

Check id: `phase_8_4.protobody_infusion`

**Steps**

1. The kit has the ingredients: a Corpse Effigy, four Void Putty and four Wisp Essences (void, flesh, aura, man). Build an infusion altar with four pedestals; the effigy goes in the middle.
2. Put the putty and essences on the pedestals, alternating (putty, void, putty, flesh, putty, aura, putty, man) and run the infusion (Thaumaturge's scribbling table or the research book shows the recipe once PROTOBODY is known).
3. Without a polished draw of 64 victus from a Destabilized Crystal with the Vis Conductor, the result must be lost; with it you get a Protobody.

**Expect**

- [ ] The recipe page appears under the Protobody research, instability low (4), essentia humanus 128, vacuos 256, alienis 64, auram 128.
- [ ] The unpolished infusion fails with the polishment message; the polished one gives the Protobody.
- [ ] Judge this call: the book text reads well and the recipe is findable.

<sub>Already covered by automated pack tests: `protobody_recipe_and_polishment_load`, `infusion_recipes_match`</sub>

## 3. Protobody: dropped into the void it breaks into six Protolimbs

Check id: `phase_8_4.protobody_void_shatter`

**Steps**

1. Press L (or /thaumicconcilium qa ethereal on) to become ethereal, then sneak straight down through the pad until you are well below the world floor (below y -80 in the overworld).
2. Hold the Protobody in your hand and drop it (Q) there; the void does not hurt an ethereal player.
3. Also drop a second Protobody above the floor (on the pad) and wait a few seconds.

**Expect**

- [ ] Below y -80 the item breaks into six small spinning pieces (head, two arms, body, two legs) that fly outward and then drift about.
- [ ] The one dropped above the floor stays an ordinary item and is not harmed.
- [ ] Judge this call: the burst reads as a body breaking apart, and the pieces are visible against the void.

<sub>Already covered by automated pack tests: `protobody_item_shatters_only_below_the_void_line`</sub>

## 4. Protolimbs: drift, shy away, are absorbed, six give Solid Void

Check id: `phase_8_4.protolimbs_absorb`

**Steps**

1. Down in the void (ethereal, below y -80) with the six limbs around you: watch them for a few seconds, then walk toward one.
2. Let each limb touch you (they shy away, so corner them or stand still). Count the sounds. On the sixth, listen for a heartbeat and look in the research book.
3. While ethereal with fewer than six absorbed, do something non-wand (break a block): your max health drops by one each time. With six absorbed it stops dropping.
4. Die or log out and in (respawn): the absorbed count resets.

**Expect**

- [ ] The limbs drift slowly in random directions and move away when you come within about four blocks.
- [ ] A touch plays a craft-fail sound and removes the limb; the sixth also plays a heartbeat and unlocks the Solid Void research entry (round, under the Protobody).
- [ ] Absorbing a seventh or a second set does not unlock it again or repeat the heartbeat.
- [ ] With six held the flesh (health held back) no longer grows; after respawn it does again.
- [ ] Judge this call: the flee distance and speed feel right; the particles on touch are fine.

<sub>Already covered by automated pack tests: `protolimb_touch_counts_and_grants_solid_void_once`, `protolimb_drifts_and_keeps_away_from_a_player`, `peaceful_does_not_remove_a_protolimb`, `protolimb_is_banned_from_creature_infusion_and_not_hostile`</sub>

## 5. Solid Void: gather it with a wand in the void

Check id: `phase_8_4.solid_void_wand`

**Steps**

1. The kit has already set your absorbed count to six (/thaumicconcilium qa protolimbs 6). Go below the world floor (y -80 or lower; the trick works from just under y -64) holding a wand, and right-click in the air.
2. Try it with an empty hand, with a stick, and above the floor: nothing should happen.
3. Place the block down, look at it by day and by night, then break it with your hand.

**Expect**

- [ ] A Solid Void block appears in your inventory with a pop sound (dropped at your feet if the inventory is full), once per click.
- [ ] The block shows the end portal's starfield on every exposed face, the same by day and by night; faces against another block are not drawn.
- [ ] It breaks at once by hand and drops itself; explosions do not break it.
- [ ] Judge this call: the look in daylight and in the dark, in the hand and as a placed wall.

<sub>Already covered by automated pack tests: `wand_trick_needs_depth_and_six_limbs`, `solid_void_block_numbers_and_drop`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_8_4`).
