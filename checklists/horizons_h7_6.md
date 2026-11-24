# QA: Horizons H7-6: the Teleological Recombinator

Chapter id `horizons_h7_6`, 4 checks. In game this is the FTB Quests chapter **QA: Horizons H7-6: the Teleological Recombinator**; each check there has a green "Set up this check" line that builds its test site.

## 1. The Recombinator: look, pearl and sparks

Check id: `horizons_h7_6.recombinator_look`

**Steps**

1. You stand in front of a small node with a Teleological Recombinator directly above it and a redstone block in your hotbar.
2. Look at it from the side and from three-quarters, then the item in your hand. Put the redstone block beside the recombinator and watch the pearl and the space under it for about five seconds. Take the block away again.

**Expect**

- [ ] Idle: a metal plate on top with four claws hanging under it holding a dark pearl, a small cap under the pearl; the item icon matches. Powered: the pearl starts to bob, gently at first and then by about two pixels, and after about two and a half seconds small blue sparks play round it and drift down toward the node. Unpowered: the bobbing and sparks fade out within about two and a half seconds and then everything is still.

<sub>Already covered by automated pack tests: `recombinator_warms_up_then_attempts_at_the_interval`</sub>

## 2. Fusing aspects at about one a second

Check id: `horizons_h7_6.recombinator_merge`

**Steps**

1. You stand in front of a node holding Ordo and Perditio, with a Recombinator above it, and a second node a few blocks to the side and slightly lower holding only Ignis. Your hotbar has a wand and a redstone block.
2. Scan the first node with the wand (or the thaumometer), then put the redstone block next to the Recombinator and wait about half a minute, scanning both nodes now and then. Remove the block when you are done.

**Expect**

- [ ] After a warm-up of about two and a half seconds, white-blue bolts jump from the second node to the first now and then (not every second, since it looks at a random nearby block); each bolt turns one Ordo into Potentia or one Perditio into Gelum in the first node and takes one Ignis out of the second; the first node's list gains compounds while the second node's Ignis falls. When the redstone is removed it stops.

<sub>Already covered by automated pack tests: `recombinator_merges_and_respects_the_lock`, `recombinator_merge_arithmetic`, `recombinator_candidate_passes_prefer_primals`</sub>

## 3. A locked node is left alone

Check id: `horizons_h7_6.recombinator_locked`

**Steps**

1. You stand in front of a node holding only Ordo, with a Recombinator above it, and a second node holding Ignis a few blocks to the side that sits on a Node Stabilizer.
2. Power the Recombinator with the redstone block and wait about twenty seconds; scan both nodes. Then put a lever on the stabilizer's neighbour block, or a redstone block beside the stabilizer, and wait again.

**Expect**

- [ ] While the stabilizer is unpowered the second node is never drained and no bolts jump to the first (the first node stays Ordo only); once the stabilizer has a redstone signal the node is no longer locked and the fusing into Potentia starts.

<sub>Already covered by automated pack tests: `recombinator_merges_and_respects_the_lock`, `recombinator_idle_cases_do_nothing`</sub>

## 4. The research and its recipe

Check id: `horizons_h7_6.recombinator_research`

**Steps**

1. You have read Planar Theory and the primordial pearl research. Open the Thaumonomicon, Horizons tab, to the right of Planar Theory.
2. Find Teleological Recombinator, read it to the end, and make it on an infusion altar with the pearl in the middle and the ring Vis Filter, Planar Conduit, Vis Filter, Node Transducer, Vis Filter, Planar Conduit, Vis Filter, Node Stabilizer.

**Expect**

- [ ] The entry sits between Planar Theory and Planar Rift, is hidden until you have the research behind it, has three pages (the third has no picture in this port), shows the infusion recipe, and the infusion consumes the whole pearl and gives one Teleological Recombinator.

<sub>Already covered by automated pack tests: `recombinator_research_and_recipe_parse`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_6`).
