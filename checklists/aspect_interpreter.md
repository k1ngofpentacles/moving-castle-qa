# QA: Aspect Interpreter

Chapter id `aspect_interpreter`, 1 checks. In game this is the FTB Quests chapter **QA: Aspect Interpreter**; each check there has a green "Set up this check" line that builds its test site.

## 1. Aspects for unassigned items and mobs

Check id: `aspect_interpreter.interpreted_aspects`

**Steps**

1. You hold the goggles, one item Thaumaturge has no aspects for (a Neo Vitae weak blood orb, Alex's Mobs elastic tendon, a Farmer's Delight tatami, raw bison, lobster pasta) and a few ordinary items with hand-written aspects (the kit's iron-and-food samples). Wear the goggles and read each one's aspects (inventory tooltip or JEI).
2. Scan or read a mob the pack gives no aspects (for example a bison or a centipede, with the goggles) and a mob that has hand-written aspects (a zombie or a cow).
3. Judge the guesses: believable for what each item or mob is, nothing in the hundreds, none stronger than the pack's own mobs of the same threat.
4. risk: You hold the goggles and three guessed items. Note their aspect amounts, quit the game, launch it again and stage this check again. The amounts must be the same after the relaunch.

**Expect**

- [ ] Every unassigned item and guessed mob shows aspects; most item totals are well under 100.
- [ ] The hand-written items and mobs show exactly the aspects in the pack's data: nothing added, nothing changed.
- [ ] The guesses read as sensible (victus and bestia for raw meat, aqua for fish, no metallum on food).
- [ ] The same amounts, after the relaunch.

<sub>Already covered by automated pack tests: `overlay_serves_ours_and_leaves_hand_written_alone`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `aspect_interpreter`).
