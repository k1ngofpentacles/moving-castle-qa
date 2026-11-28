# QA: Forbidden Magic

Chapter id `forbidden_magic`, 16 checks. In game this is the FTB Quests chapter **QA: Forbidden Magic**; each check there has a green "Set up this check" line that builds its test site.

## 1. The Apocrypha tab, its text and what stays hidden

Check id: `forbidden_magic.apocrypha`

**Steps**

1. Read its research entry ("Forbidden") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have the whole research book granted. Open it and the Apocrypha tab.
3. Next: You are in creative mode. Switch the game language to French, then open the Forbidden Magic creative tab and hover Crystal Scribing Tools.
4. Optionally repeat with Chinese (zh_CN) and Korean; then switch back to English.
5. risk: You are in creative mode. Open the Forbidden Magic creative tab and search the tab and JEI for: vinteum cap, witchwood rod, witchwood staff rod, equivalent rod, alchemical cap.
6. Then look up the alchemical cap in JEI by its recipe (gold cap with three arcane inscription tools).

**Expect**

- [ ] The tab opens, entries unlock in order, recipes show on their pages.
- [ ] The crystal scribing tools item reads in French, as do other translated names; untranslated names fall back to English with no raw keys shown.
- [ ] None of the five is listed in the creative tab.
- [ ] The four tagged ones (vinteum cap, both witchwood rods, equivalent rod) are absent from JEI; the alchemical cap is not in the tab but its recipe does show in JEI.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 2. Wand rods and caps: assembly and recharging

Check id: `forbidden_magic.wands`

**Steps**

1. Read its research entry ("Rod Infernal", "Rod Tainted", "Rod Livingwood", "Rod Dreamwood", "Cap Manasteel") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of an Arcane Workbench with the infernal and tainted rods and four gold caps. Assemble a wand of each; hold the tainted-rod wand on the taint soil strip ahead (the infernal one needs the Nether: go there yourself).
3. Next: You stand in front of an Arcane Workbench with an awakened livingwood rod and two manasteel caps on your hotbar. Put the rod in the middle and a cap on each diagonal.
4. Next: You stand in front of a full creative mana pool. Toss the dormant livingwood rod and the inert manasteel cap (both on your hotbar) into it.
5. Next: You stand beside an Arcane Workbench (assemble the wand there from the rod and two caps) and a full creative mana pool. Toss the mana tablet into the pool to fill it, then keep the wand on the hotbar with the tablet in your inventory.
6. Empty the wand a little by casting, then watch it refill.
7. Next: You stand in front of two Endoflame flowers: one beside a jar holding an aura node, one 8 blocks away from it. Throw the coal on the ground by each flower (8 pieces each) and compare how fast they burn it and fill (Botania wand on the hotbar shows their mana).

**Expect**

- [ ] Assembly works; the infernal rod recharges in the Nether, the tainted rod in taint.
- [ ] A 'Manasteel Entwined Livingwood' wand (a readable name, not a raw key).
- [ ] They become the Livingwood Rod (10,000 mana) and the Manasteel Cap (1,000).
- [ ] Every two seconds each primal gains a vis; the tablet loses 6 mana per hundredth of a vis.
- [ ] The one by the node works about 3x as fast, not 20x.

<sub>Already covered by automated pack tests: `botania_wand_parts`, `botania_mana_refill`</sub>

## 3. Blink Focus

Check id: `forbidden_magic.blink`

**Steps**

1. Read its research entry ("Focusblink") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold a wand and the Blink Focus on real terrain. Socket the focus and cast it at 128 blocks away and at a wall; try both upgrades.

**Expect**

- [ ] You teleport along your sight up to 128 blocks; both upgrades behave as described.

## 4. Infusion enchanting

Check id: `forbidden_magic.enchant`

**Steps**

1. Read its research entry ("Wrath") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a built infusion altar (centre pedestal, matrix above, ring pedestals) with a diamond sword and pickaxe. Creative jars of every aspect stand behind it, so you bring no essentia. Infuse a tool with a Forbidden enchantment (Wrath or Impact recipes are in the book), then again with a second.

**Expect**

- [ ] The enchantment applies; the cost goes up per extra enchantment.

<sub>Already covered by automated pack tests: `enchantment_infusions_work`</sub>

## 5. Wrath Cage with tubes and jars

Check id: `forbidden_magic.wrath_cage`

**Steps**

1. Read its research entry ("Wrathcage") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a Wrath Cage with an essentia tube on top and tubes and jars on your hotbar. Attach jars and tubes to it; feed it Ira (fill a jar by other means).

