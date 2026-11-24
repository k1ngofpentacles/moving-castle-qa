# QA: Aspect Interpreter 1.9.0: no runaway amounts

Chapter id `aspect_interpreter_1_9`, 5 checks. In game this is the FTB Quests chapter **QA: Aspect Interpreter 1.9.0: no runaway amounts**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `thaumaturge:goggles_revealing`

## 1. Two launches settle the index

Check id: `aspect_interpreter_1_9.two_launches`

**Steps**

1. Launch the pack, open a world, quit. Launch and open a world again.
2. In logs/latest.log, search for 'Aspect Interpreter'.

**Expect**

- [ ] First launch: 'learning from data maps only this launch'. Second launch: 'learned from ... items (N from Thaumaturge's index cache; name-based totals capped at 100)' with N in the thousands.
- [ ] Both launches log 'items derived from those are kept out of learning'.

## 2. Minor items carry small amounts

Check id: `aspect_interpreter_1_9.minor_items`

**Steps**

1. You hold the goggles and a sample of the inflated items: a Neo Vitae weak blood orb, Alex's Mobs elastic tendon, a Magic Bees skull fragment, Neo Vitae sulfur and a Farmer's Delight tatami. Wear the goggles and read each one's aspects (inventory tooltip or JEI).
2. Also look up Alex's Mobs dimensional carver shards in JEI (not given: no item id could be confirmed).

**Expect**

- [ ] None shows hundreds of any aspect; most total well under 100 (in 1.8.0 they reached 500 per aspect).

## 3. Raw meat is not metal

Check id: `aspect_interpreter_1_9.raw_meat`

**Steps**

1. You hold the goggles, raw bison, raw bunfungus and raw catfish. Wear the goggles and read each one's aspects.

**Expect**

- [ ] Victus and bestia (aqua for fish); no metallum, or only a trace.

## 4. Beach mobs are not alien

Check id: `aspect_interpreter_1_9.beach_mobs`

**Steps**

1. You hold the goggles, lobster pasta, a centipede leg and a cockroach wing fragment. Wear the goggles and read each one's aspects.

**Expect**

- [ ] No alienis or praemunio from Thaumaturge Tinker's Bedrock dimension (1.8.0 gave lobster pasta alienis 3).

## 5. Amounts stay put on a third launch

Check id: `aspect_interpreter_1_9.no_growth`

**Steps**

1. You hold the goggles and three guessed items. Note their aspect amounts, quit and relaunch the game, stage this check again and compare.

**Expect**

- [ ] The same amounts (1.8.0 grew a little every launch).

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `aspect_interpreter_1_9`).
