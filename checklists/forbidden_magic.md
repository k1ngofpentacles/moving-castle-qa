# QA: Forbidden Magic (Thaumaturge)

Chapter id `forbidden_magic`, 19 checks. In game this is the FTB Quests chapter **QA: Forbidden Magic (Thaumaturge)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `forbiddenmagic:blink_focus`

## 1. The Apocrypha tab

Check id: `forbidden_magic.apocrypha`

**Steps**

1. You have the whole research book granted. Open it and the Apocrypha tab.

**Expect**

- [ ] The tab opens, entries unlock in order, recipes show on their pages.

## 2. Infusion enchanting

Check id: `forbidden_magic.enchant`

**Steps**

1. You stand in front of a built infusion altar (centre pedestal, matrix above, ring pedestals) with a diamond sword and pickaxe. Creative jars of every aspect stand behind it, so you bring no essentia. Infuse a tool with a Forbidden enchantment (Wrath or Impact recipes are in the book), then again with a second.

**Expect**

- [ ] The enchantment applies; the cost goes up per extra enchantment.

<sub>Already covered by automated pack tests: `enchantment_infusions_work`</sub>

## 3. Wand assembly and recharging

Check id: `forbidden_magic.wands`

**Steps**

1. You stand in front of an Arcane Workbench with the infernal and tainted rods and four gold caps. Assemble a wand of each; hold the tainted-rod wand on the taint soil strip ahead (the infernal one needs the Nether: go there yourself).

**Expect**

- [ ] Assembly works; the infernal rod recharges in the Nether, the tainted rod in taint.

## 4. Wrath Cage with tubes and jars

Check id: `forbidden_magic.wrath_cage`

**Steps**

1. You stand in front of a Wrath Cage with an essentia tube on top and tubes and jars on your hotbar. Attach jars and tubes to it; feed it Ira (fill a jar by other means).

**Expect**

- [ ] Tubes push essentia in and it pulls from neighbours; jars hold the same three channels.

<sub>Already covered by automated pack tests: `wrath_cage_takes_essentia`</sub>

## 5. Blink Focus

Check id: `forbidden_magic.blink`

**Steps**

1. You hold a wand and the Blink Focus on real terrain. Socket the focus and cast it at 128 blocks away and at a wall; try both upgrades.

**Expect**

- [ ] You teleport along your sight up to 128 blocks; both upgrades behave as described.

## 6. Hidden items stay out of the creative tab and JEI

Check id: `forbidden_magic.hidden_items`

**Steps**

1. You are in creative mode. Open the Forbidden Magic creative tab and search the tab and JEI for: vinteum cap, witchwood rod, witchwood staff rod, equivalent rod, alchemical cap.
2. Then look up the alchemical cap in JEI by its recipe (gold cap with three arcane inscription tools).

**Expect**

- [ ] None of the five is listed in the creative tab.
- [ ] The four tagged ones (vinteum cap, both witchwood rods, equivalent rod) are absent from JEI; the alchemical cap is not in the tab but its recipe does show in JEI.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 7. Translation spot check

Check id: `forbidden_magic.translation`

**Steps**

1. You are in creative mode. Switch the game language to French, then open the Forbidden Magic creative tab and hover Crystal Scribing Tools.
2. Optionally repeat with Chinese (zh_CN) and Korean; then switch back to English.

**Expect**

- [ ] The crystal scribing tools item reads in French, as do other translated names; untranslated names fall back to English with no raw keys shown.

## 8. Euclidaisy

Check id: `forbidden_magic.euclidaisy`

**Steps**

1. You stand in front of a plain, a floating and a potted Euclidaisy and a full creative mana pool, with a Botania wand and spare flowers. Bind the flowers to the pool if they are not bound (wand on flower, then pool) and check the wand HUD on each.
2. Use a Thaumaturge crafting source that spawns the flower's trigger and watch what it drops.
3. Repeat with Thaumic Horizons installed and again without it.

**Expect**

- [ ] Plain, floating and potted forms place and render; the floating one hovers and animates.
- [ ] It draws mana from the pool and drops a wisp essence of an aspect with Thaumic Horizons installed, or 2 essentia crystals of an aspect without it.
- [ ] The research entry unlocks in that order and the recipe pages (infusion, floating-flower crafting) show in the book and JEI.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 9. Whisperweed

Check id: `forbidden_magic.whisperweed`

**Steps**

1. You stand in front of a plain, a floating and a potted Whisperweed and a full creative mana pool, with a Botania wand. Bind them to the pool if needed, stand within the radius and watch the radius overlay in the wand HUD.

**Expect**

- [ ] All three forms place and render; it grants aspect knowledge to players in range while it has mana; the overlay matches the real radius.
- [ ] Its recipe uses a curio of knowledge and shows in the book.

## 10. Tainthistle

Check id: `forbidden_magic.tainthistle`

**Steps**

1. You stand in front of a plain, a floating and a potted Tainthistle, a full creative mana pool and a few flux gas blocks and taint fibre around them, with a Botania wand. Bind the flowers to the pool if needed and wait.

**Expect**

- [ ] All three forms place and render; the flux around it is drained up to depth 8 and mana is spent; with no mana it stops.
- [ ] The radius overlay shows in the wand HUD.

