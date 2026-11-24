# QA: Horizons H6: Balanced Shard and vis machines

Chapter id `horizons_h6`, 6 checks. In game this is the FTB Quests chapter **QA: Horizons H6: Balanced Shard and vis machines**; each check there has a green "Set up this check" line that builds its test site.

## 1. Balanced Shard and Shard Transmutation

Check id: `horizons_h6.balanced_shard`

**Steps**

1. You stand in front of a crucible over a magma block (so it is already hot) with a crafting table beside it. Your hotbar holds one essentia crystal of each primal (three of air) and one of Permutatio, plus a water bucket.
2. Craft a Balanced Shard from one crystal of each of the six primals (any order). Fill the crucible with the water bucket, then drop the shard, two more air crystals and the Permutatio crystal into it.

**Expect**

- [ ] The shard crafts; the crucible gives a crystal of the chosen primal and uses the shard up; the shard icon looks like six colours of one crystal.

<sub>Already covered by automated pack tests: `balanced_shard_is_shapeless_from_six_primal_crystals_and_tagged`, `shard_transmutation_outputs_the_right_crystal`, `stand_ins_are_replaced_by_the_balanced_shard`</sub>

## 2. Vis Dynamo

Check id: `horizons_h6.vis_dynamo`

**Steps**

1. You stand in front of a Vis Dynamo with a Vis Relay four blocks to its side, and hold a full unfocused wand.
2. Hold right mouse on the dynamo with the wand, then right-click it empty-handed and switch some primals off.

**Expect**

- [ ] The ring rises and spins while held and the relay beam links; the menu has six aspect tags that grey when off; an off primal is not drawn from the wand; a focused wand casts instead (documented limit).

<sub>Already covered by automated pack tests: `vis_dynamo_hold_costs_and_output`, `vis_dynamo_hold_event_needs_an_aimed_unfocused_wand`</sub>

## 3. Essentia Dynamo

Check id: `horizons_h6.essentia_dynamo`

**Steps**

1. You stand in front of an Essentia Dynamo two blocks up, with a tube under it running down to a jar of fire essentia, and a Vis Relay beside it.
2. Watch the dynamo (a consumer on the relay is up to you): one unit should run it for about a second, the ring spinning while it burns.

**Expect**

- [ ] One unit runs it for about a second at 12 cV per tick split over the primals; the ring spins while it burns; it takes the next unit only in the last second.

<sub>Already covered by automated pack tests: `essentia_dynamo_numbers`</sub>

## 4. Node Monitor

Check id: `horizons_h6.node_monitor`

**Steps**

1. You stand in front of a small node with a Node Monitor on its east face and a redstone lamp beside the monitor. Your hotbar holds a full wand and one spare monitor.
2. Try the spare monitor on a block with no node (it should refuse). Drain one aspect with the wand to 1 point, then to 0, and watch the monitor and lamp.

**Expect**

- [ ] The monitor refuses a block with no node; at 1 point (or 0) its screen flips amber and the lamp lights within a second; it goes out when the aspect recovers.

<sub>Already covered by automated pack tests: `node_monitor_signals_at_one_point_or_nothing`</sub>

## 5. Ethereal Shard

Check id: `horizons_h6.ethereal_shard`

**Steps**

1. You stand before a Vis Dynamo, a Vis Relay and an Ethereal Shard in a row, three blocks apart. Your hotbar holds a full wand and eight air crystals.
2. Right-click the shard with the crystals, hold the wand on the dynamo to feed the relay, wait, then tap the shard with the wand; finally break it.

**Expect**

- [ ] Capacity rises by 4 per crystal and the stack is used up; it fills 1 point per 100 cV drawn; the wand taps it like a node; breaking it drops the shard and capacity / 4 crystals per aspect.

<sub>Already covered by automated pack tests: `ethereal_shard_capacity_tapping_and_drops`, `ethereal_shard_fills_from_a_relay`</sub>

## 6. Horizons potions in the Seroconverter

Check id: `horizons_h6.potions`

**Steps**

1. You stand in front of a Seroconverter with four jars touching it: Auram, Desiderium, Potentia and Herba. Your hotbar holds four syringes.
2. Put a syringe in, select Auram (Vis Generation), Desiderium (Item Vacuum), Potentia (Static Shock) or Herba (Photosynthesis), make an injection and use it. Repeat for the others.

**Expect**

- [ ] The aspects are in the palette; Vis Generation drops primal orbs, Item Vacuum pulls items in, Static Shock zaps neighbours, Photosynthesis heals and feeds in daylight; the status icons are readable.

<sub>Already covered by automated pack tests: `potions_do_what_the_original_did`, `photosynthesis_heals_only_in_daylight`, `serconverter_has_the_vis_potions_back`, `deferred_only_aspects_are_hidden`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h6`).