**Expect**

- [ ] Tubes push essentia in and it pulls from neighbours; jars hold the same three channels.

<sub>Already covered by automated pack tests: `wrath_cage_takes_essentia`</sub>

## 6. Tainted imprints in the Wrath Cage

Check id: `forbidden_magic.tainted_imprints`

**Steps**

1. You stand in front of a Wrath Cage with a tainted pig and a plain pig penned beside it (difficulty Normal). Hold the Diabolist Fork, with two blank imprinting crystals in your inventory.
2. Kill the tainted pig with the fork, then the plain pig. Hover both crystals.
3. Next: Right-click the cage with the Tainted Pig crystal and fuel it with Vitium or Ira as in the Wrath Cage check (tubes and jars in the kit). Power it with the lever and watch what it spawns.
4. Optionally repeat on Peaceful.

**Expect**

- [ ] The tainted pig gives a crystal named Tainted Pig (Vitium); the plain pig gives a Pig crystal (Bestia).
- [ ] The cage spawns pigs that are tainted (the host's tainted look and behaviour), fuelled by Vitium.
- [ ] On Peaceful the cage spawns plain pigs.

<sub>Already covered by automated pack tests: `fork_kill_imprints_tainted_pig`, `cage_spawns_a_tainted_pig`, `tainted_pseudo_ids_resolve`</sub>

## 7. Euclidaisy

Check id: `forbidden_magic.euclidaisy`

**Steps**

1. Read its research entry ("Euclidaisy") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a plain, a floating and a potted Euclidaisy and a full creative mana pool, with a Botania wand and spare flowers. Bind the flowers to the pool if they are not bound (wand on flower, then pool) and check the wand HUD on each.
3. Use a Thaumaturge crafting source that spawns the flower's trigger and watch what it drops.
4. Repeat with Thaumic Horizons installed and again without it.

**Expect**

- [ ] Plain, floating and potted forms place and render; the floating one hovers and animates.
- [ ] It draws mana from the pool and drops a wisp essence of an aspect with Thaumic Horizons installed, or 2 essentia crystals of an aspect without it.
- [ ] The research entry unlocks in that order and the recipe pages (infusion, floating-flower crafting) show in the book and JEI.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 8. Whisperweed

Check id: `forbidden_magic.whisperweed`

**Steps**

1. Read its research entry ("Whisperweed") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a plain, a floating and a potted Whisperweed and a full creative mana pool, with a Botania wand. Bind them to the pool if needed, stand within the radius and watch the radius overlay in the wand HUD.

**Expect**

- [ ] All three forms place and render; it grants aspect knowledge to players in range while it has mana; the overlay matches the real radius.
- [ ] Its recipe uses a curio of knowledge and shows in the book.

## 9. Tainthistle

Check id: `forbidden_magic.tainthistle`

**Steps**

1. Read its research entry ("Tainthistle") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a plain, a floating and a potted Tainthistle, a full creative mana pool and a few flux gas blocks and taint fibre around them, with a Botania wand. Bind the flowers to the pool if needed and wait.

**Expect**

- [ ] All three forms place and render; the flux around it is drained up to depth 8 and mana is spent; with no mana it stops.
- [ ] The radius overlay shows in the wand HUD.

## 10. Bloodthorn

Check id: `forbidden_magic.bloodthorn`

**Steps**

1. Read its research entry ("Bloodmagic") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a plain, a floating and a potted Bloodthorn, a full creative mana pool and a cow within 6 blocks of them, with a Botania wand and redstone blocks. Bind the flowers to the pool if needed; then power a flower with a redstone block.
3. For the Ara Vitae recipe you hold a red mystical flower and an Ara Vitae block (you must build an altar at tier 3 and place the block yourself).

**Expect**

- [ ] All three forms place and render.
- [ ] Mobs in range get Weakness III for 60 ticks, costing 40 mana each; players are never hit; redstone stops it.
- [ ] The Ara Vitae recipe produces the Bloodthorn.

<sub>Already covered by automated pack tests: `bloodthorn`</sub>

## 11. Blood rod, staff vis and the Alchemical cap

Check id: `forbidden_magic.blood_rod`

**Steps**

1. Read its research entry ("Rod Blood", "Rod Blood Staff", "Cap Alchemical") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of an Arcane Workbench with a finished blood rod, a blood staff rod, caps, an alchemical cap, and an inert blood rod plus Ara Vitae (to test the finishing recipe, which needs a tier 3 altar you build).
3. Assemble a wand, hold it with a drained vis store and watch your network LP and the vis count. Repeat with the alchemical cap on the wand, then with an empty network.
4. Next: You stand in front of a built infusion altar with a gold cap and three arcane scribe tools; creative jars of every aspect stand behind the altar, so you bring no essentia. Infuse the gold cap with the tools (the recipe is in the research book, cap_alchemical).

**Expect**

- [ ] The wand binds to you; vis refills, paying the network 5 LP per centivis (4 with the alchemical cap).
- [ ] With no LP it takes your health instead.
- [ ] The rod tooltip and binding show correctly; the rod recipes show in the research book and JEI.
- [ ] The infusion recipe completes and yields the alchemical cap; it fits on a wand and is cheaper per vis than the plain cap.

<sub>Already covered by automated pack tests: `blood_rod_drain_and_recharge`, `content_present`</sub>

## 12. Eldritch Blood Orb: binding and filling

Check id: `forbidden_magic.eldritch_orb`

**Steps**

1. Read its research entry ("Eldritchorb") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold the finished Eldritch Blood Orb (the infusion is covered by the automatic tests), an Ara Vitae block and a water bucket. Right click the orb to bind it, then right click it in the air, and use it with a Neo Vitae altar (place Ara Vitae yourself) and with a fluid tank to fill it.

**Expect**

- [ ] It is a tier 6 orb that binds to you with right click and shows your name.
- [ ] It holds 80,000,000 anima; an altar/ritual treats it as tier 6.
- [ ] It fills from fluid at a capacity of 28,000 (fill rate 25).

<sub>Already covered by automated pack tests: `content_present`</sub>

## 13. Rapier of the Strix

Check id: `forbidden_magic.rapier`

**Steps**

1. Read its research entry ("Bloodrapier") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold the Rapier of the Strix, with two frozen zombies ahead. Attack them and read the item tooltip.
3. Attack while wearing nothing, then at full health and at low health.

**Expect**

- [ ] Base damage is low (1) with attack speed 1.8-equivalent; hits drain LP/health as described and apply Weakness on hit.
- [ ] The swing feels quick and the recipe shows in the research book.

<sub>Already covered by automated pack tests: `rapier_and_dragonslayer`</sub>

## 14. Bloodwell, Boundwell and the Blood Seal

Check id: `forbidden_magic.wells_seal`

**Steps**

1. Read its research entry ("Bloodwell") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold a finished Bloodwell and Boundwell (crafting them is in the research book). Hold the Bloodwell with an empty and with a full network, then use the Boundwell with enough LP and with too little.
3. Next: You hold a weak blood orb and a milk bucket. Run /effect give @s forbiddenmagic:blood_seal 60 0 and fill your soul network with LP (an altar).
4. Wait several seconds, then remove the effect with the milk or /effect clear.

**Expect**

- [ ] The Bloodwell refills every tick from the owner (25 EV per point; otherwise it takes 2 health above 6).
- [ ] The Boundwell costs 10,000 EV or health; with too little it fails; fake players cannot use it.
- [ ] The effect icon shows; while it lasts the network is capped (it cannot be filled past the cap); clearing it restores normal filling.

<sub>Already covered by automated pack tests: `content_present`, `blood_seal_caps_the_network`</sub>

## 15. Ritual of Sanity

Check id: `forbidden_magic.ritual_sanity`

**Steps**

1. Read its research entry ("Bloodmagic") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a master ritual stone with a ritual diviner and an activation crystal. Use the diviner to look up the Ritual of Sanity and build its runes (not staged), then activate it with the crystal and stand inside the range.

**Expect**

- [ ] The ritual is listed by name with a description and info text; it builds and activates.
- [ ] It reduces warp for players in range at the listed cost per period; the range is adjustable; the owner gets nausea.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 16. Dragonslayer and Dragonwrack (creative only)

Check id: `forbidden_magic.dragon_items`

**Steps**

1. You hold the Dragonslayer (it has no recipe), with a frozen zombie and a frozen ender dragon ahead. Right click to block, and attack the zombie, then the dragon.
2. Run /effect give @e[type=minecraft:zombie,limit=1,sort=nearest] forbiddenmagic:dragonwrack 30 0.

**Expect**

- [ ] Dragonslayer blocks on right click and strikes dragons extra hard; it has no recipe and is not in JEI recipes.
- [ ] Dragonwrack damages the afflicted mob while the effect lasts.

<sub>Already covered by automated pack tests: `rapier_and_dragonslayer`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `forbidden_magic`).