## 11. Bloodthorn (needs Neo Vitae)

Check id: `forbidden_magic.bloodthorn`

**Steps**

1. You stand in front of a plain, a floating and a potted Bloodthorn, a full creative mana pool and a cow within 6 blocks of them, with a Botania wand and redstone blocks. Bind the flowers to the pool if needed; then power a flower with a redstone block.
2. For the Ara Vitae recipe you hold a red mystical flower and an Ara Vitae block (you must build an altar at tier 3 and place the block yourself).

**Expect**

- [ ] All three forms place and render.
- [ ] Mobs in range get Weakness III for 60 ticks, costing 40 mana each; players are never hit; redstone stops it.
- [ ] The Ara Vitae recipe produces the Bloodthorn.

<sub>Already covered by automated pack tests: `bloodthorn`</sub>

## 12. Blood rod and staff vis from LP

Check id: `forbidden_magic.blood_rod`

**Steps**

1. You stand in front of an Arcane Workbench with a finished blood rod, a blood staff rod, caps, an alchemical cap, and an inert blood rod plus Ara Vitae (to test the finishing recipe, which needs a tier 3 altar you build).
2. Assemble a wand, hold it with a drained vis store and watch your network LP and the vis count. Repeat with the alchemical cap on the wand, then with an empty network.

**Expect**

- [ ] The wand binds to you; vis refills, paying the network 5 LP per centivis (4 with the alchemical cap).
- [ ] With no LP it takes your health instead.
- [ ] The rod tooltip and binding show correctly; the rod recipes show in the research book and JEI.

<sub>Already covered by automated pack tests: `blood_rod_drain_and_recharge`, `content_present`</sub>

## 13. Alchemical cap recipe

Check id: `forbidden_magic.alchemical_cap`

**Steps**

1. You stand in front of a built infusion altar with a gold cap and three arcane scribe tools; creative jars of every aspect stand behind the altar, so you bring no essentia. Infuse the gold cap with the tools (the recipe is in the research book, cap_alchemical).

**Expect**

- [ ] The infusion recipe completes and yields the alchemical cap; it fits on a wand and is cheaper per vis than the plain cap.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 14. Eldritch Blood Orb: tier 6, binding, filling

Check id: `forbidden_magic.eldritch_orb`

**Steps**

1. You hold the finished Eldritch Blood Orb (the infusion is covered by the automatic tests), an Ara Vitae block and a water bucket. Right click the orb to bind it, then right click it in the air, and use it with a Neo Vitae altar (place Ara Vitae yourself) and with a fluid tank to fill it.

**Expect**

- [ ] It is a tier 6 orb that binds to you with right click and shows your name.
- [ ] It holds 80,000,000 anima; an altar/ritual treats it as tier 6.
- [ ] It fills from fluid at a capacity of 28,000 (fill rate 25).

<sub>Already covered by automated pack tests: `content_present`</sub>

## 15. Rapier of the Strix

Check id: `forbidden_magic.rapier`

**Steps**

1. You hold the Rapier of the Strix, with two frozen zombies ahead. Attack them and read the item tooltip.
2. Attack while wearing nothing, then at full health and at low health.

**Expect**

- [ ] Base damage is low (1) with attack speed 1.8-equivalent; hits drain LP/health as described and apply Weakness on hit.
- [ ] The swing feels quick and the recipe shows in the research book.

<sub>Already covered by automated pack tests: `rapier_and_dragonslayer`</sub>

## 16. Bloodwell and Boundwell

Check id: `forbidden_magic.wells`

**Steps**

1. You hold a finished Bloodwell and Boundwell (crafting them is in the research book). Hold the Bloodwell with an empty and with a full network, then use the Boundwell with enough LP and with too little.

**Expect**

- [ ] The Bloodwell refills every tick from the owner (25 EV per point; otherwise it takes 2 health above 6).
- [ ] The Boundwell costs 10,000 EV or health; with too little it fails; fake players cannot use it.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 17. Blood Seal

Check id: `forbidden_magic.blood_seal`

**Steps**

1. You hold a weak blood orb and a milk bucket. Run /effect give @s forbiddenmagic:blood_seal 60 0 and fill your soul network with LP (an altar).
2. Wait several seconds, then remove the effect with the milk or /effect clear.

**Expect**

- [ ] The effect icon shows; while it lasts the network is capped (it cannot be filled past the cap); clearing it restores normal filling.

<sub>Already covered by automated pack tests: `blood_seal_caps_the_network`</sub>

## 18. Ritual of Sanity

Check id: `forbidden_magic.ritual_sanity`

**Steps**

1. You stand in front of a master ritual stone with a ritual diviner and an activation crystal. Use the diviner to look up the Ritual of Sanity and build its runes (not staged), then activate it with the crystal and stand inside the range.

**Expect**

- [ ] The ritual is listed by name with a description and info text; it builds and activates.
- [ ] It reduces warp for players in range at the listed cost per period; the range is adjustable; the owner gets nausea.

<sub>Already covered by automated pack tests: `content_present`</sub>

## 19. Dragonslayer and Dragonwrack (creative only)

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
