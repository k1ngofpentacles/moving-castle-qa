# QA: Powders and the Burdening Amulet

Chapter id `phase3_restorations`, 10 checks. In game this is the FTB Quests chapter **QA: Powders and the Burdening Amulet**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumicconcilium:silverwood_shard_mill`, `thaumicconcilium:shard_mill`, `forbiddenmagic:pride_shard`, `forbiddenmagic:greed_shard`, `forbiddenmagic:wrath_shard`, `thaumicconcilium:burdening_amulet`, `minecraft:carved_pumpkin`, `minecraft:bone`, `minecraft:wolf_spawn_egg`, `minecraft:zombie_spawn_egg`, `thaumicconcilium:runic_body_windings`, `thaumicconcilium:runic_legs_windings`, `thaumicconcilium:dump_jackboots`, `thaumicconcilium:elemental_surfer_shorts`, `thaumicconcilium:tight_belt`, `thaumicconcilium:bottle_of_clear_water`, `thaumicconcilium:bottle_of_thick_taint`, `minecraft:stone`

## 1. Powders act when they settle

Check id: `phase3_restorations.settle`

**Steps**

1. You stand in front of a zombie 5 blocks away, with the Silverwood mill and wrath shards in your hotbar. Load the shards into the mill and grind at the zombie.

**Expect**

- [ ] The dust drifts and settles for about two seconds, then the zombie bursts into flame (nothing on contact mid-air).
- [ ] You are never affected by your own powder.

## 2. Pride flings towards the world origin

Check id: `phase3_restorations.pride`

**Steps**

1. You stand in front of a zombie 5 blocks away, with the Silverwood mill and pride shards in your hotbar. Note your coordinates (F3), then grind pride shards at the zombie.

**Expect**

- [ ] The zombie is flung towards x 0, z 0, 'the centre of the world', not simply away from the dust.

## 3. Greed pulls in

Check id: `phase3_restorations.greed`

**Steps**

1. You stand with the Silverwood mill and greed shards in your hotbar; a zombie waits 6 blocks ahead and a little to the side. Grind greed shards near it.

**Expect**

- [ ] The zombie is dragged onto the spot where the dust settled.

## 4. Burdening Amulet + pumpkin veil

Check id: `phase3_restorations.veil`

**Steps**

1. You stand beside an untamed wolf (2 blocks ahead, to the right) with bones, the Burdening Amulet, a carved pumpkin and a bracelet with the Reflection focus in your hotbar. Feed the wolf bones until it is tame.
2. Gain temporary warp (cast Reflection from the bracelet). Wear the Burdening Amulet without the pumpkin and look at the wolf.
3. Put on the carved pumpkin and look at the zombie behind it.

**Expect**

- [ ] Without the veil: Death Gaze withers whatever you look at, your wolf included, and turns it on you.
- [ ] With the pumpkin on: no Death Gaze; the wolf attacks what you look at; your warp still drains.

## 5. Art: mills, armour layers, icons

Check id: `phase3_restorations.art`

**Steps**

1. You hold both Shard Mills and the armour pieces in your hotbar. Look at both mills in hand, in the GUI and dropped on the ground; wear the windings, jackboots and shorts and look at the armour layers; look through the item icons.

**Expect**

- [ ] Models sit right in hand (positions are first guesses: describe or screenshot what is off), armour layers fit, no missing textures.

## 6. Shard Mill cranking

Check id: `phase3_restorations.mill_crank`

**Steps**

1. You hold the Greatwood mill with shards in your hotbar, a zombie 6 blocks ahead as a target. Load shards (the original used essentia crystals; any shard loads the mill); crank it in first person, in third person (F5) and as seen by another player.

**Expect**

- [ ] It tips toward you while loading; while grinding it is held bottom-forward with the crank spinning and the other hand working it; dust trails behind the motes.

## 7. Runic Windings and the strong numbers

Check id: `phase3_restorations.windings`

**Steps**

1. You stand beside an arcane workbench (ahead, to the right) with both windings, the Silverwood mill and wrath, pride and greed shards in your hotbar. Wear one and then both windings and watch the runic shield; craft at the workbench with them worn.
2. Judge the original numbers kept: windings 200 charge each, entropy powder Wither 51, wrath powder's 50,000-second burn, pride and greed powders' speed of 3.

**Expect**

- [ ] The shield grows with both pieces and refills faster; the workbench vis discount applies. The strong numbers feel acceptable (report any that don't).

## 8. Tight Belt

Check id: `phase3_restorations.belt`

**Steps**

1. You hold the Tight Belt and a bracelet with the Reflection focus. Cast Reflection a few times to gain temporary warp, then wear the belt.

**Expect**

- [ ] Warp turns into Thaumarhia by total warp, drains about 1 in 25 per tick, and the belt leaks flux gas.

## 9. Bottles thrown

Check id: `phase3_restorations.bottles`

**Steps**

1. You stand in front of a fire (ahead), a burning zombie (left), a blaze (right) and a stone block (8 blocks ahead), with Clear Water and Thick Taint bottles in your hotbar. Throw the Clear Water on the fire, the burning zombie and the blaze; throw the Thick Taint on the stone.

**Expect**

- [ ] Fire goes out, the blaze is scalded; the taint splashes Flux Taint, fibres and flux gas, with splash particles.

## 10. Dump Jackboots

Check id: `phase3_restorations.jackboots`

**Steps**

1. You are already wearing the Dump Jackboots with stone in your hotbar. Hold the stone, sneak to climb; release sneak mid-climb; repeat on a LAN client.

**Expect**

- [ ] You rise steadily laying a block beneath you; releasing sneak never leaves a gap; same on the client.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase3_restorations`).
