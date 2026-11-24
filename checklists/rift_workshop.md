# QA: The rift workshop

Chapter id `rift_workshop`, 8 checks. In game this is the FTB Quests chapter **QA: The rift workshop**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumaturge:thaumometer`, `minecraft:stick`

## 1. Breaking a node tears a rift

Check id: `rift_workshop.node_rift`

**Steps**

1. An aura node floats two blocks up, four blocks ahead of you; the thaumometer is in your hotbar. Break the node. Stand back and watch for a minute; then scan the rift.

**Expect**

- [ ] A rift opens where the node was (sized by the node's vis, up to 80) and grows slowly.
- [ ] Every 15 seconds or so it may lash out: magic arcs at whatever is near, primal orbs, charged wisps, a swarm of mind spiders, or it feeds on your warp and grows.
- [ ] Scanning it (or any flux rift) reveals the Rifts research. When it closes it leaves taint fibres, flux gas and goo around.

<sub>Already covered by automated pack tests: `spatial_rift`</sub>

## 2. Charging a destabilized crystal

Check id: `rift_workshop.crystal`

**Steps**

1. A Vis Condenser stands ahead on the right and a stone wall on the left; you have three crystals and essentia crystals of aer and ignis. Place a crystal on the ground, on the wall and on the condenser. Right-click them with essentia crystals.

**Expect**

- [ ] It grows out of the face you placed it on and takes the colour of the first aspect you feed it; more of that aspect charges it, others are refused.
- [ ] Breaking it gives nothing back (as the original).

<sub>Already covered by automated pack tests: `condenser_and_crystal`</sub>

## 3. Vis Conductor

Check id: `rift_workshop.conductor`

**Steps**

1. Charged crystals stand ahead (two aer on the left and right, one auram further right), a cow stands still further on, and a small rift hangs beyond it. Your wand has the Vis Conductor; the Dematerialization focus is in your hotbar.
2. Channel (hold right-click) at a charged crystal, then let go looking at empty sky.
3. Recharge another crystal (essentia crystals are in your hotbar); with the Dematerialization focus socketed, channel and let go at the cow; then with the auram crystal, at the rift.

**Expect**

- [ ] Arcs in the crystal's colour run from it to you while it drains.
- [ ] Let go at nothing: the crystal bursts in a small explosion.
- [ ] With Dematerialization: the mob takes damage for what you drained; an auram charge shrinks the rift, and draining enough closes it quietly.

## 4. Wisp Launcher

Check id: `rift_workshop.wisp_launcher`

**Steps**

1. Your wand has the Vis Conductor already set to the Wisp Launcher upgrade; a wisp hovers ahead and two cows stand still further on. Channel at the wisp until it reaches you, then let go towards the cows.

**Expect**

- [ ] The wisp is reeled in, then flung where you look as a charged wisp that hurts everything within 4 blocks of its path and leaves them vis-exhausted.

## 5. Vis Condenser discharge

Check id: `rift_workshop.condenser`

**Steps**

1. A Vis Condenser with a charged aer crystal on it stands ahead, a lever beside it on the right and a still pig four blocks to its left. Flip the lever (redstone strength 15; a redstone block is in your hotbar for other strengths).

**Expect**

- [ ] A bolt in the crystal's colour shoots out of the opposite side as far as the signal is strong, hitting harder the shorter it is; up to 16 charge is spent.

## 6. The Hex and its chained rift

Check id: `rift_workshop.hex`

**Steps**

1. A formed Hex with its chained rift lies four blocks ahead (a jarred node on its centre), and a powered condenser with a charged crystal stands to the right within 8 blocks. Watch the rings turn.
2. Throw a stick onto the hex (sticks and void slag are in your hotbar).

**Expect**

- [ ] The ring becomes the Hex: a plate with three rune rings. The node unseals into a young rift above it; the rings start turning and the runes glow purple.
- [ ] The essentia goes into the hex; with the stick on it, arcs run to the stick and void slag spatters out for about 20 seconds. (No rift recipe exists until phase 6b, so nothing is made yet.)
- [ ] Void slag thrown near keeps it running; left long enough it overheats and the rift collapses. Breaking any hex block turns it back into stone and bedrock.

<sub>Already covered by automated pack tests: `hex_transmutation`</sub>

## 7. Taming a flux rift with a lesser hex

Check id: `rift_workshop.lesser_hex`

**Steps**

1. A flux rift hangs above a Barrier Stone ringed with eight ancient stone, three blocks ahead; your wand is full of vis. Strike the Barrier Stone with the wand (50 ordo, 50 terra).

**Expect**

- [ ] The rift above is calmed: it stops growing, shrinks to size 25 if larger, makes no flux events, and closes harmlessly. It transmutes too, for twice the essentia.

<sub>Already covered by automated pack tests: `lesser_hex`</sub>

## 8. Primal orb: summoned versus thrown

Check id: `rift_workshop.primal_orb`

**Steps**

1. A rift hangs nine blocks ahead; wait for it to throw orbs and watch them. Then run /summon thaumicconcilium:primal_orb ~ ~1 ~3 and watch.

**Expect**

- [ ] The summoned motionless orb bursts at once; orbs a rift throws fly and burst on impact. Neither looks wrong (the original's sound and particles are the reference).

<sub>Already covered by automated pack tests: `spatial_rift`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `rift_workshop`).
