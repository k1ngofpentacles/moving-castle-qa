# QA: Thaumaturges and the fallen

Chapter id `thaumaturges`, 11 checks. In game this is the FTB Quests chapter **QA: Thaumaturges and the fallen**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:skeleton_skull`, `minecraft:diamond_sword`, `thaumaturge:thaumometer`

## 1. Before the research: taunts

Check id: `thaumaturges.taunt`

**Steps**

1. A Thaumaturge stands three blocks ahead and you have no Thaumaturge research yet. Right-click it.

**Expect**

- [ ] A purple chat line mocking you ('Why are you mooing? Can you even read?' or one of three others). No trade screen.

## 2. Trading at the Pech table

Check id: `thaumaturges.trade`

**Steps**

1. A Thaumaturge stands three blocks ahead and the research is done; bottles, an enchanted book, a skull, mana beans and dirt are in your hotbar. Right-click it.
2. Put a bottle o' enchanting in the left slot and click the dice. Take the goods out, then try the enchanted book, the skull, mana beans and dirt.

**Expect**

- [ ] Thaumcraft's Pech trade screen. The dice light up only for something the Thaumaturge values (not dirt) and only while the four payout slots are empty.
- [ ] Each click takes one offered item and lays out a few things: mana beans, essentia crystals, Curios of Knowledge, crystal clusters, more rarely a focus pouch, a fire focus, a vis amulet or a profane wand core.
- [ ] If you have a finished research note, offering it buys Scribbled Research Notes (Positive Burst or Impulse) and a purple remark.

<sub>Already covered by automated pack tests: `thaumaturge_trades`, `thaumaturge_menu`</sub>

## 3. Hit one, anger them all

Check id: `thaumaturges.anger`

**Steps**

1. Two Thaumaturges stand ahead, and you have a diamond sword in survival. Hit one with the sword.

**Expect**

- [ ] Both turn on you: angry-villager puffs, fire bolts from their wands at range, punches up close. The trade screen won't open while they're angry.
- [ ] After 20 to 40 seconds they calm down and trade again. They heal slowly meanwhile.

<sub>Already covered by automated pack tests: `thaumaturge_menu`</sub>

## 4. They fight the darkness

Check id: `thaumaturges.allies`

**Steps**

1. It is night: a Thaumaturge stands five blocks ahead with a zombie and a skeleton about eleven blocks beyond it. Watch what the Thaumaturge does (stay near it).

**Expect**

- [ ] It attacks them with its wand, unprovoked.

## 5. Hint notes gate their entries

Check id: `thaumaturges.hint_gate`

**Steps**

1. The prerequisites of Reflection, Positive Burst, Impulse, Thick Taint and Runic Windings are done, and you hold the Scribbled Research Notes for Reflection and a Thaumonomicon. Hover over the notes, then open the Thaumonomicon at the Reflection Focus entry and start it.
2. Do the same for Positive Burst, Impulse, Thick Taint or Runic Windings without their notes.

**Expect**

- [ ] Tooltip: 'Hm, the only things missing are a method of experience exchanging and a brain contact scheme...'
- [ ] Reflection asks for the notes and takes them when you begin it. The others can't be started without their own notes.

<sub>Already covered by automated pack tests: `hint_gates`</sub>

## 6. Mad Thaumaturges

Check id: `thaumaturges.mad`

**Steps**

1. You are in survival with a diamond sword; two Mad Thaumaturges stand nine blocks ahead. Let one reach you; hit it a few times. Kill both, and spawn a few more with /summon if you want more drops.

**Expect**

- [ ] Ragged skin, a void hoe or shovel. It hunts you (and Thaumaturges and cultists), sometimes leaps onto you and claws at you before falling off. Sad mutterings.
- [ ] Drops: usually a Curio of Knowledge or nothing; one in five a set of Scribbled Research Notes (Reflection, Thick Taint or Runic Windings).
- [ ] About one Brainy Zombie in five is replaced by one as it spawns. They spawn in any biome, the Nether and the End included.

## 7. Nether Explorers

Check id: `thaumaturges.explorer`

**Steps**

1. A lava pool lies four blocks ahead with two Nether Explorers drifting on it; you have a diamond sword (do not step into the lava).
2. Right-click one; hit the other.

**Expect**

- [ ] A thin body lies on its back and floats on lava (and water), drifting slowly.
- [ ] Right-click: a Nether Membrane in your inventory, a heartbeat, and the Nether Membrane research. Hit: the membrane pops out and survives the lava.

<sub>Already covered by automated pack tests: `nether_explorer`</sub>

## 8. Wrapping in Nether Membrane

Check id: `thaumaturges.membrane`

**Steps**

1. You have two Nether Membranes and a diamond sword, and a lava pool lies four blocks ahead. Craft the membrane with the sword (any grid). Throw the wrapped sword into the lava.

**Expect**

- [ ] One sword with a red 'Nether Protection' line. It floats on lava like netherite. A wrapped item can't be wrapped again.

<sub>Already covered by automated pack tests: `nether_membrane_recipe`</sub>

## 9. Withered Botanist (Botania)

Check id: `thaumaturges.botanist`

**Steps**

1. With Botania: a Withered Botanist lies on the grass three blocks ahead. Right-click it.

**Expect**

- [ ] Three or four Botania mystical flowers of random colours bloom around it, petals and coloured motes rise, the wind sighs, and the body is gone.

## 10. The Price of Scientific Advances

Check id: `thaumaturges.bestiary`

**Steps**

1. A Mad Thaumaturge, a Nether Explorer and a Withered Botanist stand still ahead (the botanist needs Botania), and you have a thaumometer; only the Concilium root is researched. Scan the Mad Thaumaturge and the Nether Explorer with the thaumometer, then open the Concilium tab in the Thaumonomicon.

**Expect**

- [ ] Scanning the Mad Thaumaturge reveals 'Mad Thaumaturges'; scanning the explorer reveals 'The Price of Scientific Advances', both left of the tab's root. Scanning a Withered Botanist adds its page.

## 11. Where Thaumaturges turn up

Check id: `thaumaturges.wanderers`

**Steps**

1. Staging does not move you: this check needs real terrain. Over a few in-game days, explore new (never-loaded) chunks with villages, desert and jungle temples, witch huts, igloos and ruined portals; also stay put near home.

**Expect**

- [ ] Now and then a structure (about one in several) has one to three Thaumaturges living at it when you first find it. They don't respawn there, and never appear in the open countryside.
- [ ] Now and then, one or two wander up to you wherever you are, and leave after a day or two.

<sub>Already covered by automated pack tests: `thaumaturge_haunts`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `thaumaturges`).
