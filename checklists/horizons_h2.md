# QA: Horizons H2: souls and golems

Chapter id `horizons_h2`, 9 checks. In game this is the FTB Quests chapter **QA: Horizons H2: souls and golems**; each check there has a green "Set up this check" line that builds its test site.

## 1. Soul Sieve feeds the Inspiratron and Soulforge

Check id: `horizons_h2.sieve_chain`

**Steps**

1. Two Soul Sieves stand in front of you: one under an Inspiratron, one under a Soulforge. Soul sand and paper are on your hotbar.
2. Feed soul sand into each sieve; give the Inspiratron paper.

**Expect**

- [ ] Sand is used only when something above receives the soul; the Inspiratron writes Knowledge Fragments; the machines look like the original models and animate.

<sub>Already covered by automated pack tests: `sieve_feeds_the_soulforge`, `sieve_drops_sand_a_full_chest_refuses`, `inspiratron_writes_fragments`</sub>

## 2. Knowledge Fragment

Check id: `horizons_h2.fragment`

**Steps**

1. Knowledge Fragments are on your hotbar.
2. Use one.

**Expect**

- [ ] 1-2 of each primal aspect is added to your aspect pool; the message reads well.

<sub>Already covered by automated pack tests: `fragment_grants_every_primal`</sub>

## 3. Lost Soul and soul jars

Check id: `horizons_h2.lost_soul`

**Steps**

1. A Lost Soul hovers six blocks ahead; the wand, Containment focus and empty soul jars are on your hotbar.
2. Catch it with the Containment focus and an empty soul jar.

**Expect**

- [ ] The Lost Soul's sprite animates; the catch gives a soul jar with a soul wisp drawn inside.

<sub>Already covered by automated pack tests: `lost_soul_capture_gives_a_soul_jar`, `soul_jar_keeps_its_soul`</sub>

## 4. Soul Beacon reincarnation into the Vat

Check id: `horizons_h2.beacon`

**Steps**

1. A raw vat stands in front of you; the wand and a Soul Beacon are on your hotbar.
2. Wand-click the vat to form it, put the Soul Beacon on it and bind it; die (e.g. /kill).

**Expect**

- [ ] Instead of dying you wake inside the vat with health restored; the binding is used up (re-bind to use again).

<sub>Already covered by automated pack tests: `beacon_cancels_a_death`, `death_event_reincarnates`, `beacon_reincarnates_into_the_vat`</sub>

## 5. Mirrored Amulet

Check id: `horizons_h2.amulet`

**Steps**

1. A mirror stands ahead; the hand mirror is on your hotbar and you are already wearing the Mirrored Amulet in the Curios necklace slot.
2. Link the hand mirror to a mirror elsewhere (use the one ahead, or place another far away), then die with a full inventory.

**Expect**

- [ ] Your items arrive at the linked mirror (it ejects them over a few moments).

<sub>Already covered by automated pack tests: `amulet_sends_everything_through_the_mirror`</sub>

## 6. Corpse Effigy revival and standby

Check id: `horizons_h2.effigy`

**Steps**

1. A raw vat stands in front of you; the wand, Corpse Effigies and soul jars are on your hotbar.
2. Wand-click the vat to form it, put a Corpse Effigy in the sample slot; pipe 16 Victus (bring a jar and tubes).
3. Then load a soul jar into the standby vat.

**Expect**

- [ ] The effigy body revives in the vat (pose and scale look right) and the vat stands by; a villager of the soul's profession appears and the jar comes back empty.

<sub>Already covered by automated pack tests: `effigy_revival`, `effigy_revival_waits_and_aborts`, `standby_enters_and_leaves`</sub>

## 7. Animation Powder golems

Check id: `horizons_h2.powder`

**Steps**

1. Five blocks stand in a row ahead: stone, iron block, cactus (on sand), cobweb and TNT. Animation Powder is on your hotbar.
2. Use Animation Powder on each, one at a time; watch each golem for 60 s.

**Expect**

- [ ] Each golem wears its block's textures, follows you and fights; cactus thorns, web slows; when time runs out the block is put back; the TNT golem explodes.
- [ ] Feel: speed, size, animation; the powder is used up.

<sub>Already covered by automated pack tests: `powder_animates_a_block_and_is_consumed`, `stats_follow_the_type_table`, `timer_expiry_returns_the_block`, `tnt_and_detonation_golems_explode`, `cactus_thorns_and_web_slowness`</sub>

## 8. A seal makes a powder golem permanent

Check id: `horizons_h2.seal_binding`

**Steps**

1. A stone block stands ahead; Animation Powder and two Guard seals are on your hotbar.
2. Animate the stone, use a seal item on the temporary golem; place a matching seal in the world.
3. Sneak-click it as its owner.

**Expect**

- [ ] It stays, works the seal's task like a Thaumaturge golem, keeps its block skin; picking it up gives an Animated Golem item that places it back.

<sub>Already covered by automated pack tests: `seal_binding_makes_the_golem_permanent`, `pickup_item_round_trips`</sub>

## 9. Animation focus

Check id: `horizons_h2.animation_focus`

**Steps**

1. A Focal Manipulator stands beside you and a row of blocks (stone, iron, planks, glass) ahead; the wand is on your hotbar.
2. Craft the Animation focus (research Animation focus), cast it on the blocks with Extend, Berserk and Detonation settings.

**Expect**

- [ ] Vis cost depends on the material; Extend lengthens life; Berserk attacks everything but you; Detonation explodes at the end.

<sub>Already covered by automated pack tests: `focus_charges_by_material`, `berserk_golem_attacks_everything_but_the_owner`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h2`).
