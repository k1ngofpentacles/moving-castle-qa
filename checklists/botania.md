# QA: Botania wand parts

Chapter id `botania`, 4 checks. In game this is the FTB Quests chapter **QA: Botania wand parts**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `forbiddenmagic:livingwood_inert_rod`, `forbiddenmagic:dreamwood_inert_rod`, `forbiddenmagic:manasteel_inert_cap`, `forbiddenmagic:elementium_inert_cap`, `botania:mana_tablet`, `botania:mana_pool`, `botania:livingwood_log`

## 1. Mana pool wakes the rods and caps

Check id: `botania.pool`

**Steps**

1. You stand in front of a full creative mana pool. Toss the dormant livingwood rod and the inert manasteel cap (both on your hotbar) into it.

**Expect**

- [ ] They become the Livingwood Rod (10,000 mana) and the Manasteel Cap (1,000).

<sub>Already covered by automated pack tests: `botania_wand_parts`</sub>

## 2. Assemble a livingwood wand

Check id: `botania.assemble`

**Steps**

1. You stand in front of an Arcane Workbench with an awakened livingwood rod and two manasteel caps on your hotbar. Put the rod in the middle and a cap on each diagonal.

**Expect**

- [ ] A 'Manasteel Entwined Livingwood' wand (a readable name, not a raw key).

<sub>Already covered by automated pack tests: `botania_wand_parts`</sub>

## 3. Mana refills the wand

Check id: `botania.refill`

**Steps**

1. You stand beside an Arcane Workbench (assemble the wand there from the rod and two caps) and a full creative mana pool. Toss the mana tablet into the pool to fill it, then keep the wand on the hotbar with the tablet in your inventory.
2. Empty the wand a little by casting, then watch it refill.

**Expect**

- [ ] Every two seconds each primal gains a vis; the tablet loses 6 mana per hundredth of a vis.

<sub>Already covered by automated pack tests: `botania_mana_refill`</sub>

## 4. Node boost is 3x

Check id: `botania.node_boost`

**Steps**

1. You stand in front of two Endoflame flowers: one beside a jar holding an aura node, one 8 blocks away from it. Throw the coal on the ground by each flower (8 pieces each) and compare how fast they burn it and fill (Botania wand on the hotbar shows their mana).

**Expect**

- [ ] The one by the node works about 3x as fast, not 20x.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `botania`).
