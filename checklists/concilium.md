# QA: Thaumic Concilium

Chapter id `concilium`, 98 checks. In game this is the FTB Quests chapter **QA: Thaumic Concilium**; each check there has a green "Set up this check" line that builds its test site.

## 1. Thaumaturges: meeting, trading and fighting beside them

Check id: `concilium.thaumaturges`

**Steps**

1. Read its research entry ("Thaumaturges") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Thaumaturge stands three blocks ahead and you have no Thaumaturge research yet. Right-click it.
3. Next: A Thaumaturge stands three blocks ahead and the research is done; bottles, an enchanted book, a skull, mana beans and dirt are in your hotbar. Right-click it.
4. Put a bottle o' enchanting in the left slot and click the dice. Take the goods out, then try the enchanted book, the skull, mana beans and dirt.
5. Next: Two Thaumaturges stand ahead, and you have a diamond sword in survival. Hit one with the sword.
6. Next: It is night: a Thaumaturge stands five blocks ahead with a zombie and a skeleton about eleven blocks beyond it. Watch what the Thaumaturge does (stay near it).
7. Next: The prerequisites of Reflection, Positive Burst, Impulse, Thick Taint and Runic Windings are done, and you hold the Scribbled Research Notes for Reflection and a Thaumonomicon. Hover over the notes, then open the Thaumonomicon at the Reflection Focus entry and start it.
8. Do the same for Positive Burst, Impulse, Thick Taint or Runic Windings without their notes.
9. Next: Staging does not move you: this check needs real terrain. Over a few in-game days, explore new (never-loaded) chunks with villages, desert and jungle temples, witch huts, igloos and ruined portals; also stay put near home.
10. Next: A Mad Thaumaturge, a Nether Explorer and a Withered Botanist stand still ahead (the botanist needs Botania), and you have a thaumometer; only the Concilium root is researched. Scan the Mad Thaumaturge and the Nether Explorer with the thaumometer, then open the Concilium tab in the Thaumonomicon.

**Expect**

- [ ] A purple chat line mocking you ('Why are you mooing? Can you even read?' or one of three others). No trade screen.
- [ ] Thaumcraft's Pech trade screen. The dice light up only for something the Thaumaturge values (not dirt) and only while the four payout slots are empty.
- [ ] Each click takes one offered item and lays out a few things: mana beans, essentia crystals, Curios of Knowledge, crystal clusters, more rarely a focus pouch, a fire focus, a vis amulet or a profane wand core.
- [ ] If you have a finished research note, offering it buys Scribbled Research Notes (Positive Burst or Impulse) and a purple remark.
- [ ] Both turn on you: angry-villager puffs, fire bolts from their wands at range, punches up close. The trade screen won't open while they're angry.
- [ ] After 20 to 40 seconds they calm down and trade again. They heal slowly meanwhile.
- [ ] It attacks them with its wand, unprovoked.
- [ ] Tooltip: 'Hm, the only things missing are a method of experience exchanging and a brain contact scheme...'
- [ ] Reflection asks for the notes and takes them when you begin it. The others can't be started without their own notes.
- [ ] Now and then a structure (about one in several) has one to three Thaumaturges living at it when you first find it. They don't respawn there, and never appear in the open countryside.
- [ ] Now and then, one or two wander up to you wherever you are, and leave after a day or two.
- [ ] Scanning the Mad Thaumaturge reveals 'Mad Thaumaturges'; scanning the explorer reveals 'The Price of Scientific Advances', both left of the tab's root. Scanning a Withered Botanist adds its page.

<sub>Already covered by automated pack tests: `thaumaturge_trades`, `thaumaturge_menu`, `hint_gates`, `thaumaturge_haunts`</sub>

## 2. Mad Thaumaturges

Check id: `concilium.mad_thaumaturges`

**Steps**

1. Read its research entry ("Mad Thaumaturges") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are in survival with a diamond sword; two Mad Thaumaturges stand nine blocks ahead. Let one reach you; hit it a few times. Kill both, and spawn a few more with /summon if you want more drops.

**Expect**

- [ ] Ragged skin, a void hoe or shovel. It hunts you (and Thaumaturges and cultists), sometimes leaps onto you and claws at you before falling off. Sad mutterings.
- [ ] Drops: usually a Curio of Knowledge or nothing; one in five a set of Scribbled Research Notes (Reflection, Thick Taint or Runic Windings).
- [ ] About one Brainy Zombie in five is replaced by one as it spawns. They spawn in any biome, the Nether and the End included.

## 3. Nether Explorers

Check id: `concilium.nether_explorers`

**Steps**

1. Read its research entry ("Fallen") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A lava pool lies four blocks ahead with two Nether Explorers drifting on it; you have a diamond sword (do not step into the lava).
3. Right-click one; hit the other.

**Expect**

- [ ] A thin body lies on its back and floats on lava (and water), drifting slowly.
- [ ] Right-click: a Nether Membrane in your inventory, a heartbeat, and the Nether Membrane research. Hit: the membrane pops out and survives the lava.

<sub>Already covered by automated pack tests: `nether_explorer`</sub>

## 4. Nether Membrane

Check id: `concilium.nether_membrane`

**Steps**

1. Read its research entry ("Nether Membrane") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have two Nether Membranes and a diamond sword, and a lava pool lies four blocks ahead. Craft the membrane with the sword (any grid). Throw the wrapped sword into the lava.
3. Next: You hold a Nether Membrane next to a vanilla phantom membrane. Look at them in the inventory.

**Expect**

- [ ] One sword with a red 'Nether Protection' line. It floats on lava like netherite. A wrapped item can't be wrapped again.
- [ ] It is the phantom membrane shape tinted crimson (dark red-pink). Say if it should be lighter.

<sub>Already covered by automated pack tests: `nether_membrane_recipe`</sub>

## 5. Withered Botanist

Check id: `concilium.withered_botanist`

**Steps**

1. Read its research entry ("Fallen") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. With Botania: a Withered Botanist lies on the grass three blocks ahead. Right-click it.

**Expect**

- [ ] Three or four Botania mystical flowers of random colours bloom around it, petals and coloured motes rise, the wind sighs, and the body is gone.

## 6. Chort and Sloppy Alchemist

Check id: `concilium.sloppy_alchemist`

**Steps**

1. You stand on the pad with a diamond sword, a Thaumometer and three Sloppy Alchemist spawn eggs; a Sloppy Alchemist (with his Chort) stands six blocks ahead.
2. Watch the pair come at you for half a minute; let a few globs hit you, then step back and let him ram you.
3. Scan the Sloppy Alchemist with the Thaumometer, then read his research entry ("Sloppy Alchemist", under Fallen): judge clarity, typos, and whether it explains the feature.
4. Kill the Chort on his back (not him), then right-click the Sloppy Alchemist.
5. Use an egg for another pair and kill both: judge the drops. Use another egg and right-click the new Alchemist while the Chort still rides.
6. Later, in a Nether survival trip: judge how often the pair turns up.

**Expect**

- [ ] A gaunt alchemist carries a small horned Chort on his back. The Chort spits three globs about every two seconds; the Alchemist keeps his distance, then rams with a hard knockback.
- [ ] The scan unlocks the hidden Sloppy Alchemist entry next to Fallen.
- [ ] Freed, he stops fighting; the right-click gives flames, a breath sound, a thank-you line in dark red and 1-3 demon's blood or bottles of blood, and he leaves.
- [ ] Right-clicking him while ridden does nothing. Neither mob burns in fire or lava.
- [ ] Nether: an occasional encounter, rarer than ghasts; never in the overworld.

<sub>Already covered by automated pack tests: `attributes_and_sizes`, `spawn_hook_mounts_a_chort`, `freed_and_unfreed_interaction`, `spit_volley`, `alchemist_charge`, `alchemist_research_entry`, `data_resolves`</sub>

## 7. Burned Witch: her brews, orbit and immunity

Check id: `concilium.burned_witch`

**Steps**

1. You stand on the pad in survival with a bow, arrows, a Thaumometer and three Burned Witch spawn eggs; a Burned Witch flies six blocks ahead.
2. Let her circle you for half a minute and take a few of her brews; watch her broom and how she flies.
3. Scan her with the Thaumometer, then read her research entry ("Burned Witch", under Fallen): judge clarity, typos, and whether it explains the feature.
4. Shoot her down and judge the drops. Use the other eggs to fight more.
5. If you can: become a vampire or a werewolf in the remake and let her attack you again.
6. Later, in a Nether survival trip: judge how often she turns up.

**Expect**

- [ ] A charred witch on a broom circles you in the air and throws a brew about every one and a half seconds: Brew of Webs or Brew of Wasting.
- [ ] Against a vampire she throws a Sun Grenade, against a werewolf a wolfsbane flask; her own and other brews do nothing to her. She does not burn in fire or lava.
- [ ] The scan unlocks the hidden Burned Witch entry next to Fallen. Drops: blaze powder, ghast tears, foul fume, oil of vitriol or reek of misfortune.
- [ ] Nether: an occasional encounter, never in the overworld.

<sub>Already covered by automated pack tests: `attributes_and_flags`, `brew_choice`, `projectiles_and_items`, `orbit_and_throw_cycle`, `immune_to_brews`, `loot_as_the_originals_roll`, `burned_witch_research_entry`, `data_resolves`</sub>

## 8. Imp pact

Check id: `concilium.imp_pact`

**Steps**

1. You stand on the pad in survival with Sloppy Alchemist spawn eggs; a Witchery imp stands three blocks ahead. Right-click the imp.
2. Use an egg about eight blocks away: a Sloppy Alchemist and his Chort appear. Stand near the pair for a minute.
3. Hit the Chort once.
4. Right-click the imp again with whatever its soul trading asks for.

**Expect**

- [ ] After the imp: the pair ignores you; when the Chort would have attacked, chat shows a dark red line about dealing with a business person.
- [ ] Once you strike, they fight back as usual.
- [ ] The imp's own soul trading screen still opens: the pact never takes it over.
- [ ] The pact lasts an hour of play (config impPactTime) and then the pair attacks on sight again.

<sub>Already covered by automated pack tests: `imp_pact_starts_and_never_cancels`, `pact_players_are_not_targeted`</sub>

## 9. Burning Site: the village pen, its hunter, stake and palisade

Check id: `concilium.burning_site`

**Steps**

1. The world is not on Peaceful (the hunter is a monster). You stand south of a closed 9 x 9 pen of cobblestone wall with a gravel floor: a pyre of coal, hay and logs round a four-high stake, and a Witch Hunter with a crossbow inside. Walk round it and look at the pyre, the stake (foot, shackle, shaft, top) and the hunter.
2. Stay a few blocks from the wall in the open. Does the hunter ignore you (a plain player)?
3. Next: a zombie stands ten blocks beyond the pen. Does the hunter shoot it over the wall?
4. Next: you hold a voodoo poppet in the hotbar. Walk up to the wall in sight of the hunter: does it shoot you? Put the poppet away: does it stop?
5. Next: three palisade posts stand in a row with one on top of the middle one and a stub joined to it. Look at the points (only the topmost post of a stack has one) and at how the posts join. Stand on a post.
6. Next: any village. Over time, `/locate structure minecraft:village_plains` (also desert, savanna, snowy, taiga) and look for a pen among its houses: rare, about one house in ten, never two in a village. Desert pens have a sandstone floor.

**Expect**

- [ ] The pen is closed all round (no gap), gravel inside, one pyre of nine mixed blocks and a stake of four distinct parts; the hunter stands inside in hunter armour holding a crossbow.
- [ ] The hunter does nothing to a plain player (no shot, no bear trap at your feet).
- [ ] The hunter turns and shoots the zombie.
- [ ] With a voodoo (or vampiric) poppet in your inventory the hunter shoots you; without it, not.
- [ ] Only the top post of a palisade stack shows a sharpened point; neighbouring posts and a fence gate join; standing on a post hurts (3 damage, as cactus). The posts are thin but readable, and the stake is blunt and does not hurt.
- [ ] A village may carry a pen (rarely); it sits level with the street, never twice in one village.

<sub>Already covered by automated pack tests: `places_plain`, `places_desert_rotated`, `second_chunk_pass_spawns_no_second_hunter`, `one_per_village_picks_the_first_site`, `injection`, `targeting_rule`, `reload_swaps_again`, `stockade_exists_only_with_the_remake`, `stockade_behaviour`, `stake_parts`</sub>

## 10. Casting bracelets: worn, off-hand and in hand

Check id: `concilium.bracelets`

**Steps**

1. Read its research entry ("Casting Bracelets") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the void bracelet (Signal) in the Curios bracelet slot.
3. Look at yourself in F5 (front and back) and ask a friend to look.
4. Next: You are already wearing the void bracelet (Signal) in the Curios bracelet slot and hold an iron sword. Press V to cast Signal from the bracelet.
5. Watch in first person, then F5.
6. Next: You hold the void bracelet. Put it in your off hand (not a curio slot) and press V.
7. Next: You hold the eldritch bracelet in your main hand, in front of an Arcane Workbench. Right-click to cast Impulse.
8. Use it in the Arcane Workbench's wand slot. (Tapping an aura node needs a real node: find one if you want that part.)
9. Next: You are already wearing the void bracelet, and a shield is in your hotbar. Put the shield in your off hand and press V.

**Expect**

- [ ] A band of void metal with purple rims and a glowing gem on the back of your left wrist (right wrist if you play left-handed).
- [ ] Hidden if you turn the slot's visibility off.
- [ ] The left arm stretches out ahead and a little up, hand towards the middle of the view ('Moses reaching for the sea'), band and gem visible.
- [ ] A burst of particles in the spell's colour at the hand.
- [ ] Vis drops by about two thirds of a wand's cast; the cooldown is half.
- [ ] Band on the left wrist; V casts from it.
- [ ] Band on the right wrist, the right forearm rises when casting.
- [ ] Casts at bracelet prices (2/3 vis, half cooldown).
- [ ] Taps nodes and works in the Arcane Workbench like a wand.
- [ ] Nothing is cast; the action bar says your shield arm is busy (only shield foci cast past a shield).
- [ ] Take the shield out: V casts again. A bracelet held in either hand still right-clicks normally.

<sub>Already covered by automated pack tests: `bracelet_casting`, `bracelet_parts`</sub>

## 11. Channelled spells and the focus radial

Check id: `concilium.bracelet_channel`

**Steps**

1. Read its research entry ("Infernal Bracelet") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the infernal bracelet (Cooling focus) in the Curios bracelet slot. Hold V for a few seconds, then let go.
3. Next: You are already wearing a void bracelet with no focus (no wand in hand); a Positive Burst focus is in your hotbar. Hold F and pick the focus from the radial.

**Expect**

- [ ] Snowballs while held; the arm stays up and motes swirl at the wrist; it lowers on release.
- [ ] A radial of your foci; the chosen focus socketed in the bracelet; the HUD next to the hotbar shows it and the vis bars.

## 12. Blood Bracelet: vis from your soul network

Check id: `concilium.blood_bracelet`

**Steps**

1. Read its research entry ("Blood Bracelet") and its recipe page: judge clarity, typos, and whether it explains the feature.
2. You wear the Blood Bracelet (Signal) in the Curios bracelet slot; a Weak Blood Orb is in your inventory and your network holds 5000 LP. Right-click the orb once to bind it. Cast Signal with V until the bracelet is dry, then wait half a minute.
3. Type /neovitae anima-network @s set 0, set your health to 4 hearts and wait with the bracelet on.
4. Take the bracelet off and keep it in your inventory for half a minute.

**Expect**

- [ ] A band of bloodstone brick with gilded rims on your wrist.
- [ ] Vis climbs back by about one vis per primal a second while LP falls (4 LP per centivis with the alchemical cap).
- [ ] With no LP it takes 1.5 hearts at a time instead, and at 3 health or less it kills you (death message from Forbidden Magic's blood staff).
- [ ] Off the wrist it does not refill.

<sub>Already covered by automated pack tests: `blood_bracelet_exists_only_with_neovitae`, `blood_bracelet_refills_worn_not_carried`, `blood_bracelet_health_fallback_kills_at_three`</sub>

## 13. Drainage Syringe: draw and return vis, mana and blood

Check id: `concilium.drainage_syringe`

**Steps**

1. Needs Thaumic Horizons, Botania and Neo Vitae. Read its research entry ("Drainage Syringe") and recipe: judge clarity, typos, and whether it explains the feature.
2. You hold the syringe (closed, blood mode). A cow stands two blocks ahead. Hold right-click on it for ten seconds.
3. Shift + left-click in the air with the syringe empty, three times; then shift + right-click to open it.
4. Right-click the Weak Blood Orb once to bind it. Fill the syringe in blood mode from the cow again, open it and hold right-click; watch /neovitae anima-network @s query.
5. Next (LAN, a second player): draw from the other player in each mode.
6. Look at the syringe held, in first and third person, idle and while using it; then hold it in your off hand (and try left-handed in the options).

**Expect**

- [ ] Every two seconds the cow takes a tenth of its health with a stab sound; it stops at half health.
- [ ] The mode cycles vis, mana, blood; it only cycles when the syringe is empty; shift + right-click opens and closes the cap.
- [ ] Open, it pours 20000 LP a second into your network, never past your best orb's maximum (5000 for a Weak orb).
- [ ] A player loses vis from their wands, a million mana or a million LP per draw (the original's numbers).
- [ ] First person: the syringe rides the forearm, needle forward, with a small sway while in use; when closed a cap in the mode's colour, and the barrel fills with that colour as it draws. Third person and in the hotbar it shows bare (as the original). The off hand and left-handed views are mirror images.

<sub>Already covered by automated pack tests: `syringe_exists_only_with_all_three_mods`, `syringe_draws_from_mobs`, `syringe_drains_players_of_each_type`, `open_syringe_returns_to_the_user`, `syringe_type_cycles_only_when_empty`</sub>

## 14. Terrasteel Bracelet: the volley and one release per raise

Check id: `concilium.volley`

**Steps**

1. Read its research entry ("Terrasteel Bracelet") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the terrasteel bracelet in the Curios bracelet slot. Press V once.
3. Next: Only with Botania installed. You are already wearing the terrasteel bracelet with Riposte > Frost and have a shield in the off hand; zombies wait in a glass box ahead. Press V once (the volley is ten casts).
4. Break the glass, lower and raise the shield and take ten separate parried hits, one per raise.
5. Next: You are already wearing the terrasteel bracelet (Riposte > Frost, several charges) and a shield in the off hand; two zombies wait in a glass box ahead. Press V, break the glass and take two quick hits within one raise.

**Expect**

- [ ] Ten Signal casts at once; a long cooldown; a big vis bill (each cast at the original's 3.0 cost modifier).
- [ ] One cast arms ten charges (the ward grows brighter and adds shells with charges), at the usual long volley cooldown.
- [ ] Each parried hit spends one charge; after ten the ward is gone.
- [ ] Only the first hit releases; the second is just blocked. Judge this call: one release per raise.

<sub>Already covered by automated pack tests: `bracelet_volley`, `riposte_past_window_and_same_raise`</sub>

## 15. Riposte and Aegis foci: building them and how they look

Check id: `concilium.shield_build`

**Steps**

1. Read its research entry ("Riposte Focus", "Aegis Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand next to a Focal Manipulator with three blank foci in your hotbar. Build three foci: Self > Aegis; Riposte > Frost (or any effect); Aura > Aegis.
3. Read the part tooltips and the research entries Riposte focus and Aegis focus, and the new paragraph on the guard stance in Casting Bracelets.
4. Next: A Focal Manipulator stands in front of you, and you are already wearing both bracelets and have a shield. Look at the part icons and the Aegis effect icon in the Focal Manipulator and the HUD, and at the wards in play.

**Expect**

- [ ] Riposte and Aegis appear as spell parts once researched; the research entries read clearly and the guard stance paragraph says what a shield blocks.
- [ ] Settings (window 5 to 20 s, duration 5 to 20 s) change the complexity and vis cost sensibly.
- [ ] Judge this call: Riposte window steps of 5 s (default 10 s) with +1 complexity per step; Aegis aspect praemunio, complexity 6, vis 3, double cooldown.
- [ ] Both wards are runic amber on purpose; the spell parts keep their own colours: steel for the swordsman's Riposte, blue for the guardian's Aegis.
- [ ] Judge this call: that split (ward amber, parts steel and blue).

<sub>Already covered by automated pack tests: `guard_gate_walk`, `guard_look_messages`</sub>

## 16. Guard stance: aimed spells and the shield

Check id: `concilium.shield_guard`

**Steps**

1. Read its research entry ("Riposte Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing a void bracelet with the Signal focus socketed (a projectile), and a plain shield is already in your off hand. Press V.
3. Swap to the Self > Aegis focus in your hotbar and press V. Try Self > Signal as well, and the Aura > Frost drum focus.
4. Take the shield out of the off hand and press V with Signal.
5. Next: You hold the shield in the main hand (off hand empty) and the void bracelet with Signal is already worn. Press V.

**Expect**

- [ ] Signal is refused with the action-bar message 'You cannot aim past your shield', no vis spent, no cooldown, a fail sound.
- [ ] Self, Aura, Touch, Wall, Cloud and Riposte spells cast; Self > Signal is refused (it would aim).
- [ ] Without a shield in the off hand everything casts as before.
- [ ] It casts: only an off-hand shield triggers the guard stance (design decision 8).

<sub>Already covered by automated pack tests: `guard_gate_walk`, `guard_gate_press`</sub>

## 17. Riposte: arming, parrying melee and arrows, and expiry

Check id: `concilium.riposte`

**Steps**

1. Read its research entry ("Riposte Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have a shield in the off hand and are already wearing a bracelet with Riposte > Frost. Press V.
3. Watch the shield in first person and in F5, and listen.
4. Next: You are already wearing a void bracelet with Riposte > Frost socketed and have no shield in the off hand. Press V.
5. Next: A zombie waits in a glass box six blocks ahead, and you are already wearing the Riposte bracelet. Press V to arm Riposte (you have 10 seconds), then break the glass and let the zombie reach you.
6. Armed, lower the shield. Raise it (hold right-click) just before it hits, so the hit lands within half a second of raising.
7. Repeat, but hold the shield up for several seconds first and only then take a hit (press V again to re-arm).
8. Next: You are in survival at night with a zombie and a skeleton each in their own glass box ahead, and you are already wearing the Riposte bracelet. Arm Riposte (V), break a box open and do the melee parry against the real mob, then the skeleton.
9. Next: You are already wearing the Riposte bracelet. Two skeletons wait in glass boxes: one about 6 blocks away on your left, one about 11 blocks away on your right. Arm Riposte (V), break the near box and raise the shield just before the arrow lands.
10. Repeat from the far skeleton (about 11 blocks).
11. Next: You are already wearing the Riposte bracelet and have a shield in the off hand. Arm Riposte with the default 10 s window, do nothing, and wait. Also arm and then die (/kill) or log out.

**Expect**

- [ ] Vis is paid and the spell's normal cooldown starts. The shield gets a runic amber ward shell and a rim halo; a charge sound plays.
- [ ] The glow reads as 'armed', is not blinding in first person, and does not hide the shield.
- [ ] Judge this call: the look (accepted after round 4: runic amber wards).
- [ ] Refused with 'Riposte needs a shield in your off hand' before any vis is spent. Judge this call: the refusal before paying.
- [ ] Parry: the blow is blocked, the attacker takes the spell (Frost) at 1.5x power, a white-amber burst and crackle play, the shield loses 1 extra durability.
- [ ] Held past the window (10 ticks by default): the shield just blocks, the charge stays and the ward stays.
- [ ] Judge this call: the parry window feel. Is half a second fair or too tight? Is the burst short enough? (config riposte.parryTicks)
- [ ] It fires on a genuine blocked hit. The GameTests post the shield-block event directly, so this is the first real check of the damage pipeline.
- [ ] Within 8 blocks: the arrow's owner takes the spell.
- [ ] Beyond 8 blocks: the arrow is only blocked and the charge stays armed (config riposte.range).
- [ ] Judge this call: 8 blocks as the reach.
- [ ] After the window the ward fades and nothing fires; the vis is not refunded.
- [ ] Logging out or dying clears it. Judge this call: the window runs from the last arming or release, 5 to 20 s.

<sub>Already covered by automated pack tests: `riposte_arm_release_parry`, `guard_look_messages`, `riposte_needs_shield_and_cleanup`, `riposte_past_window_and_same_raise`, `riposte_archer_range`, `riposte_expiry`</sub>

## 18. Aegis: the ward, its arc and expiry

Check id: `concilium.aegis`

**Steps**

1. Read its research entry ("Aegis Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have a shield in the off hand and are already wearing a bracelet with Self > Aegis. Press V, then raise the shield. Check the effect icon in the HUD.
3. Next: Zombies wait in glass boxes behind you and on your right, and a witch on your left. The Aegis bracelet is already worn: press V for Aegis and raise the shield.
4. Break a box open and let the mob hit you from behind and from the side; let the witch throw potions at you.
5. Compare with the thaumium shield (it is in your hotbar; put it in the off hand).
6. Next: You are in survival at night wearing the Aegis bracelet. Ahead: a zombie in a glass box. On the right: a tall stone tower with a ladder (jump off the top). Further right: a fire on netherrack. On the left: a water shaft in a glass block.
7. With Aegis on (V), lower the shield, break the zombie box open and get hit.
8. With the shield raised, fall from the tower, stand in the fire, and drown in the shaft.
9. Next: You are already wearing the Aegis bracelet and have a shield in the off hand. Cast Aegis and wait out its duration (default 10 s) while holding the shield up.

**Expect**

- [ ] A beneficial Aegis effect icon appears; a rune ring on a ward wall shows while you block.
- [ ] Judge this call: the effect icon and the look.
- [ ] Hits from any direction are blocked with the forced-block crackle and rune flash and the warding sound; the shield takes double durability.
- [ ] Magic is blocked; on a thaumium or void shield the magic half is there already and Aegis adds the all-round arc.
- [ ] Lowered: the hit lands normally.
- [ ] Raised: fall, fire, drowning and starvation damage is never blocked.
- [ ] The icon and ward disappear on time and blocks return to normal.

<sub>Already covered by automated pack tests: `aegis_blocks`, `guard_look_messages`, `aegis_forced_block_triggers_riposte`</sub>

## 19. Aegis through an aura, with a friend on LAN

Check id: `concilium.aegis_aura`

**Steps**

1. Read its research entry ("Aegis Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing a bracelet with Aura > Aegis and have a shield in the off hand; a zombie waits in a glass box behind you. Open the world to LAN, a friend joins and stands next to you. Press V.
3. The friend raises their own shield; break the box open so the zombie hits them from behind. Then the friend, shield lowered, takes a hit.

**Expect**

- [ ] Both of you get the Aegis effect; the friend must still hold their own raised shield for it to block.
- [ ] Judge this call: sharing the effect to allies through an aura.

<sub>Already covered by automated pack tests: `aegis_aura_shares`</sub>

## 20. Riposte and Aegis together: a second client and shader packs

Check id: `concilium.shield_together`

**Steps**

1. Read its research entry ("Riposte Focus", "Aegis Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing two bracelets: a void one with Riposte > Frost and an infernal one with Self > Aegis, and have a shield in the off hand; a zombie waits in a glass box behind you. Press V for each, raise the shield, break the box open and take a hit from behind within half a second.
3. Next: You are already wearing the Riposte and Aegis bracelets and have a shield in the off hand; a zombie waits in a glass box behind you. In LAN, the friend watches you arm Riposte, parry a hit, and block with Aegis.
4. The friend then walks into view of you after you armed (catch-up), and logs in while you are armed.
5. Next: You are already wearing the Riposte and Aegis bracelets and have a shield in the off hand. With Iris installed and a shaderpack on, arm Riposte and cast Aegis; look in first and third person.
6. Check with any mod that also draws the off hand.

**Expect**

- [ ] The block Aegis forces counts for Riposte: the attacker takes the spell. Judge this call: Aegis counting for Riposte.
- [ ] They see the amber shell, the release burst, the Aegis ring and the forced-block crackle on you, with the same sounds nearby.
- [ ] A player who starts tracking you later still sees the current ward state.
- [ ] The shield is drawn normally with the ward on top; no missing shield, double hand or flicker in first person.
- [ ] Third person: the shells draw after the shield with no broken batches.
- [ ] Known untested: the first-person off-hand render takeover and the third-person batch end.

<sub>Already covered by automated pack tests: `aegis_forced_block_triggers_riposte`, `guard_look_messages`</sub>

## 21. Primal arrows

Check id: `concilium.primal_arrows`

**Steps**

1. Read its research entry ("Primal Arrows") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand with a bow, a crossbow, arrows and 16 of each primal arrow in your hotbar. A pig stands 9 blocks ahead; an armoured zombie is to its right; a dispenser (loaded with all six kinds, 4 each) faces a second pig to your left, with a lever beside it.
3. Fire each of the six primal arrows (aer, aqua, ignis, ordo, perditio, terra) from the bow at the pig and at the ground, then from the crossbow, then power the dispenser with the lever.
4. Try a primal arrow against the armoured zombie. A Power-enchanted bow or piercing crossbow is up to you.
5. Next: You stand with a bow, plain arrows and terra arrows. Two zombies that cannot walk stand 8 blocks ahead, one each side, at the same distance. Shoot a terra arrow at one and a plain arrow at the other.
6. Next: It is night and you hold a bow with all six primal arrows; a stone wall stands 9 blocks ahead. Fire each type at the wall and watch the arrow in flight and stuck in the stone; look at the items in the inventory too.

**Expect**

- [ ] Every type flies, lands and does damage from all three launchers, and each shows its own effect (aer, aqua, ignis fire or water interplay, ordo, perditio, terra).
- [ ] Primal damage ignores or reduces armour less than a plain arrow; the effect reads clearly and is not overwhelming.
- [ ] The dispenser fires them in a straight line like vanilla arrows.
- [ ] The terra arrow throws the mob back clearly further than a plain arrow does, without launching it absurdly far.
- [ ] Each arrow glows in its primal's colour in flight and while stuck, readable in the dark and distinct per type; no lag or flicker.

<sub>Already covered by automated pack tests: `primal_arrows_effects`, `primal_arrows_damage_types`, `primal_arrows_items_recipes_nbt`, `crimson_archer_fires_primal_arrow`</sub>

## 22. Powders: settling, Pride and Greed

Check id: `concilium.powders`

**Steps**

1. Read its research entry ("Shard Mill", "Silverwood Shard Mill") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a zombie 5 blocks away, with the Silverwood mill and wrath shards in your hotbar. Load the shards into the mill and grind at the zombie.
3. Next: You stand in front of a zombie 5 blocks away, with the Silverwood mill and pride shards in your hotbar. Note your coordinates (F3), then grind pride shards at the zombie.
4. Next: You stand with the Silverwood mill and greed shards in your hotbar; a zombie waits 6 blocks ahead and a little to the side. Grind greed shards near it.

**Expect**

- [ ] The dust drifts and settles for about two seconds, then the zombie bursts into flame (nothing on contact mid-air).
- [ ] You are never affected by your own powder.
- [ ] The zombie is flung towards x 0, z 0, 'the centre of the world', not simply away from the dust.
- [ ] The zombie is dragged onto the spot where the dust settled.

## 23. Shard Mills: look and cranking

Check id: `concilium.shard_mills`

**Steps**

1. Read its research entry ("Shard Mill") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold both Shard Mills and the armour pieces in your hotbar. Look at both mills in hand, in the GUI and dropped on the ground; wear the windings, jackboots and shorts and look at the armour layers; look through the item icons.
3. Next: You hold the Greatwood mill with shards in your hotbar, a zombie 6 blocks ahead as a target. Load shards (the original used essentia crystals; any shard loads the mill); crank it in first person, in third person (F5) and as seen by another player.

**Expect**

- [ ] Models sit right in hand (positions are first guesses: describe or screenshot what is off), armour layers fit, no missing textures.
- [ ] It tips toward you while loading; while grinding it is held bottom-forward with the crank spinning and the other hand working it; dust trails behind the motes.

## 24. Burdening Amulet and the pumpkin veil

Check id: `concilium.burdening_amulet`

**Steps**

1. Read its research entry ("Burdening Amulet") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand beside an untamed wolf (2 blocks ahead, to the right) with bones, the Burdening Amulet, a carved pumpkin and a bracelet with the Reflection focus in your hotbar. Feed the wolf bones until it is tame.
3. Gain temporary warp (cast Reflection from the bracelet). Wear the Burdening Amulet without the pumpkin and look at the wolf.
4. Put on the carved pumpkin and look at the zombie behind it.

**Expect**

- [ ] Without the veil: Death Gaze withers whatever you look at, your wolf included, and turns it on you.
- [ ] With the pumpkin on: no Death Gaze; the wolf attacks what you look at; your warp still drains.

## 25. Runic Windings and the strong numbers

Check id: `concilium.runic_windings`

**Steps**

1. Read its research entry ("Runic Windings") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand beside an arcane workbench (ahead, to the right) with both windings, the Silverwood mill and wrath, pride and greed shards in your hotbar. Wear one and then both windings and watch the runic shield; craft at the workbench with them worn.
3. Judge the original numbers kept: windings 200 charge each, entropy powder Wither 51, wrath powder's 50,000-second burn, pride and greed powders' speed of 3.

**Expect**

- [ ] The shield grows with both pieces and refills faster; the workbench vis discount applies. The strong numbers feel acceptable (report any that don't).

## 26. Tight Belt

Check id: `concilium.tight_belt`

**Steps**

1. Read its research entry ("Tight Belt") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold the Tight Belt and a bracelet with the Reflection focus. Cast Reflection a few times to gain temporary warp, then wear the belt.

**Expect**

- [ ] Warp turns into Thaumarhia by total warp, drains about 1 in 25 per tick, and the belt leaks flux gas.

## 27. Bottles thrown

Check id: `concilium.bottles`

**Steps**

1. Read its research entry ("Bottle Of Clear Water", "Bottle Of Thick Taint") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a fire (ahead), a burning zombie (left), a blaze (right) and a stone block (8 blocks ahead), with Clear Water and Thick Taint bottles in your hotbar. Throw the Clear Water on the fire, the burning zombie and the blaze; throw the Thick Taint on the stone.

**Expect**

- [ ] Fire goes out, the blaze is scalded; the taint splashes Flux Taint, fibres and flux gas, with splash particles.

## 28. Dump Jackboots

Check id: `concilium.jackboots`

**Steps**

1. Read its research entry ("Dump Jackboots") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the Dump Jackboots with stone in your hotbar. Hold the stone, sneak to climb; release sneak mid-climb; repeat on a LAN client.

**Expect**

- [ ] You rise steadily laying a block beneath you; releasing sneak never leaves a gap; same on the client.

## 29. Rifts from nodes and charging a destabilized crystal

Check id: `concilium.node_rift_crystal`

**Steps**

1. Read its research entry ("Rifts", "Destabilized Crystal") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. An aura node floats two blocks up, four blocks ahead of you; the thaumometer is in your hotbar. Break the node. Stand back and watch for a minute; then scan the rift.
3. Next: A Vis Condenser stands ahead on the right and a stone wall on the left; you have three crystals and essentia crystals of aer and ignis. Place a crystal on the ground, on the wall and on the condenser. Right-click them with essentia crystals.

**Expect**

- [ ] A rift opens where the node was (sized by the node's vis, up to 80) and grows slowly.
- [ ] Every 15 seconds or so it may lash out: magic arcs at whatever is near, primal orbs, charged wisps, a swarm of mind spiders, or it feeds on your warp and grows.
- [ ] Scanning it (or any flux rift) reveals the Rifts research. When it closes it leaves taint fibres, flux gas and goo around.
- [ ] It grows out of the face you placed it on and takes the colour of the first aspect you feed it; more of that aspect charges it, others are refused.
- [ ] Breaking it gives nothing back (as the original).

<sub>Already covered by automated pack tests: `spatial_rift`, `condenser_and_crystal`</sub>

## 30. Vis Conductor

Check id: `concilium.vis_conductor`

**Steps**

1. Read its research entry ("Vis Conductor Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Charged crystals stand ahead (two aer on the left and right, one auram further right), a cow stands still further on, and a small rift hangs beyond it. Your wand has the Vis Conductor; the Dematerialization focus is in your hotbar.
3. Channel (hold right-click) at a charged crystal, then let go looking at empty sky.
4. Recharge another crystal (essentia crystals are in your hotbar); with the Dematerialization focus socketed, channel and let go at the cow; then with the auram crystal, at the rift.

**Expect**

- [ ] Arcs in the crystal's colour run from it to you while it drains.
- [ ] Let go at nothing: the crystal bursts in a small explosion.
- [ ] With Dematerialization: the mob takes damage for what you drained; an auram charge shrinks the rift, and draining enough closes it quietly.

## 31. Wisp Launcher

Check id: `concilium.wisp_launcher`

**Steps**

1. Your wand has the Vis Conductor already set to the Wisp Launcher upgrade; a wisp hovers ahead and two cows stand still further on. Channel at the wisp until it reaches you, then let go towards the cows.

**Expect**

- [ ] The wisp is reeled in, then flung where you look as a charged wisp that hurts everything within 4 blocks of its path and leaves them vis-exhausted.

## 32. Vis Condenser discharge

Check id: `concilium.vis_condenser`

**Steps**

1. Read its research entry ("Vis Condenser") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Vis Condenser with a charged aer crystal on it stands ahead, a lever beside it on the right and a still pig four blocks to its left. Flip the lever (redstone strength 15; a redstone block is in your hotbar for other strengths).

**Expect**

- [ ] A bolt in the crystal's colour shoots out of the opposite side as far as the signal is strong, hitting harder the shorter it is; up to 16 charge is spent.

## 33. The Hex and taming a flux rift with a lesser hex

Check id: `concilium.hex`

**Steps**

1. Read its research entry ("Hex Of Predictability") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A formed Hex with its chained rift lies four blocks ahead (a jarred node on its centre), and a powered condenser with a charged crystal stands to the right within 8 blocks. Watch the rings turn.
3. Throw a stick onto the hex (sticks and void slag are in your hotbar).
4. Next: A flux rift hangs above a Barrier Stone ringed with eight ancient stone, three blocks ahead; your wand is full of vis. Strike the Barrier Stone with the wand (50 ordo, 50 terra).

**Expect**

- [ ] The ring becomes the Hex: a plate with three rune rings. The node unseals into a young rift above it; the rings start turning and the runes glow purple.
- [ ] The essentia goes into the hex; with the stick on it, arcs run to the stick and void slag spatters out for about 20 seconds.
- [ ] Void slag thrown near keeps it running; left long enough it overheats and the rift collapses. Breaking any hex block turns it back into stone and bedrock.
- [ ] The rift above is calmed: it stops growing, shrinks to size 25 if larger, makes no flux events, and closes harmlessly. It transmutes too, for twice the essentia.

<sub>Already covered by automated pack tests: `hex_transmutation`, `lesser_hex`</sub>

## 34. Primal orb: summoned versus thrown

Check id: `concilium.primal_orb`

**Steps**

1. A rift hangs nine blocks ahead; wait for it to throw orbs and watch them. Then run /summon thaumicconcilium:primal_orb ~ ~1 ~3 and watch.

**Expect**

- [ ] The summoned motionless orb bursts at once; orbs a rift throws fly and burst on impact. Neither looks wrong (the original's sound and particles are the reference).

<sub>Already covered by automated pack tests: `spatial_rift`</sub>

## 35. Reflection focus

Check id: `concilium.reflection`

**Steps**

1. Read its research entry ("Reflection Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the eldritch bracelet (Reflection) and have 30 levels. Hold V for a few seconds.

**Expect**

- [ ] 10 experience points a tick become 1 temporary warp a tick (more with potency).
- [ ] The bracelet's vis doesn't go down: Reflection refunds what it charges.

## 36. Warp Extraction focus

Check id: `concilium.warp_extraction`

**Steps**

1. Read its research entry ("Warp Extraction Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the ring and an eldritch bracelet with Reflection and hold a wand with Warp Extraction; two cows stand ahead. Hold V (Reflection) first to build up temporary warp.
3. Then with the wand: sneak + cast, a charge appears; sneak + cast again near it, it vanishes. Cast and hold while looking at the cows; let go.

**Expect**

- [ ] Holding draws the charge you look at in front of you; letting go hurls it.
- [ ] Each creature it touches costs a point of temporary warp a tick; damage comes from permanent warp only.

## 37. Alchemist's Spree focus

Check id: `concilium.alchemist_spree`

**Steps**

1. Read its research entry ("Alchemist Spree Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are already wearing the ring, hold a wand with Alchemist's Spree, and have snowballs, eggs, clear water bottles and fire charges. Channel Spree, and throw the items straight up (or have a friend throw them at you).

**Expect**

- [ ] Snowball → frost shard along your aim; egg → a taint spider; clear water bottle → thick taint bottle; fire charge → explosive orb that only sets fires with Primal Essence.

## 38. Taint Animation focus

Check id: `concilium.taint_animation`

**Steps**

1. Read its research entry ("Taint Animation Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold a wand with Taint Animation, in front of a strip of taint soil with fibres and flux gas, and a cow beyond it. Channel Taint Animation looking at the cow.
3. Tainted mobs for the sneak part are not staged: bring some (taint crawlers, spawn eggs) if you want to test it.

**Expect**

- [ ] Every half second a fibre wears down a stage (or vanishes) into a taintacle, or gas becomes a swarm, aimed at what you look at.
- [ ] Sneaking: tainted mobs within 16 go for your target, with Strength from your permanent warp (up to 200) at potency.

## 39. Ring of Blustering Light

Check id: `concilium.ring_blustering`

**Steps**

1. Read its research entry ("Ring Of Blustering Light") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold the ring, a wand with Spotlight, loose Alchemist's Spree and Warp Extraction foci, and a shield. Cast each focus (socket the loose ones into the wand) with and without the ring worn (Curios ring slot); hold the shield in the off hand.

**Expect**

- [ ] The ring shows in the slot and fills a hotbar wand with vis, and shields; the three foci refuse without it (action-bar message, no vis spent).

## 40. Ethereal Manipulator focus

Check id: `concilium.ethereal_manipulator`

**Steps**

1. Read its research entry ("Ethereal Manipulator Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold a wand with the Ethereal Manipulator, a bow and arrows; a diamond lies on the ground ahead. Channel the focus at the diamond, then at an arrow you shoot; scroll the mouse wheel while channelling.

**Expect**

- [ ] It holds the item or projectile in front of you; the wheel sets the distance 1 to 16 and does not change your hotbar slot while channelling.

## 41. Scribing focus on a second player

Check id: `concilium.scribing`

**Steps**

1. Read its research entry ("Scribing Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold a wand with the Scribing focus. This check needs a second player (open to LAN) wearing runic gear: channel at them.

**Expect**

- [ ] Their Thaumaturge runic shield refills, never past what their gear grants; runes stream from you to them.

## 42. Foundation foci: cost and fire rate

Check id: `concilium.foundation_foci`

**Steps**

1. Read its research entry ("Signal Focus", "Impulse Focus", "Positive Burst Focus", "Cooling Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold four wands: Signal, Impulse, Positive Burst and Cooling. Cast each; watch the vis bar and the Cooling flurry's fire rate.
3. Open the research book and check the Thaumic Concilium tab shows these four entries and their parts (staging has already granted them, so the unlock order is not tested here).

**Expect**

- [ ] Each focus costs a sensible amount of vis (report any that feel off); the flurry fires about every 4 + complexity/8 ticks; the Thaumic Concilium tab opens after Base Auromancy and gates its parts.

## 43. Valet Seal: speaking a phrase to lever, door, lamp and bell

Check id: `concilium.valet_phrase`

**Steps**

1. Read its research entry ("Valet Seal") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a lever with a Valet seal on it; the seal's phrase paper already says "open sesame".
3. Place the golem from your hotbar and give it the Use settings it needs (open the seal with the golem bell; right click, not into air).
4. Stand within 32 blocks and type exactly: open sesame
5. Next: You stand between a door with a Valet seal on it (phrase "open sesame") and a redstone lamp with a button in front of it, no seal yet. An anvil is ahead of you; the kit has a seal, two papers, a golem and 10 levels.
6. Name a paper "light" in the anvil, put a Valet seal on the lamp's button (open it with the golem bell, paper in the second filter slot), place the golem.
7. Say each phrase in turn.
8. Next: You stand in front of a lever whose Valet seal is set to "open sesame"; the golem is in your hotbar (place it and give it its Use settings).
9. Say "Open Sesame", "open  sesame" (two spaces), "open sesame!" and "open".
10. Then say "open sesame".
11. Next: You stand in front of a lever with a Valet seal ("open sesame"), an anvil on your right and a plain stone block on your left; the kit has the golem, two golem bells and 10 levels. Place the golem.
12. Rename the golem bell "open sesame" in the anvil.
13. Ring it in the air (aim at no seal, not sneaking). Then ring it aimed at the plain stone block.
14. Ring the second, unnamed bell, and ring the renamed bell while aiming at the seal (it opens the seal GUI) and while sneaking.

**Expect**

- [ ] The golem walks to the lever and flips it once, then goes back to what it was doing.
- [ ] Your message still shows in chat as normal.
- [ ] Judge this call: how readable the arming is (the only cue is the golem moving).
- [ ] The door opens or closes on its phrase; the button presses on its phrase; the other does not react.
- [ ] Judge this call: one click per phrase (it never repeats on its own).
- [ ] Case, spacing and punctuation count: none of the near misses fires; the exact phrase does.
- [ ] Judge this call: exact match as the original (user decision).
- [ ] Ringing the renamed bell in the air or at a seal-less block acts like saying the phrase: the golem goes and uses the lever. The bell still rings.
- [ ] An unnamed bell does nothing extra; aiming at a seal or sneaking keeps Thaumaturge's own gestures (GUI, remove) and does not trigger the Valet.
- [ ] Judge this call: the bell as a quiet trigger.

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`, `valet_armed_click_toggles_a_lever_once`, `valet_bell_arms_like_the_phrase`</sub>

## 44. Valet Seal: reach, several seals and a second player

Check id: `concilium.valet_reach`

**Steps**

1. Read its research entry ("Valet Seal") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand between two levers, each with a Valet seal set to "open sesame"; two golems are in your hotbar (use one or both, with Use settings).
3. Say the phrase.
4. Next: Staged where you stand: a lever with a Valet seal ("open sesame") four blocks ahead. The golem is in your hotbar; place it and give it its Use settings.
5. Stand more than 32 blocks from the seal and say the phrase.
6. Back within range, remove the golem (or send it far away), say the phrase and wait about ten seconds.
7. Next: You stand in front of a lever with a Valet seal ("open sesame") and an anvil. Place the golem. Open the world to LAN, a friend joins (they must go to this site themselves) and stands near your seal.
8. The friend says your phrase.
9. Then the friend builds their own Valet seal with their own phrase and says it, while you stand by.

**Expect**

- [ ] Both levers are flipped, each by whichever golem takes the task.
- [ ] Judge this call: every matching seal fires (user decision).
- [ ] Out of range: nothing happens.
- [ ] No golem takes the task: the arming lapses after 200 ticks and the lever is not flipped later when a golem returns.
- [ ] Judge this call: distance measured to the seal, not the golem.
- [ ] The friend's saying your phrase does nothing: only the seal's owner arms it.
- [ ] The friend's own seal works for them and not for you.

<sub>Already covered by automated pack tests: `valet_chat_arms_exact_phrase_in_range_for_owner`, `valet_expires_unserved_and_idles_free`</sub>

## 45. Assistant Seal: jarring a pig, Order and Entropy

Check id: `concilium.assistant_seal`

**Steps**

1. Read its research entry ("Assistant Seal") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A fenced pen lies ahead with a pig and a cow inside and a stone block at its near edge. Your hotbar has the Assistant seal, golem bell, Pig blood sample, a claw golem, soul jars and a Provider seal.
3. Place the Assistant seal on the stone block, open it with the golem bell and put the Pig blood sample in one filter slot (nine slots).
4. Place the golem near the seal and supply empty soul jars (a Provider seal with jars, or have a jar in its hands).
5. Wait up to a minute or two, watching the golem.
6. Next: The pen ahead holds a full-health pig, a hurt pig and a still zombie (it is night); your hotbar has the seal, bell, Zombie blood sample, a claw golem and soul jars.
7. Place the Assistant seal on the stone block and open its GUI: read the Order and Entropy toggles. Put the Zombie sample in a filter slot and leave Entropy off, with the golem placed nearby.
8. Turn Entropy on and watch again. Turn Order on and watch with the full-health pig, then with the hurt one.
9. Try a wither or a player nearby, with samples of them if you can make one.

**Expect**

- [ ] The golem walks to the pig (not the cow), strikes it, and when the blow would kill it a soul jar holding the pig drops at the golem; the pig is gone.
- [ ] With no empty jar in reach the golem asks for one and does nothing else; a jar kit and a Provider fixes it.
- [ ] Judge this call: the walk, the hit and the jarring read clearly, and the golem does not stand idle.
- [ ] Entropy off: hostile creatures are left alone; on: the zombie is hunted and jarred.
- [ ] Order on: only weakened prey is taken; a full-health pig is ignored until it is hurt.
- [ ] Your tamed pets, players, Thaumaturge golems and bosses are never jarred.
- [ ] Judge this call: the toggle names and descriptions in the GUI read sensibly.

<sub>Already covered by automated pack tests: `assistant_hunt_filter`, `assistant_jars_when_damage_reaches_health_else_hits`, `assistant_order_and_entropy_settings`</sub>

## 46. Golem Bydlo: made in the vat, its look and riding

Check id: `concilium.golem_bydlo`

**Steps**

1. Read its research entry ("Buff Golem", "Brain Littering") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A raw Curative Vat frame (planks, glass, water, alchemical constructs and a vat matrix on top) stands four blocks ahead; you have a wand, a Thaumonomicon, Thaumaturge spawn eggs, a blood syringe and a soul jar. Form and fill the vat (see the Horizons chapter).
3. Read the Brain Littering and Buff Golem entries and their infusion pages.
4. Load a Thaumaturge (spawn one) and run the Brain Littering infusion to make a Mad Thaumaturge, then Buff Golem to make a Golem Bydlo.
5. Afterwards try the vat on the Bydlo itself.
6. Next: A Golem Bydlo stands five blocks ahead. Look at it from the front, the side and the back, in daylight and in a dark place (/time set night to try).
7. Push it or lead it to make it walk; watch the legs, arms and body.
8. Next: A Golem Bydlo stands four blocks ahead, and beyond it a one-block step and then a two-block step of stone. Right-click the Bydlo with an empty hand to mount it. Walk it over the one-block step and the two-block step. Dismount and mount again, and try with a second player on LAN.

**Expect**

- [ ] Each infusion turns the creature into the next; its name and health stay; the Bydlo has 90 health.
- [ ] The Bydlo is refused by the vat afterwards.
- [ ] Judge this call: the recipe pages and ingredients read clearly in the research UI.
- [ ] A tall iron golem with brass plates, a furnace slit on the chest, a boiler hump on the back and long gauntlets to the knee; the head sits between the shoulder plates.
- [ ] The walk swings the legs and arms in opposition, with a heave in the body; it never freezes in a T pose.
- [ ] Judge this call: proportions against the original (ours swings less wide), and the texture.
- [ ] You sit behind its shoulders and the camera feels right; the golem walks where you steer, climbs a full block while ridden, and one rider only.
- [ ] The arms are carried forward while ridden, not frozen; no model pokes through your legs.
- [ ] Judge this call: seat height, camera and steering feel.

<sub>Already covered by automated pack tests: `bydlo_chain_converts_through_the_vat_and_keeps_data`, `bydlo_vat_refusal_and_chain_inputs`, `bydlo_stats_and_vat_refusal`, `bydlo_ride_and_step_height`</sub>

## 47. Golem Bydlo: Excavation and Wrath Attraction

Check id: `concilium.bydlo_foci`

**Steps**

1. Read its research entry ("Buff Golem", "Wrath Attraction Focus") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Golem Bydlo stands four blocks ahead and a stone wall with a bedrock block in it beyond; you have a wand and an Excavation (Break) focus. Socket the focus into the wand, ride the Bydlo and left-click the stone wall, then the part with bedrock.
3. Click rapidly several times.
4. Next: A Golem Bydlo stands four blocks ahead with still pigs and zombies beyond it; your wand has the Wrath Attraction focus. Ride the Bydlo, move in among them (plus a tamed wolf or another player on LAN if you want to test sparing), and left-click the air or an enemy.

**Expect**

- [ ] A 5x5 plane of the clicked face breaks, one layer deep, dropping items; bedrock and anything a protection mod forbids stay.
- [ ] A short cooldown (about a third of a second) limits the rate; no vis is spent.
- [ ] Judge this call: the speed and the sound and look of the swing.
- [ ] Everything living around the golem takes 10 to 24 damage and is flung up a little; you, the other player, tamed pets and your allies are not hurt.
- [ ] Both arms rise in a punch pose.
- [ ] Judge this call: the damage range and the feel of the punch.

<sub>Already covered by automated pack tests: `bydlo_excavation_respects_break_event`, `bydlo_commands_read_the_focus_and_keep_the_cooldown`, `bydlo_punch_damage_range_and_friends_spared`</sub>

## 48. Vengeful Golem: finding it, taunts and dimensions

Check id: `concilium.vengeful_meeting`

**Steps**

1. It is night. A Vengeful Golem stands in a glass cage nine blocks ahead of you (it cannot see you through the glass); a spawn egg is in your hand to place another.
2. Look at it from a distance, side-on and from behind (walk round the cage), and watch it walk.
3. Next: It is night and a Vengeful Golem stands eleven blocks ahead of you in the open. Do not fight it.
4. Stay in its sight and let it attack. Watch your character and the chat. Kill the golem to end the drift (the pad is too small to walk 32 blocks away: do that on real terrain if you want to).
5. Next: Staged where you stand: only a Vengeful Golem spawn egg (use it to confirm one can exist in each dimension). Explore the Nether, then the End, for a while.
6. Check the config blacklist: add a biome id to vengefulGolem.biomeBlacklist and confirm none appears there.
7. Next: Four Vengeful Golems stand still in a row ahead of you; you have a Thaumometer, a plain sword and a Looting III sword. You have not scanned a golem yet.
8. Scan a golem with the Thaumometer, then open the Concilium bestiary entry.
9. Kill the rest, with the plain sword and with the Looting sword.

**Expect**

- [ ] A bell-carrying golem with a brain in a jar on its head shows up; it holds the golem bell in its right hand.
- [ ] Judge this call: how often it appears (weight 5, group 1 to 2, config vengefulGolem.spawnWeight), and its look and walk against the original.
- [ ] It stops at range, swings, an orb sound plays and about four in ten times a purple taunt appears in chat.
- [ ] You are enslaved: your character walks on its own, drifting toward it; you can still look around. Failing the roll (about one in five) releases you instead.
- [ ] Distance over 32 blocks or its death ends the drift.
- [ ] Judge this call: the feel of the enslavement, and the taunt text.
- [ ] It spawns in all three dimensions (user decision), at the config weight; blacklisted biomes have none.
- [ ] Judge this call: whether the Nether and End population is too much or too little.
- [ ] A page about the Vengeful Golem appears once one is scanned (the image page is skipped on purpose).
- [ ] Drops: 0 or 1 Knowledge Fragment, one more per Looting level.
- [ ] Judge this call: the page text.

<sub>Already covered by automated pack tests: `vengeful_golem_data_tag_loot_spawn_and_bestiary`, `vengeful_golem_attributes_bell_and_egg`, `vengeful_golem_enslaves_in_sight_and_releases_otherwise`, `vengeful_golem_ranged_goal_refuses_inside_one_block`</sub>

## 49. Vengeful Golem: earmuffs and wandering mobs

Check id: `concilium.vengeful_effects`

**Steps**

1. You wear a leather helmet and a Vengeful Golem stands eleven blocks ahead of you in the open. Stand in its sight for half a minute.
2. Swap the helmet for the Earmuffs (in your inventory) and stand in its sight again.
3. Next: You wear earmuffs so the golem leaves you alone. A Vengeful Golem stands ten blocks ahead with two pigs and a villager in front of it.
4. Watch the pigs and the villager.

**Expect**

- [ ] With the helmet the bell works on you as usual (enslaving, taunts in chat).
- [ ] With the Earmuffs: no enslaving, no taunt; the golem keeps trying but nothing happens.
- [ ] Most of the time (about nine in ten) the mob walks off to a random point nearby.

<sub>Already covered by automated pack tests: `earmuffs_in_tag_and_muffle_the_golem`, `vengeful_golem_never_enslaves_with_earmuffs`, `vengeful_golem_sends_mobs_wandering`</sub>

## 50. Earmuffs: craft and wear

Check id: `concilium.earmuffs`

**Steps**

1. You stand at a crafting table with leather and white wool. Craft the Earmuffs (leather band over two wool pads).
2. Wear them; look at yourself in F5 from the front and the side, and at the item in the inventory.

**Expect**

- [ ] The recipe shows in the recipe book and gives one pair.
- [ ] Two wool pads over the ears joined by a leather band over the crown; the icon reads as earmuffs; no armour bar.

<sub>Already covered by automated pack tests: `earmuffs_in_tag_and_muffle_the_golem`, `new_data_files_resolve`</sub>

## 51. Polished infusion and the Polishment Device

Check id: `concilium.polished_infusion`

**Steps**

1. You stand in front of an infusion altar for the Cooling Focus: a focus on the centre pedestal, a torch on two of the ring pedestals. A Cooling Focus is in your inventory, and creative jars of every aspect stand behind the altar.
2. Look up the Cooling Focus in the book (Thaumonomicon key): its recipe page ends with the Polished Infusion line. Hover the Cooling Focus: the tooltip shows the requirement.
3. Start the infusion on the matrix and let it finish without channelling a crystal.
4. Next: You stand in front of the Cooling Focus infusion altar (creative jars of every aspect stand behind it), with a destabilized crystal charged with 100 aversio two blocks to your right, and the Vis Conductor wand in your hand.
5. Start the infusion, aim the Vis Conductor at the crystal and keep channelling until it has given up 64 or more.
6. Keep channelling while the infusion finishes.
7. Next: A Cooling Focus and a Tight Belt are in your inventory.
8. Look at them in the inventory and at their recipes in the research book.
9. Next: A rift hangs in the air ahead of you and the Polishment Device is in your hand. Look at the rift and use the device.

**Expect**

- [ ] The infusion completes, the pedestal ends up empty and a purple message says it unravelled. Nothing is left over and nothing duplicates.
- [ ] The crystal vanishes with a shock sound, you swing, a lightning arc runs from you to the matrix and the Cooling Focus appears on the pedestal. Letting go afterwards does nothing.
- [ ] The item shows the polished tooltip and the book page shows the polished line.
- [ ] The rift disappears at once (no taint, no event); the device is not consumed.

<sub>Already covered by automated pack tests: `polishment_lookup`, `polishment_gate`</sub>

## 52. Xylography

Check id: `concilium.xylography`

**Steps**

1. Read its research entry ("Xylography") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a crafting table with a charged wand in your hand.
3. Put the wand alone in the crafting grid and take the result.

**Expect**

- [ ] The wand now says it is signed with your name.

<sub>Already covered by automated pack tests: `xylography_signs_wand`</sub>

## 53. Astral Monitor

Check id: `concilium.astral_monitor`

**Steps**

1. Read its research entry ("Astral Monitor") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a crafting table with a wand and an Astral Monitor in your inventory.
3. Craft the wand alone in the grid to sign it. Look at the Astral Monitor in the inventory, the creative tab and the research book: is its icon drawn (not a missing texture)?
4. Hold it in the main hand, then the off hand: do both hands hold it up two-handed, steady, in first and third person?
5. Sneak and use it, put the signed wand in the slot, close it. Watch the gems on the frame for ten seconds, then hover the item.
6. Try with another player holding the signed wand too (LAN).

**Expect**

- [ ] The icon is the monitor with its gems.
- [ ] The two-handed pose looks right; nothing clips the face.
- [ ] The frame gems cycle through their colours; the tooltip says "Watching" and the signed player's name.
- [ ] Constellation glyphs hover over the screen showing that player's health (and mana with Botania); the slot cannot be emptied by clicking the monitor.

## 54. Lithographer and the Lithograph HUD

Check id: `concilium.lithographer`

**Steps**

1. Read its research entry ("Lithographer") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of the bed pattern, already built: bed, thaumium block on its head, gold blocks either side of both, an alchemical construct on top. Two charged wands and two Astral Monitors are in your inventory, a crafting table is on your right and a sensus crystal with 100 floats above the construct.
3. Strike the construct with a charged wand (try both axes by rebuilding if you wish).
4. Craft each wand alone to sign it and put each in a monitor, then put both monitors in the Lithographer.
5. Put the Vis Condenser on top of the Lithographer (under the crystal), sleep in the bed and power the machine with the redstone block.
6. Next: You are already lithographed, watching yourself. Read the glyphs: health, then in Botania mana; try a dark cave and a bright day (use /time set to switch).
7. Use Coagulating Eye Drops twice.

**Expect**

- [ ] The thaumium block becomes the Lithographer; the screen opens and holds four monitors.
- [ ] After the pulse the HUD appears and the crystal loses 32.
- [ ] The glyphs are readable against bright and dark scenes and do not cover the crosshair.
- [ ] The drops switch the HUD off, then on again, costing 1 health each time.

<sub>Already covered by automated pack tests: `lithographer_build`</sub>

## 55. Astral Monitor and Lithograph HUD: the blood glyph

Check id: `concilium.astral_blood`

**Steps**

1. You are lithographed and watching yourself (Lithograph HUD on). Right-click the Weak Blood Orb once to bind it; your network is empty.
2. Raise your network with /neovitae anima-network @s set 500, then 2500, then 5000, and watch the blood glyph.
3. Hold the Astral Monitor watching yourself and read the same glyph on its screen.
4. Drop the orb (or put it in a chest) and look again.

**Expect**

- [ ] With an orb bound and no LP, the blood glyph shows its first frame (not hidden).
- [ ] It steps up a frame per tenth of the orb's maximum: 500 one frame, 2500 the middle, 5000 full. A player who never had an orb shows no blood glyph.
- [ ] The monitor shows the same frame.
- [ ] The glyph stays: the best orb you ever had sets the scale, as the original's network did.

<sub>Already covered by automated pack tests: `party_stats_blood_frames`, `blood_ceiling_remembers_the_best_orb`</sub>

## 56. Quicksilver Reactor and the Quicksilver Elemental

Check id: `concilium.quicksilver_reactor`

**Steps**

1. Read its research entry ("Quicksilver Crucible") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand between a boiling crucible full of water (left) and a Quicksilver Reactor (right), 6 blocks apart.
3. Throw quicksilver into the reactor; give the crucible aspects whose last two combine (throw in the kit items, for example the parts of a compound).
4. Power it with the redstone block, then pause it with a lever; stand a creature in the mercury; add a comparator.
5. Next: You stand beside a Quicksilver Elemental (it stands still) and a boiling crucible of water on the right.
6. Hit the elemental with fire, lava and a sword; watch its hitbox as it shrinks.
7. Throw the quicksilver from your inventory into the crucible.

**Expect**

- [ ] Every second a flow of mercury runs from the reactor to the crucible and the last two aspects become one of their compound; a lever or redstone block pauses it; creatures inside the mercury are burned; the comparator reads the reactor.
- [ ] It is immune to what the original lists, its hitbox shrinks with its size, and the crucible becomes a Quicksilver Reactor.

<sub>Already covered by automated pack tests: `quicksilver_reactor_merge`</sub>

## 57. Thaumaturge's and Warped Drums

Check id: `concilium.drums`

**Steps**

1. Read its research entry ("Thaumdrum", "Warpdrum") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Both drums and the Void Bracelet are in your inventory.
3. Hold use on the Thaumaturge's Drum, then the Warped Drum, in the main hand; watch the strike against the beat.
4. Move a drum to the off hand (main hand empty) and hold use; then hold the Void Bracelet in the main hand and hold use again.
5. Next: Both drums and the Void Bracelet are in your inventory.
6. In Options > Skin Customization set the main arm to Left. Repeat the strike in the main hand, the off hand, and the off hand with a bracelet.
7. Next: You stand on open ground with both drums.
8. Play the Thaumaturge's Drum for a minute, then the Warped Drum; count what appears.
9. Next: Nothing is staged: this check needs real terrain, so you stay where you are.
10. Without any drum, play for five minutes in an overworld forest, then a cave. Note any wisps near you and what the area is.

**Expect**

- [ ] The arm strikes in time with the bass-drum sound, in first and third person; the off hand strikes with the off arm (the bracelet's band shows on the striking wrist).
- [ ] Everything is mirrored: the same strike and sound, the right arm for the off hand, no arm clipping through the drum.
- [ ] Roughly one wisp of a random primal every 1.5 seconds (up to 16 within 64 blocks); the Warped Drum calls a harmless mind spider every half second (up to 16 within 32).
- [ ] No wisps follow you around. If some do, report where: the pack test found 16 wisps near its test player (source unknown).

<sub>Already covered by automated pack tests: `drum_offhand`</sub>

## 58. Drum stance: casting while drumming

Check id: `concilium.drum_stance`

**Steps**

1. Read its research entry ("Thaumdrum") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand with three cows in a line ahead of you at 2, 4 and 6 blocks (they stand still). The Void Bracelet with the QA Aura > Frost focus is in slot 1 and a drum in slot 2.
3. Put the bracelet in the main hand and the drum in the off hand. Press V with the drum held silent; note the vis and which cows are frozen.
4. Hold use on the drum so it plays, and press V again; compare.
5. Next: You stand with the Signal focus bracelet in slot 1 and a drum in slot 2, a cow six blocks ahead.
6. In the stance (bracelet main hand, drum off hand) press V, drum silent then played.
7. Next: You stand with the Taint Animation bracelet in slot 1, a drum in slot 2 and a loose Positive Burst focus (slot 3). A zombie stands still five blocks behind you.
8. With the drum in the off hand press and hold V (a taint area with a tainted creature is not staged: go to one if you want to see raised creatures; command mode if you set it).
9. Then socket the Positive Burst focus in the bracelet with another player nearby, facing a different way each time.

**Expect**

- [ ] Silent: a plain wand's vis cost and cooldown, an aura of 3 blocks. Played: 1.5 times the vis and the aura reaches 1.5 times as far (4.5 blocks). V never interrupts the drumming.
- [ ] Refused: the action-bar message "You cannot aim while drumming", the fail sound, no vis spent, no cooldown, and the drumming goes on.
- [ ] Taint Animation pulses (never picking what you look at: command goes for the nearest foe, raised creatures choose their own targets). Positive Burst releases its orbs straight up whichever way you face, and they find the other player.

<sub>Already covered by automated pack tests: `bracelet_drum_stance`, `bracelet_drum_taint`</sub>

## 59. Crimson Paladin, Archer and Ranger

Check id: `concilium.crimson_mobs`

**Steps**

1. You are in survival with iron armour, a shield, a diamond sword, a bow and golden apples; the three spawn eggs are in your hotbar. Use each spawn egg on the ground, one at a time, and fight it. Fight the Archer from open ground and (dig down or build a roof) in the dark; fight the Ranger at range and up close.
2. Check what they drop on death.
3. Next: You are in creative in daylight, facing a Paladin, an Archer and a Ranger standing still in a row 6 blocks ahead. Look at each from the front, back and side (fly around them) and compare with the harness shots; at dusk (/time set night) look again.
4. Next: This check needs real terrain, so you are not moved. You are armed and it is night. Explore, or spend a night in a spot where Thaumaturge knights spawn, and watch what appears. Also look for a Ranger on its own in the open and in lit areas.

**Expect**

- [ ] Paladin: keeps its distance, casts at you from 8+ blocks away (orb or shackles) and melees when close. Archer: strafes and shoots primal arrows, Power and Flame from its bow pass on. Ranger: sprays shard powder.
- [ ] All three are fair for the pack's level, do not stand still or jitter, and drop gear and loot sensibly.
- [ ] The Archer and Ranger have no bow-draw pose yet (known).
- [ ] Red-robed bodies with Thaumaturge armour, readable at range. The Paladin's hood and staff show; nothing is magenta, invisible or stretched.
- [ ] Known: the original wore black plate where ours wears red robes; judge whether the look is acceptable.
- [ ] Some fresh Thaumaturge knight spawns are replaced by Crimson Paladins at a modest rate (never every one).
- [ ] Rangers turn up naturally now and then, not in swarms and not in lit caves.
- [ ] Portal minions are not turned into Paladins.

<sub>Already covered by automated pack tests: `crimson_stats_and_gear`, `crimson_drops`, `crimson_paladin_spells`, `crimson_archer_fires_primal_arrow`, `crimson_ranger_sprays_shard_powder`, `archer_damage_multiplier`, `crimson_knight_replacement_rate`, `crimson_ranger_spawn_modifier`</sub>

## 60. Crimson outfits

Check id: `concilium.crimson_outfits`

**Steps**

1. You stand facing five rows of frozen mobs: 8 Crimson Paladins, 8 Archers, 8 Rangers, then 4 host Cultist Knights and 4 Clerics (summoned, not from eggs; eggs are on your hotbar if you want to spawn more). Look at each from the front and the back.
2. Next: You stand in front of a Crimson Avanpost tower with its three guard archers on top (frozen). Look at their outfits.
3. Behind you a Lesser Crimson Portal is open: look at the cultists that arrive.

**Expect**

- [ ] Each of our three mobs comes in several looks: roughly half in Thaumaturge crimson armour, half in Armor Series gear (Paladin: gilded helm, praetor, knight, paladin helm; Archer: cleric robes or crossbowman; Ranger: ranger set or madcap). All wear the host cultist face. The Archer carries a quiver on its back and a bow; the Paladin a wand.
- [ ] The host knights and clerics look exactly as before (Thaumaturge armour only, none of the Armor Series gear).
- [ ] The tower guards do not all look alike: they wear outfits from the Archer table (cleric robes or crossbowman).
- [ ] Raid and portal Paladins, Archers and Rangers show the same mix; knights and clerics from the portal stay host-looking.

<sub>Already covered by automated pack tests: `outfit_tables_resolve_and_split`, `our_cult_mobs_wear_table_outfits`, `host_cultists_and_pontifex_unchanged`</sub>

## 61. Cultist tower in the wild

Check id: `concilium.cultist_tower`

**Steps**

1. This check needs real terrain, so you are not moved. You are armed in survival. Explore a new world area (or a fresh seed) until you find a Crimson cultist tower; look at it from outside and inside. Check its banners, fight the guards and open the chest.

**Expect**

- [ ] The tower is found now and then, not too often, sits flat on the ground and faces sensibly.
- [ ] Banners show as intended (hanging on the walls, not broken or invisible); archers stand guard and do not despawn.
- [ ] The chest holds fair loot.

<sub>Already covered by automated pack tests: `tower_template_contents`, `tower_ground_rule`, `tower_loot_table`, `tower_placement_spawns_persistent_archers`</sub>

## 62. Gilded Crimson Helm

Check id: `concilium.crimson_helm`

**Steps**

1. You are in creative already wearing the Gilded Crimson Helm, with a Paladin standing 4 blocks ahead to compare its helm. Look at yourself in third person (F5, front and back), in first person with the head visible.

**Expect**

- [ ] The helm and its fin sit properly on the head, with no clipping into the face or body.
- [ ] Fine in first person, and the Paladin's gilded helm variant matches.

<sub>Already covered by automated pack tests: `crimson_paladin_gilded_helm`</sub>

## 63. Ethereal Shackles and ethereal no-clip

Check id: `concilium.ethereal_shackles`

**Steps**

1. You are in survival with armour, a shield and stone. A Crimson Paladin stands 11 blocks ahead and will cast at you. Let it hit you with its shackles. While chained, try to place and break blocks, use items, swing at it and open doors. Wait it out (about 5 seconds).
2. Next: A Crimson Paladin stands 11 blocks ahead and will cast at you; you are armed in survival (the robe is in your hotbar).
3. Watch the shackles fly, then look at your own hand while chained, and wait it out (5 seconds).
4. Wear the robe and turn the toggle on (L): the chained hand shows for a moment there too.
5. Next: You wear the full Pontifex Robe in survival; a stone wall stands 5 blocks ahead, a stone ceiling 6 blocks overhead and a pig beside you. Open the world to LAN and let a second player join (it is not staged for them). Press L (or run /thaumicconcilium qa ethereal on).
6. Fly into and through the stone wall, up through the ceiling, and down below the floor. Sneak to descend. The second player watches you the whole time.
7. Try breaking a block, hitting the pig and using an item while ethereal, then /thaumicconcilium qa flesh 0 and check your health bar. Step off the pad edge into the void.

**Expect**

- [ ] You cannot use, place, break, interact or attack for about 100 ticks, then it lifts cleanly. Movement is still free.
- [ ] Other mobs hit by it are slowed instead.
- [ ] There is no visual effect for the chain (known gap): judge whether it is readable that you are chained at all.
- [ ] The thrown shackles spin as they fly. While chained your hand is the shackled arm with a chain, blue haze rising as the timer runs out, and you cannot break, place or attack.
- [ ] The hand returns cleanly when the chain ends, with no leftover or flicker.
- [ ] You pass through walls with no stutter or rubber-banding for you, and the second player sees you pass through walls too (no snapping back, no being pushed out).
- [ ] No block overlay when your head is inside stone. Damage and healing do nothing. Each action you take gains flesh and the maximum hearts shrink.
- [ ] Falling into the void does not hurt you: you can fall forever (deliberate, a PvP blink). Switching the robe toggle off ends the state.

<sub>Already covered by automated pack tests: `crimson_paladin_spells`, `chained_blocks_and_counts_down`, `ethereal_flight_and_idle`, `ethereal_damage_and_heal`, `flesh_gain_rules`, `flesh_max_health_modifier`, `respawn_rule`, `robe_toggle_on_state`, `state_round_trip`</sub>

## 64. Lesser Crimson Portal and its boss

Check id: `concilium.crimson_portal`

**Steps**

1. Read its research entry ("Crimson Pontifex") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Lesser Crimson Portal has just been placed 7 blocks ahead of you, and you are armed in survival. Stand back and watch it for a few minutes without killing the minions at first, then fight them.
3. Hit the portal to see it flicker.
4. Next: A chained rift over a hex stands 5 blocks ahead, the research is granted and you hold two Crimson Rites. Throw one Crimson Rites into the rift by hand (Q while facing it).
5. Let the collapse finish and see what appears. Then let the resulting portal run to stage 13, or use /thaumicconcilium qa portal ~ ~ ~7 boss to skip ahead.

**Expect**

- [ ] The portal opens from a slit to a full oval over a short time (ours is slower and red; the reference was violet), then sends Crimson minions in waves with growing intervals.
- [ ] Waves arrive at a pace you can handle and the portal does not spam.
- [ ] Hits visibly register on the portal.
- [ ] The rift eats the Rites, turns interdimensional and collapses at once, and a Lesser Crimson Portal opens where it was. Without the research nothing happens.
- [ ] At stage 13 the portal kills itself and the Crimson Pontifex arrives.

<sub>Already covered by automated pack tests: `portal_stage_functions`, `portal_stats_and_spawn`, `rift_route_sets_boss_flag`, `portal_boss_at_stage_13`</sub>

## 65. The Crimson Pontifex: fight, drops and loot

Check id: `concilium.pontifex`

**Steps**

1. Read its research entry ("Crimson Pontifex") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. The Crimson Pontifex stands 10 blocks ahead and you are armed in survival. Look at the top of the screen and the sky while near it. Back away to the edge of the pad. Kill it.
3. Next: The Crimson Pontifex stands 10 blocks ahead and you are armed in survival. Fight it until it enslaves you. Try to resist, look around, and see how long it lasts and whether you can break out.
4. Next: The Crimson Pontifex stands 10 blocks ahead; you hold a sword, bow, arrows, primal arrows and a wand with the Signal focus. Hit it with the sword, arrows, the wand and primal arrows; take its attacks.
5. Next: You are in creative with a diamond sword and the Pontifex stands 10 blocks ahead. Kill it and collect the drops. Open the loot bag. Press Again to kill a few more and see the spread.
6. Next: You stand in front of 18 frozen crimson mobs (six each of Paladin, Archer and Ranger) and a frozen Crimson Pontifex, with a diamond sword. Kill the grunts and watch their armour drops, then look at the Pontifex.

**Expect**

- [ ] A boss bar shows with the sky darkened while it fights, and returns to normal when it is dead or you are far away.
- [ ] You are walked toward it against your will; the pull is clear and readable but not nauseating, the camera stays usable and it ends predictably.
- [ ] In multiplayer (LAN) other players see the walk smoothly.
- [ ] Damage is split as designed (a share lands as normal damage, the rest is reduced) so it takes a while but is killable in a fair fight.
- [ ] Its attacks are readable and dodgeable and not overwhelming.
- [ ] It drops a Thaumaturge rare loot bag and, by chance, its own gear. The bag opens with its contents.
- [ ] Research hint notes appear for the right players.
- [ ] Armour drops are rare (about one piece in twenty per slot, the host cultist rate), and Armor Series pieces can drop.
- [ ] The Pontifex still wears its own robe and nothing from Armor Series.

<sub>Already covered by automated pack tests: `pontifex_stats_bar_and_loot`, `enslave_flag`, `pontifex_damage_split`, `pontifex_attack_rolls`, `pontifex_drop_odds`, `pontifex_wears_his_gear`, `notes_unlock_research`, `host_cultists_and_pontifex_unchanged`</sub>

## 66. Crimson Spells: the six symbology spells

Check id: `concilium.crimson_spells`

**Steps**

1. The kit gives you an Ent Twig, a full infernal infusion and the Crimson Spells note (the Pontifex drops it). Complete the research "Crimson Spells" and read it: judge clarity, typos, and whether it explains the feature.
2. Open the remake's symbology drawing with the Ent Twig and draw each stroke from the research page: Incarcerous, the arrow, the anti-arthropod and anti-undead bolts, the blinding curse.
3. Draw Trup Ehsolvi's long stroke (five cells down from the start): the cursor must reach the fifth cell.
4. Cast at a zombie, a spider and a cow; then change infusion (/witchery infusion set @s witchery:light, then witchery:overworld and witchery:otherwhere) and cast again.
5. Log out and back in, then check the six spells are still known.

**Expect**

- [ ] Finishing the research teaches all six spells (the remake's spell list shows them). Each costs 600 charge, the long anti-undead stroke 1200.
- [ ] Incarcerous throws Ethereal Shackles; the arrow is a critical arrow; the bolts strike only arthropods or only undead (the long stroke harder); the curse blinds.
- [ ] The infusion changes each spell as its research text says. The long stroke can be drawn on the remake's screen.

<sub>Already covered by automated pack tests: `registered_with_paths`, `research_teaches_all_five`, `incarcerous_by_infusion`, `arrow_damage_by_infusion`, `bolts_hit_only_their_kind`, `blind_by_infusion`, `note_and_entry`</sub>

## 67. Crimson Annales

Check id: `concilium.crimson_annales`

**Steps**

1. Read its research entry ("Crimson Annales") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You hold the Crimson Annales and have no research. Use it now: you should get the unclear message. Then press this quest's "Crimson Rites research" reward button (or grant yourself thaumaturge:crimson_rites) and use it again; use it a second time.
3. Five chests of the dungeon, mineshaft, desert pyramid, jungle temple and stronghold loot tables stand 4 blocks ahead: open them, and press Again to re-roll them a few times.

**Expect**

- [ ] Without the research you get a dark purple 'meaning remains unclear' message and nothing is consumed. With it the research completes with the learn sound; a second use does nothing new.
- [ ] The Annales turns up rarely in those chests (about as rare as a loot-bag drop, not common).

<sub>Already covered by automated pack tests: `annales_use`, `annales_loot_entries`</sub>

## 68. Pontifex Hammer

Check id: `concilium.pontifex_hammer`

**Steps**

1. Read its research entry ("Pontifex Hammer") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are hurt a little and hold the Pontifex Hammer, with cows and a pig near you. Hold the hammer (right-click) near them and hit them. Look at it held in first and third person, off hand too.

**Expect**

- [ ] Life drains from nearby mobs to you while held, with particles flowing to you, and you are healed.
- [ ] The hammer pose is a block-style hold. Known: third person is smaller and tilted compared to the original; judge acceptability.

<sub>Already covered by automated pack tests: `hammer_life_steal`</sub>

## 69. Pontifex Robe

Check id: `concilium.pontifex_robe`

**Steps**

1. Read its research entry ("Pontifex Robe") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand beside a crafting table with the four robe pieces and dyes in your hotbar; Thaumaturge cultists wait 11 blocks ahead. Dye the four robe pieces in a crafting grid. Wear the full set, press L, then let the cultists see you with it on and off.
3. Wear only part of the set and press L.

**Expect**

- [ ] The robe takes dye on its base layer with the overlay unchanged; the dyed inventory icon matches.
- [ ] L toggles the form with a clear indication; while on, cultists and Crimson mobs drop aggro on you, while off they attack as normal. A partial set does nothing.
- [ ] The cloth flaps while walking, the helm reveals nodes like goggles, and the look matches the reference.

<sub>Already covered by automated pack tests: `robe_dye_result`, `robe_toggle_state`, `robe_drops_cultist_aggro`</sub>

## 70. Arcane Levitator

Check id: `concilium.arcane_levitator`

**Steps**

1. Read its research entry ("Arcane Levitator") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A single levitator stands ahead to the left and a column of six ahead to the right, with a lever beside it; you hold more levitators, stone, levers and redstone blocks. Stand on the single one: judge the lift, jitter at the top, and whether the item and the pig rise too.
3. Stand on the column of six and see the height. Switch it with the lever (or a redstone block), then back. Sneak while falling onto it from height.
4. Place a stone block in the column and check the lift stops and starts as it changes.

**Expect**

- [ ] You rise smoothly with no jerk or jitter at the top; items and mobs lift too. Boats and minecarts are not lifted (known).
- [ ] Each stacked levitator lengthens the column. Redstone power turns it off and it resumes when unpowered.
- [ ] Sneaking dampens your fall onto it.
- [ ] Under a ceiling you hover below it rather than clipping in.

<sub>Already covered by automated pack tests: `levitator_lifts_and_stops`, `levitator_stack_height`, `levitator_redstone_off`, `levitator_sneak_damps_fall`, `levitator_recipe_output`, `levitator_cache_follows_neighbours`</sub>

## 71. Crimson Dagger: raise, stab, bleed and self-cut

Check id: `concilium.crimson_dagger`

**Steps**

1. Read its research entry ("Crimson Initiation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear iron armour with a shield and hold the dagger; Death Gaze is on you. A Paladin, an Archer, a Ranger and a Thaumaturge Knight stand 8 blocks ahead (they will advance; the Pontifex spawn egg is in your hotbar).
3. Right-click the dagger: a short raise (0.75 s). Hold it raised, looking at each mob and then the Pontifex if you spawn it.
4. Release after a complete raise and stab straight away with left-click. Try stabbing again straight after, and a third time inside a second.
5. Note how the raise, the point and the stab read in first and third person.
6. Next: You hold the dagger and a diamond sword; three Crimson Archers that stand still and a pig are 4 blocks ahead. Stab the left Archer once, then twice more inside the 3-second window. Watch its health and the effect icon. Let it bleed out, and kill the middle one by a stab.
7. Hit the right Archer with the sword to the death, and the pig with the dagger.
8. Next: You hold the dagger and an Ara Vitae stands 4 blocks ahead. Open it to see its LP, then sneak + right-click with the dagger several times. Then walk more than 8 blocks away (to the pad edge) and try the same.
9. Next: You hold the dagger and a diamond sword; two zombies that stand still are 5 blocks ahead. With Neo Vitae in the pack, stab one and hit the other with the sword and compare the hit and the bleed message. (No Neo Vitae-specific mob is staged: swap in one by hand if you have one.)

**Expect**

- [ ] The raise feels quick but deliberate. Knights, Clerics and Archers freeze in place and stop attacking while the gaze holds them; Paladins and Rangers are slowed; the Pontifex is unaffected.
- [ ] The stab follows the release within a beat and hits fast for small damage. Spamming has an obvious rhythm (the raise is the stab's cooldown).
- [ ] Animation: the poses read clearly and and read the same in first and third person.
- [ ] Each stab adds a counter up to 3; at the window's end the target takes 1 damage per counter, one burst per window, not a drip.
- [ ] A cultist killed by the dagger or by the bleed drops exactly 1 Crimson Blood. A sword kill or the pig drops none.
- [ ] Each cut costs 1 health point and adds LP at Neo Vitae's own self-sacrifice rate, with a short cooldown. Out of range it only shows an action-bar hint.
- [ ] The hit and the bleed read as Neo Vitae's sacrifice damage (death message; it ignores armour and shields and knocks nothing back). Damage scales with the swing cooldown and nothing sweeps or crits.

<sub>Already covered by automated pack tests: `trunk_dagger_data`, `trunk_raise_stun_slow_tiers`, `trunk_bleed_requires_raise`, `trunk_bleed_stacks_and_window`, `trunk_blood_from_bleed_kill`, `trunk_blood_from_dagger_kill_only`, `trunk_self_cut_gate`, `trunk_dagger_hit_damage_type`</sub>

## 72. Flesh Crucible

Check id: `concilium.flesh_crucible`

**Steps**

1. Read its research entry ("Flesh Crucible") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A Flesh Crucible stands 3 blocks ahead and you hold Mad Thaumaturge, pig and zombie spawn eggs; you have flesh 0. Stand in the crucible with flesh 0: nothing happens.
3. Give yourself flesh (/thaumicconcilium qa flesh 10), then stand in the empty crucible: nothing. Spawn a Mad Thaumaturge beside it and push or lead it into the crucible to smelt it: it vanishes, the block stays a Flesh Crucible and its store gains 2 (up to 64).
4. Stand in the filled crucible with flesh: each tick sips 1. Also drop a pig and a zombie into an empty crucible.
5. Next: You have the Material Peeler and Quicksilver Crucible research, and the whole Flesh Crucible infusion kit: three motes, the Quicksilver Reactor (the catalyst), a Nether Shard, three Crimson Plating and Bright Nitor.
6. Build an infusion altar yourself (the pad is empty) and set up the Flesh Crucible infusion from the research page.

**Expect**

- [ ] If a store can be had: while you have flesh and the store has aspect, every tick costs 1 flesh and 1 aspect with a gore sound, and your health bar regrows as the flesh falls.
- [ ] A smelt leaves the Flesh Crucible in place with 2 more aspect (faithful, checked in the 1.7.10 game); it never turns into a reactor. Other creatures take 1 damage about twice a second. A powered crucible does nothing.
- [ ] The infusion accepts the three motes with the other components and makes a Flesh Crucible; nothing else blocks it.

<sub>Already covered by automated pack tests: `crucible_sip`, `crucible_smelt_and_cap`, `crucible_burns_others`, `crucible_recipe_present`, `trunk_smelt_fills_and_stays`, `trunk_sip_every_tick`, `trunk_damage_once_per_ten_ticks`, `flesh_crucible_needs_only_motes_and_its_research`</sub>

## 73. Material Peeler

Check id: `concilium.material_peeler`

**Steps**

1. Read its research entry ("Material Peeler") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A chained rift over a hex stands 5 blocks ahead; you hold Primordial Life and the robe pieces. Throw one Primordial Life into the rift by hand, then wait for the rift to collapse.
3. Walk into the Peeler; then wear the full Pontifex Robe with the toggle on and walk into it again.
4. Break one hex block under it, and wait.
5. Next: A Peeler of Matter hangs above a hex 6 blocks ahead, standing in for the real summon. Look at it from close and far, against sky, a cave wall (dig one) and at dusk (/time set night). Walk around it. If you use Iris, try a shader pack as well.

**Expect**

- [ ] The Peeler appears where the rift collapses, two blocks above the hex, and stays put, solid. An ambient sound plays now and then.
- [ ] Touching it toggles you ethereal with nausea about every second; with the robe toggle on you are not affected. With the hex broken it bursts, tainting the ground around it.
- [ ] A pale halo wraps the starry cube, near white-blue over daylight sky; the core is dark with stars. The glow is smooth (it has no glitter, by decision).
- [ ] No flicker, no square edges, and nothing breaks under a shader pack.

<sub>Already covered by automated pack tests: `bursts_without_hex`, `survives_above_hex`, `touch_flips_ethereal`, `primordial_life_route`, `note_resolves_to_research`</sub>

## 74. Crimson Raid spell and Crimson Initiation

Check id: `concilium.crimson_raid_spell`

**Steps**

1. Read its research entry ("Crimson Raid") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You wear the full Pontifex Robe; a wand, two blank foci, the dagger and a stick are in your hotbar; a focal manipulator stands ahead to the right and two still Mad Thaumaturges ahead to the left. In the manipulator, inscribe a focus with the Crimson Raid part (complexity 22, so it needs an advanced focus or better: use the best one the manipulator accepts). Cast it at a block, then cast again at once, then with one robe piece removed.
3. Stand clear and watch the portal and its cultists. Wait for it to end (about 20 seconds).
4. Initiation: in the full robe, right-click a Mad Thaumaturge with the dagger several times, with the stick, and with an empty hand.

**Expect**

- [ ] A Lesser Crimson Portal opens at the impact point and its cultists attack everyone but you; the second cast does nothing while the first portal lives; a partial robe does nothing but spend the cast. The portal vanishes quietly after about 20 seconds.
- [ ] The dagger converts a Mad Thaumaturge into a Crimson Knight, Cleric or Paladin (roughly a third each), equipped. The stick and the empty hand do not.

<sub>Already covered by automated pack tests: `raid_needs_robe_and_one_portal`, `raid_portal_despawns`, `initiation_needs_blade_and_robe`</sub>

## 75. The Offertory: the chain, helpers, the Yank and the snap raid

Check id: `concilium.offertory`

**Steps**

1. Read its research entry ("Crimson Initiation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. An infusion altar stands 7 blocks ahead: matrix over a centre pedestal, ring of pedestals around it. The Crimson Rites, a zombie brain, 2 tallow, a phial, a bone, a void sword and rotten flesh are in your hotbar; creative jars of every aspect stand behind the altar and supply the essentia it needs (humanus, ordo, vinculum). Put the Rites in the centre and a ring of brain, tallow x2, phial, bone and void sword on the pedestals. Do not put any offering out yet.
3. Right-click the matrix to begin. Watch the chain, your health and the action bar. Within the first 40 ticks keep rotten flesh ready; when the matrix demands an offering, place it on a free pedestal in the ring and keep going.
4. Run it again and miss one demand on purpose; then again, and let your health fall to the floor; then again, and walk 12 blocks away.
5. Offerings are strictly human flesh (Crimson Blood, zombie brain, rotten flesh, fleshy derivatives); beef, pork and spider eyes are refused.
6. Next: The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it) with the offering items in your hotbar (a second player must join over LAN; it is not staged). Run the rite and have the helper place the offerings while you stay bound. Try a golem with a seal on a pedestal if you have one. Then let the chain snap and see whether the helper can take over.
7. Next: The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it) with the offering items in your hotbar. Run the rite on this moderately stable altar and wait for a native instability event. Watch for the telegraph about a second before it, then see where you end up.
8. Next: The same infusion altar stands 7 blocks ahead (creative jars of every aspect stand behind it); you are in survival with armour and the offering items. Run the rite and let the chain snap on purpose (let your health fall to the floor). Take stock of the room.
9. Fight the raid: cultists and a Crimson Paladin champion with a boss bar. Let the raid kill you before you hold the dagger, then again while you hold it.
10. Win once: kill the champion and take the dagger from the pedestal.

**Expect**

- [ ] A chain rises from the matrix, binds you at the chest and pulls you back if you walk past 6 blocks; you lose about 1 HP per second, never through armour. The demanded item floats above the matrix; a met demand eats the offering, flicks the chain to its pedestal and pauses the drain.
- [ ] A missed demand bites 5 HP and doubles the drain; at the health floor the chain snaps with a reason on the action bar and you get Weakness I. You never die from the ritual itself (mobs and lava still can).
- [ ] Success: the dagger appears and the Rites is spent. Failure: the Rites drops back and is reusable.
- [ ] Putting an offering out before the start stops the recipe. A rite with another ring, or no session, never starts the minigame.
- [ ] A helper's offerings count; golems can serve the pedestals once the craft has begun. On a snap the chain does not pass to the helper (helpers assist only).
- [ ] The chain, the icon above the matrix and the flick read the same for the second player.
- [ ] A clear telegraph (about 20 ticks) warns of the Yank; then you are pulled to the altar and fully Chained for 3 seconds (first-person shackles, no item use). Helpers or golems have to serve the pedestals meanwhile.
- [ ] The drain keeps its pace; the Yank alone never kills you.
- [ ] The snap still completes the rite: the dagger lies on the pedestal and a hostile persistent raid opens in the room, with the champion and its boss bar.
- [ ] If the raid kills the binder before or while they hold the dagger, the champion takes it and drops it guaranteed when it dies. A raid that is beaten leaves the dagger with the winner.
- [ ] Raid and champion survive a world restart, and nothing ticks when no rite is running.

<sub>Already covered by automated pack tests: `minigame_opens_for_the_dagger_and_binds_the_starter`, `minigame_not_for_another_infusion`, `minigame_not_for_a_wrong_ring`, `minigame_offering_before_the_start_blocks_the_recipe`, `minigame_drains_the_binder_only_and_demands_at_40`, `minigame_offering_is_eaten_and_pauses_the_drain`, `minigame_wrong_and_ring_items_are_not_eaten_and_a_miss_bites`, `minigame_snaps_at_the_health_floor`, `minigame_snaps_when_the_player_is_far`, `minigame_ritual_damage_never_kills_but_mobs_and_lava_land`, `minigame_hard_gate_returns_the_rites`, `minigame_saved_data_round_trip`, `minigame_offering_tag_and_recipe_data`</sub>

## 76. Crimson Plating and the Gilded Cult Plate

Check id: `concilium.crimson_plating`

**Steps**

1. Read its research entry ("Crimson Initiation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. The infusion altar stands 7 blocks ahead, with creative jars of every aspect behind it; you hold an iron block, 2 Crimson Blood and 4 gold nuggets. Open the Crimson Initiation research page and read the plating entry. Build the infusion: iron block in the centre, the blood and nuggets on the ring; the jars behind the altar supply the essentia (metallum 64, victus 32, praemunio 32).
3. Run it. Then press Again (which resets research) and try it without the research.

**Expect**

- [ ] The recipe shows on the research page with its ring and costs; the infusion runs at low instability (2) and yields 9 Crimson Plating; the item and its tooltip read well.
- [ ] Without Crimson Initiation the recipe will not run.

## 77. Feeding a tamed rift to a hex

Check id: `concilium.vessel_feeding`

**Steps**

1. Read its research entry ("What It Keeps", "Rifts That Hold") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand four blocks from a lesser hex (Barrier Stone centre) holding a tamed rift. Only a lesser hex is a sink: a full hex tames a rift but never takes burden. You carry 10 temporary and 10 normal warp, a thaumometer, Wrath Cages (they carry warp) and a flux goo bucket.
3. Sneak and use the hex with nothing in hand: with the temporary warp first, then clear it (/thaumaturge warp remove temporary 10) and use it with only normal warp.
4. Throw a Wrath Cage onto the hex; pour the flux goo within four blocks. (Not staged: pushing vitium from a Vis Condenser, and standing in a flux aura for a few minutes. Try them by hand if you want those routes.)
5. Hold the thaumometer on the hex now and then to see the rift's size.
6. Next: You stand four blocks from a tamed lesser hex, with a stack of Wrath Cages. Throw them onto it and look at the ring stones at a third, two thirds, and past the threshold.

**Expect**

- [ ] Each route makes the rift grow (25 up to 75 as the burden nears the threshold); warp is taken temporary first, then normal, never permanent; thrown warp items vanish.
- [ ] The rift eats no blocks while the hex holds it; a wild rift nearby still does.
- [ ] The conversion rates feel about right: roughly three evenings of an active workshop to a break, not one hour and not ten.
- [ ] Three crack states appear on the ring stones, readable at a glance, the last once the hex is strained. A strained hex still transmutes.
- [ ] The look is acceptable as a placeholder (it is retextured runes, not final art).

<sub>Already covered by automated pack tests: `routes_f1_f2_f3_w1`, `route_w2_item`, `growth_eats_nothing`, `wild_rift_still_eats`, `chained_rift_unchanged`, `crack_states`, `strained_still_works`</sub>

## 78. A strained hex: loading, sleeping, contributors and absent players

Check id: `concilium.vessel_sink_edges`

**Steps**

1. Read its research entry ("What It Keeps", "Rifts That Hold") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A tamed lesser hex stands four blocks ahead on the ground where you were (staged here, not on a pad: the break cuts a crater of about 14 blocks round it, so stand on open ground first).
3. Throw Wrath Cages onto it until it is past its threshold, then save and quit to the title screen and reload the world (or fly far away and back).
4. Stand near it when it loads.
5. Next: It is night and a tamed lesser hex stands four blocks ahead on the ground where you were (staged here: the break cuts a crater of about 14 blocks, so stand on open ground first). You carry a bed and a stack of Wrath Cages.
6. Strain the hex with the cages, keep feeding past its threshold and watch the aura flux in the chunk.
7. Once the flux that leaked out passes a few hundred, place the bed and sleep through the night with every player in it.
8. Next: A tamed lesser hex stands four blocks ahead on the ground where you were (staged here: the break cuts a crater, so stand on open ground first). You carry Wrath Cages.
9. With a friend (LAN), both feed the same hex. Send the friend to the Nether, or the Causal Bouillon, before the break.
10. Let it break.
11. A friend feeds the hex, then logs off. Strain it with the cages yourself and let it break while they are away. They log in.
12. Compare with a friend who fed more or less.

**Expect**

- [ ] The hex and its rift are gone for good (nothing is put back). After the six-second break a blast crater lies round the spot, four anchor blocks stand on its floor 8 to 12 blocks out, and a dormant Vessel hangs three blocks above the middle.
- [ ] Nobody who fed it is left out: every online contributor is carried to the edge of the arena.
- [ ] A strained hex returns about 150 percent of what it is fed as aura flux, and nothing breaks until the leak passes its hidden second threshold and everyone sleeps.
- [ ] Sleeping before that threshold changes nothing.
- [ ] The friend is taken out of their dimension to a safe spot at the arena edge (15 blocks out), not into rock or lava, and the arena is the overworld one.
- [ ] They get temporary warp in proportion to their share of the burden, a warp event fires at once, and a message tells them something has come due. It happens once.
- [ ] Their research book shows the field note The Vessel (unfinished).

<sub>Already covered by automated pack tests: `break_on_reload`, `pure_rules`, `leak_returns_150_percent`, `break_on_sleep`, `sleep_below_leak_threshold_keeps_hex`, `absent_debt_paid`, `note_three_appears_at_the_break_and_completes_at_the_subdue`</sub>

## 79. The Vessel fight: waking, the pull, drawing and phases

Check id: `concilium.vessel_fight`

**Steps**

1. Read its research entry ("The Vessel") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand at a corner of the pad, 17 blocks from a dormant Vessel hanging over the middle, with its four anchors round it. Walk in.
3. Once it is awake, fight a while, then walk well away (more than 48 blocks: break through the glass rim, or use /gamemode creative to fly out) for a minute or more and come back.
4. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a shield, the ancient stone, a sword and a bow.
5. Wake it by walking in. Walk straight out from it at 4, 8 and 12 blocks, then jump near it. Do it again with a second player on LAN watching you.
6. Stand on a path of the stone from the kit (place it yourself), and use the shield.
7. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword and a shield.
8. Wake it and use the wand on an anchor. Hold still at the anchor while the tether builds (two draws, then it cools).
9. When a clot winds up at you, hit it back with your sword toward the hole. Miss one on purpose.
10. Draw at all four anchors, then do the whole fight alone and, if you can, with two others.
11. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword, a bow, a shield and the ancient stone.
12. Wake it and fight it from full Mass down. Notice the swarms at the middle phase and the swell before the gulp in the last.
13. Note how long the whole fight took solo, and with three.
14. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel (creative, so you can fly). The airship is not staged: bring a Create airship on Sable physics within 16 blocks of the Vessel once it is awake, with and without a crew aboard. Also park one and leave it.

**Expect**

- [ ] Within 16 blocks it wakes with a swell and a rumble; a boss bar appears. Its starting Mass grows with the players near it (8 solo).
- [ ] Left alone it goes dormant and keeps its Mass; coming back wakes it where it was.
- [ ] Walking out at 4 blocks is hard but possible; jumping near it is clearly a mistake. The pull is smooth on your own screen, and the watcher sees you move without snapping back.
- [ ] Weapons and arrows do not hurt it; arrows and items that reach it feed it. It eats only taint blocks and loose plants, never ordinary terrain.
- [ ] Each draw takes Mass off; an anchor cools after two draws and shows it. The clot's wind-up is readable (it grows, a ring closes) and the bat-back is hittable. A batted clot staggers the Vessel: no pull for four seconds and drawing goes twice as fast.
- [ ] A missed clot leaves goo and costs you the tether when it hits. Players who drew or batted count as participants.
- [ ] The phases change at the memo's Mass; swarms appear (never more than three). The gulp swells for three seconds, so there is time to reach a stone or an anchor before the pull triples.
- [ ] A solo fight takes some minutes, not seconds and not an hour; three players is quicker but still a fight. Anything wildly off is a balance note.
- [ ] The ship is drawn toward it without tumbling wildly (a slow turn is fine); crew aboard are not pulled off the deck; a parked ship is not thrown.
- [ ] A dormant Vessel does not touch it.

<sub>Already covered by automated pack tests: `pull_nothing_when_dormant`, `dormancy_keeps_state_and_wake_restores`, `start_mass_counts_players_within_48`, `pull_pure_rules`, `pull_item_gains_accel`, `pull_on_player_factors`, `weapons_do_nothing_kill_works`, `horizon_eats_and_feeds`, `horizon_hurts_never_kills_and_throws`, `eating_gain_cap_per_window`, `tether_forms_draws_and_drops_mass`, `tether_two_draws_cool_the_anchor`, `tether_breaks_on_leaving_and_loses_progress`, `clot_batted_staggers_and_doubles_draw`, `clot_miss_leaves_goo_and_counts`, `clot_hit_hurts_and_breaks_tether`, `participants_by_swarm_damage_and_presence_rule`, `phases_switch_and_spin_up_spawns_swarms`, `gulp_swells_then_pulls_and_stagger_cancels`, `sable_impulse_function_and_caps`, `sable_ship_near_moves_toward_the_hole_far_does_not`</sub>

## 80. How the Vessel looks and sounds

Check id: `concilium.vessel_looks`

**Steps**

1. Read its research entry ("The Vessel") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand at a corner of the pad, 17 blocks from a dormant Vessel. Look at it in daylight and again at night (/time set night), walk round it and see the disc edge-on.
3. Walk in to wake it and look at it feeding, in spin-up and in collapse (fight a while). The quiescent state is staged by the Draining check below: look at it there.
4. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand. Wake it by walking in and draw from an anchor.
5. Look at the ribbon in first person, then switch to third person (F5) and look at it from behind and from the side, and from a second player's view.
6. Next: A lesser hex stands six blocks ahead on the ground where you were (staged here, on real ground: the break carves a crater of about 14 blocks), with a chest of diamonds and a block of obsidian beside it inside the crater radius. You carry a wand and an anchor item (look at it in the hotbar).
7. Standing where you arrived, run /thaumicconcilium qa vessel ~ ~-1 ~6 breaking and watch the six seconds: with Sable in the pack the hex itself lifts off as a sub-level; use breaking_standin instead of breaking to see the version without Sable (restage first).
8. Try to wake the Vessel during the sequence (walk up to it), then look at the crater and where the four anchors landed.
9. Walk onto an anchor (no jump needed), draw from each of the four with the wand, and watch the glyphs and the hovering shard as an anchor is used up, cools and is tethered. Look again at night. Stage it again for a second break.
10. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with its anchors 8 to 12 blocks round it.
11. Walk in to wake it and approach slowly, then walk away; stand at the anchors (8 to 12 out).
12. Check the same near the Vessel while it is still dormant (before you walk in) and, from the Draining check, a quiescent one.
13. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, a sword, a bow and a shield. Sound on.
14. Play through a wake, a gulp, a stagger, an anchor cooling and becoming ready, and a horizon throw.
15. Repeat the wake and the quiescent view with a shader pack (Iris) on, if you use one.

**Expect**

- [ ] A black core with a ring; the accretion haze reads as a tilted disc whose near half passes in front. The sky dims near it while it feeds, and it is readable but not a screen-filler.
- [ ] Quiescent it is smaller and quiet, with four light ribbons running from the anchors to the hole. The vignette and dim violet bar show only near it.
- [ ] First person: it starts at the wand hand and ends at the hole. Third person (the harness could not measure it, the body hides it): it still leaves the hand, stays violet rather than washed white, and does not cut through your body strangely. A friend's tether looks the same from outside.
- [ ] The break: the Vessel shows only its ring and a thin haze while the hex rises into it (2 s), spins up with its runes lit (2 s) and cracks, runes whitening, with beams of white light (1 s). Then it bursts: streaks of light and glyphs fly out, the black closes, four shards tumble out along arcs and the anchors form exactly where they land, with dust and a thud. The Vessel does not wake until they are down. The hex is gone for good.
- [ ] The blast hurts and throws outward anything within the crater radius, hardest near the middle (armour and Blast Protection help), and nothing beyond it. The crater: carved as a ring spreading from the centre in under two seconds, never at the landing spots first, wider than the farthest anchor (about 14 blocks), a shallow bowl about 4 deep in the middle with a ragged edge and a low mound of the broken material (1 to 2 high) on its rim. Nothing drops from the destroyed blocks, but the chest spills its items; obsidian and tougher blocks are left standing.
- [ ] The four anchors stand in a rough circle round the hex: about a quarter turn apart and at about the same distance (8 to 12 blocks).
- [ ] Each anchor is a jagged, tilted piece of the hex itself: the same dark stone with an empty carved rune and a crack, no paint or glow on it; the four of one Vessel differ, and another Vessel shows another set (eight shapes in all). The top is half a block high: you step onto it.
- [ ] The runes leave the stone as glyphs that rise, sway, flicker and turn as they fade: a steady violet stream at two charges, a sparse one at one charge, only a small orange ember now and then (and smoke, an ember crack) while cooling, quick white glyphs while someone draws.
- [ ] A small stone shard hovers above each anchor, bobbing and turning slowly like an item on an infusion pedestal, each at its own height and rhythm; it spins faster while tethered, lies on the stone while cooling, rises above your head while you stand there, and the ribbon starts at it. The item reads as a rock with a shard, not a cube.
- [ ] Inside about 8 blocks the world dims (Darkness); inside about 4 you go blind (Blindness); the anchors stay readable; both end a few seconds after you step back.
- [ ] A dormant or quiescent Vessel never darkens you. The halo and the edge vignette still show. It feels like a warning, not a punishment.
- [ ] Every event has a sound and the hum changes with the state; none is harsh, subtitles read sensibly.
- [ ] With shaders the core and ribbons still draw (this has never been tried).

<sub>Already covered by automated pack tests: `a_vessels_four_anchors_carry_four_distinct_shapes`, `anchor_spokes_form_a_rough_circle`, `break_sequence_lands_four_anchors_on_the_radial_spots`, `interrupted_break_finishes_at_once_on_load`, `sable_break_holds_the_hex_and_leaves_no_sub_level`, `the_burst_carves_a_crater_with_a_rim`, `a_crater_cut_short_is_finished_on_load`, `a_full_hex_never_becomes_a_sink`, `darkness_and_blindness_follow_the_radii_while_active`, `no_darkness_when_dormant_or_subdued`</sub>

## 81. The rite: needing the research and draining the Vessel

Check id: `concilium.vessel_rite_drain`

**Steps**

1. Read its research entry ("Drawing It Out") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand five blocks from a quiescent Vessel with its four anchors round it. You have none of the research (the staging reset it) and carry a wand.
3. Use the wand on one of the four anchors.
4. Then get Drawing It Out: it needs The Vessel note (subdue a Vessel, or /thaumicconcilium qa research) and Thaumaturge's eldritch research (Unlock Eldritch, which needs the Void Seed). Try again after only one of the two.
5. Next: You stand five blocks from a quiescent Vessel with its four anchors round it, and have Drawing It Out. Use the wand on an anchor and hold the wand in your hand next to it.
6. Wait through one unit (about a minute), then up to five. Try the other three anchors with a friend.
7. Check your warp (thaumonomicon or /thaumaturge warp info) before and after.
8. Next: You stand five blocks from a quiescent Vessel with its four anchors round it, and have Drawing It Out.
9. Start a drain with the wand on an anchor, wait half a unit, then put the wand away (or walk away). Save and quit, reload, and go back to the anchor (staging again would rebuild it: do not press Again).

**Expect**

- [ ] Without it the anchor tells you that you do not know how to draw from it and nothing happens, even with only one of the two researches.
- [ ] Drawing It Out appears in the Thaumic Concilium tab, right of the Hex of Predictability, once its parents are done; it costs warp 3 to learn.
- [ ] A tether runs from the anchor to the hole. Each full minute the Vessel's charge drops by one of 20 and you gain 1 temporary warp; at every fifth unit 1 normal warp as well. Four anchors together drain it faster; a full drain by one person takes about 20 minutes.
- [ ] The pace feels like a slow rite you can do between other jobs, not a chore.
- [ ] The tether lets go at once. The charge and the unit's progress are kept; using the wand again carries on where it was. Nothing runs while nobody drains (no particles, no fibre growth, no goo).

<sub>Already covered by automated pack tests: `drain_needs_the_research`, `each_unit_gives_warp_every_fifth_normal`, `rite_pure_rules`, `pause_and_resume_keep_charge_across_save_and_load`</sub>

## 82. The rite: the world answers, the Taint Seed and the motes

Check id: `concilium.vessel_rite_end`

**Steps**

1. Read its research entry ("Drawing It Out") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand five blocks from a quiescent Vessel with its four anchors round it, with a wand and a thaumometer (the pad is only 25 blocks wide, so the ring is cut off at its edge).
3. Drain for several units with the wand on an anchor. Watch the ring around the Vessel as units pass (fly up and out for a view), and the anchor you are using.
4. Pause the drain and wait a few minutes.
5. Next: You stand five blocks from a quiescent Vessel (charge 20, no missed clots) with its four anchors round it, with a wand and a sword; difficulty is easy so the seed can spawn.
6. Drain it to the end with the wand (about 20 minutes alone, quicker with a friend on the other anchors). Do the same once after a fight where you let several clots land (fight_phases stages one).
7. Kill the seed and wait a few minutes.
8. Next: You stand at a corner of the pad, 17 blocks from a dormant Vessel, with a wand, sword, bow, shield and ancient stone.
9. Subdue it with a friend (both draw or bat clots). Have one more friend who fed the hex stand near for ten seconds, and one who took part log out before the end.
10. Fill your inventory completely with stone before Mass reaches zero in one run.
11. Compare motes with each other over a few fights.

**Expect**

- [ ] Taint fibres and a blight spread outward from the Vessel in a ring that widens from about 8 to 24 blocks as units pass; goo spills at the anchor you are using.
- [ ] As soon as you pause, no new fibre appears, and the blight stops being held by the Vessel (it starts to wither at its own pace).
- [ ] The spread is dramatic but does not lag the game.
- [ ] The Vessel is gone; a Taint Seed stands where it hung: a plain one for a clean fight, a Prime Taint Seed from a score of 12 (one point per missed clot, one per 15 goo spills at the anchors), with more health and reserve the higher the score. It lives until you kill it.
- [ ] When it dies the blight around it withers.
- [ ] The four anchor shards crumble into rubble particles with a stone-break sound as the last unit drains, and their blocks are gone.
- [ ] At Mass 0 every participant gets a Primordial Mote in the inventory (dropped at the feet if full), about one in ten gets a second. The player who logged out gets theirs on login. Someone who did nothing gets nothing.
- [ ] The field notes The Vessel (completed) and Primordial Mote appear.

<sub>Already covered by automated pack tests: `taint_origin_and_pulses_only_while_draining`, `last_unit_leaves_a_plain_seed_and_removes_the_vessel`, `many_missed_clots_leave_a_prime_seed`, `seed_scale_follows_clots_and_goo`, `motes_reach_every_participant_online_full_and_offline`, `second_mote_rolls_at_ten_percent_seeded`</sub>

## 83. The Vessel field notes

Check id: `concilium.field_notes`

**Steps**

1. Read its research entry ("The Vessel") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have no research (reset) and stand on the ground where you were, with a tamed lesser hex four blocks ahead (staged here: the break carves a crater, so stand on open ground first) and Wrath Cages.
3. Finish the Hex of Predictability research (the staging cannot grant it without the note appearing early); feed the hex past a quarter of its threshold; let it break; subdue the Vessel; receive a mote.
4. Open the Thaumic Concilium tab after each and read the new entry, then read all five once more in order.

**Expect**

- [ ] Rifts That Hold arrives with the hex research (warp 1); What It Keeps once a hex you fed passes a quarter; The Vessel appears at the first break and completes at the first subdue; Drawing It Out when its parents are done; Primordial Mote with the first mote.
- [ ] They sit in one row, right of the hex entry, with the book's lines drawn sensibly. The prose reads as dry notes growing uneasy and the rules are stated plainly.

<sub>Already covered by automated pack tests: `note_one_comes_with_the_hex_research_and_on_login`, `note_two_when_a_hex_you_fed_passes_a_quarter`, `note_three_appears_at_the_break_and_completes_at_the_subdue`, `note_three_completes_on_login_for_a_participant_who_was_away`</sub>

## 84. The Verdant Capital: craft, place, feed and Heartstones

Check id: `concilium.verdant_capital`

**Steps**

1. Read its research entry ("The Green Translation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have The Green Translation research and three Verdant Capitals (the infusion itself is covered by the recipe test: it needs the jar node catalyst and the two Botania runes, silverwood and greatwood saplings, gold, quicksilver and a mana diamond). A Subdued Vessel hangs five blocks ahead with its four anchors round it; one lone anchor stands three blocks behind you.
3. Place a capital on one of the Vessel's anchor shards, then on another block (the grass), then on the lone anchor.
4. Next: A Verdant Capital stands three blocks ahead on an anchor shard, with a creative Botania mana pool three blocks to its left. You have two sparks, a spreader and a wand of the forest.
5. Feed the capital with a spark between the pool and it (or with the spreader) and note how long one spreader keeps it fed.
6. Stop feeding. Wait past the grace (6000 ticks, or lower the config).
7. Next: A Verdant Capital stands three blocks ahead on an anchor shard (the Heartstone pair and the second player are not staged).
8. With a Heartstone pair linked, finish the rite with the partner offline (see the Teaser check), then have them log in.
9. Next: You have the Botania lexicon and the Thaumonomicon, and the research up to The Glade.
10. Open the Botania lexicon (Misc) and Thaumonomicon: The Green Translation and The Glade.

**Expect**

- [ ] It places only on an anchor shard; on any other block it vanishes (drops back).
- [ ] Without a Subdued Vessel it refuses.
- [ ] Broken, it drops itself.
- [ ] Fed: the star opens, counter-rotates, the beam runs through the centre. One spreader should not keep it fed for long.
- [ ] Starved: spin slows, sphere darkens; past the grace it unwinds with purple crackles and a unit is refunded.
- [ ] The partner is counted at the ending and is paid (mote, research) on login.
- [ ] The lexicon lists the Verdant Capital under Misc and names our tab. The Green Translation states the quarter-per-capital root chance and the endings; The Glade matches.

<sub>Already covered by automated pack tests: `capital_infusion_recipe_is_loaded`, `capital_places_only_on_a_subdued_shard`, `capital_is_a_mana_receiver_and_spark_socket`, `capped_anchor_spends_mana_a_tick_and_gives_no_warp_or_spill`, `starved_capital_pauses_unwinds_refunds_and_shows_its_drive`, `placer_and_heartstone_partner_are_participants`, `offline_partner_counts_and_is_owed_a_mote`, `registry_records_heartstone_ids_on_login`</sub>

## 85. The Verdant Capital: looks, breath and shader packs

Check id: `concilium.capital_looks`

**Steps**

1. Read its research entry ("The Green Translation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Shader packs off. You stand three blocks from a Verdant Capital sitting on a Vessel Anchor shard.
3. Set its state by hand from where you arrived (the capital is at ~ ~1 ~3): /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:0b} for idle, {drive:2b,starvedSince:99999999L} for starved and calm, {drive:2b,starvedSince:-100000L} for starved and angry (the latter half of its grace), {drive:3b} for unwinding. feedSide 2, 3, 4, 5 are north, south, west, east; 1 is from above (a spark).
4. Watch each state for at least two breaths from two blocks away, from the side and from above, then from five blocks. Go idle, fed, starved calm, starved angry, unwinding (wait ten seconds), then fed again and keep watching for half a minute.
5. Next: You stand three blocks from a Verdant Capital sitting on an anchor shard.
6. Watch it across idle, fed, starved, angry, unwinding and fed again; set the states from where you arrived (the capital is at ~ ~1 ~3): /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:0b} for idle, {drive:2b,starvedSince:99999999L} for starved and calm, {drive:2b,starvedSince:-100000L} for starved and angry (the latter half of its grace), {drive:3b} for unwinding. feedSide 2, 3, 4, 5 are north, south, west, east; 1 is from above (a spark).
7. Next: The render harness cannot load Iris, so this is checked only here. You stand three blocks from a Verdant Capital on an anchor shard. Turn on BSL and repeat the fed and unwinding states from the steps above (set them from where you arrived with /data merge block ~ ~1 ~3 {drive:1b,feedSide:5b} for fed, {drive:3b} for unwinding), by day and by night; then the same under Bliss.

**Expect**

- [ ] The capital is eight small golden tetrahedra (cyan gilding, a little lichen along their edges) hovering over the shard on a faint cyan sphere: each piece is half sunk into the sphere's surface, its centre exactly on it. Four form a triforce pointing up, four one pointing down. From above, idle, it is a six-pointed star.
- [ ] It breathes in every state: the sphere and the pieces swell a little and settle back, never below the size of the state. Idle: slow, even and deep, about five breaths a minute, with a short rest at the top and a longer one at the bottom; a very faint rocking of the pieces and shiver of the whole thing that is strongest at the top of the breath and gone by the end of the rest.
- [ ] Fed: a little wider, the two triforces turning opposite ways (one turn in six seconds), a green-white beam from the fed side through the exact centre of the sphere, its pulses flowing inward. The breath is exact box breathing: four seconds in, four held, four out, four held.
- [ ] Starved, calm: the ray fades, the star returns to its idle size and slows to a crawl, the sphere dims half way to black with a violet rim. It breathes like uneasy rest, about 13 a minute, a little uneven, with a long slow sigh now and then.
- [ ] Starved, angry (the latter half of the grace): within a few seconds the breath turns deep and hard, about 16 a minute: a full inhale, a short sharp exhale, then a half-second pause.
- [ ] Unwinding: the star draws in, the rings reverse briefly then stop on a star alignment, and the six waist pieces leave their triforces: each loops over the equator and back, one after another round the waist, turning a little about its own axis one way above the equator and the other way below, while the two pole pieces keep spinning opposite ways. The star then draws in further. The sphere is a practically jet-black orb with a dark violet rim (the Vessel's colours). The breath is fast, shallow and ragged, about 43 a minute, with gasps; the pieces tremble and the whole capital jiggles roughly and never quite stops. The beam is violet with its pulses flowing back out, and purple-white crackles jump from the pieces.
- [ ] Fed again after unwinding or starving: the pieces return to their triforces, the star opens, and it takes one sigh of relief: a double inhale to its fullest and one long exhale (about ten seconds), then box breathing.
- [ ] The pieces never touch or pass through one another, in any state or while changing state, and the whole star stays inside its block.
- [ ] In the inventory and in the hand the item is the closed star (the eight pieces joined into two interlocked triforces), still, in a faint cyan sphere.
- [ ] Calm and slow when fed or idle, anger in the latter half of the grace, ragged panic when unwinding, one sigh of relief when fed again.
- [ ] At full compaction the pieces cross the equator and pirouette; the orb is near black with a faint violet rim.
- [ ] The gold pieces are lit and shadowed like any block and cast shadows; with a labPBR pack the gold shines and the lichen does not.
- [ ] The sphere is a faint translucent glow round the pieces, not an opaque disc; dark with a violet rim when unwinding. Its shadow, if the pack casts one, may be a disc: say if that is distracting.
- [ ] The ray is bright (it should glow or bloom like a beacon beam), with its cleats still visible.
- [ ] Each crackle keeps its white core and violet fringe. The dark outline round it may be softer than without shaders, but it must darken, not brighten or tint, what is behind it.

<sub>Already covered by automated pack tests: `capital_update_tag_carries_drive_side_and_time`, `capital_motion_keeps_to_its_proven_bounds`</sub>

## 86. The Vessel endings: tiers, finale, saving and a second player

Check id: `concilium.endings`

**Steps**

1. Read its research entry ("The Green Translation") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are staged where you stand and the tier 4 ending (four capitals) has been started: you are moved to the crater's edge. Tier 3: press Again at a new spot and run /thaumicconcilium qa finale 3 instead of the staged one. Tiers 0 to 2 need a played rite (the command takes 3 or 4 only).
3. Run the rite at 0, 1, 2, 3 and 4 capitals and compare the endings.
4. Next: You are staged where you stand: open flat ground, difficulty easy. Set your shader pack and start your own recorder first (the game does not film itself).
5. Tick this box, then claim a reward: the first runs the tier 4 ending (four capitals), the second tier 3 (three). The crater is cut under your feet and you are moved to its edge; the rite is on its last unit and finishes at once.
6. Fly or walk around by hand while the real ending plays: the swell, the dark, the wisp and the burst, the grove spreading, the trees growing, three to five wild Taint Seeds eaten by roots in the background.
7. Next: You are staged where you stand and the tier 4 ending has been started (you are moved to the crater edge). Watch it from outside; to see it from inside the swollen Vessel, press Again and walk into the crater at once. Use a second player over LAN if you can.
8. Also run the ending at tiers 0 to 2 (played rite) and at 3 (/thaumicconcilium qa finale 3).
9. Next: You are staged where you stand and the tier 4 ending has been started: you are moved to the crater's edge.
10. Save and quit mid-finale and mid-painting; reload. (Mid-rite: the Vessel rite checks stage a rite.) Press Again to run it once more.
11. Next: Host from your game and have a friend join first, standing nearby, then press Again: the tier 4 ending starts where you stand and you are moved to the crater's edge.

**Expect**

- [ ] Taint pulses run in full at every tier, including a rite run only by capitals.
- [ ] Tier 0: an accelerated seed and its children spread past the crater. Tier 1: a bound seed, taint held near the rim. Tier 2: a seed that starves. Tiers 3 and 4: no seed at the centre.
- [ ] Second mote chances rise with tier; tier 4 removes permanent warp (3 solo, 1 with a partner), once per Vessel.
- [ ] Research The Glade arrives for every tier 3 and 4 participant, online and on next login; none at tiers 0 to 2.
- [ ] The real finale, painter, growth and roots run as in a played rite (the tier 4 grove is 70 or more blocks across: give it about 2 to 3 minutes), with the seeded Taint Seeds strangled by roots after the light returns.
- [ ] Tier 3 differs only in three capitals and about three in four seeds rooted.
- [ ] Tiers 0 to 2: about 8 s of full Blindness and Darkness inside; nothing outside; no light, no flash.
- [ ] Tiers 3 and 4 inside: dark while the crater is painted, then a shadowy view with a faint wisp from the pond, pulsing and bursting. Outside: the Vessel shifts violet to cyan, then a white-out of 1 to 2 s. Insiders see before outsiders.
- [ ] Sight returns well before the roots begin (about 20 s). Logging out or reloading mid-finale ends the Vessel at once and sight returns.
- [ ] All three resume (the finale ends at once with sight returned, by design).
- [ ] Capital animation syncs, flash and blindness are per player, the Glade note arrives, roots show.

<sub>Already covered by automated pack tests: `pulses_are_full_at_every_capital_count`, `mixed_rite_finishes_records_the_capital_count_and_drops_the_capitals`, `tier0_accelerated_seed_and_children`, `tier1_bound_spreads_to_the_rim_and_no_further`, `tier2_starving_seed_has_no_reserve`, `tiers_3_and_4_doomed_seed_has_no_reserve_and_a_grove_job`, `tier4_warp_three_solo_one_each_for_a_pair`, `tiers_3_and_4_grant_the_glade_to_every_participant_tiers_0_to_2_do_not`, `an_offline_participant_gets_the_glade_on_login`, `staging_finishes_a_tier_4_rite_and_seeds_the_grove`, `staging_finishes_a_tier_3_rite_and_seeds_the_grove`, `tier0_blinds_for_8_seconds_without_light_or_flash`, `tier1_blinds_for_8_seconds_without_light_or_flash`, `tier2_blinds_for_8_seconds_without_light_or_flash`, `tier3_paints_the_crater_under_cover`, `tier4_roots_wait_for_sight_after_the_painted_crater`, `unfinished_crater_collapses_at_the_timeout`, `a_vessel_loaded_in_dying_ends_at_once_and_returns_sight`, `buffer_placer_drive_timer_and_progress_survive_save_and_load`, `aftermath_survives_save_and_load`, `job_resumes_after_save_and_load`, `a_strangle_survives_a_save_and_a_load`, `seed_death_skips_a_missing_seed_and_resumes_after_load`, `capital_update_tag_carries_drive_side_and_time`</sub>

## 87. Roots and the grove strangle Taint Seeds

Check id: `concilium.grove_roots`

**Steps**

1. Read its research entry ("The Glade") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You are staged where you stand and the tier 3 ending (three capitals) has been started, with wild Taint Seeds seeded in the grove. Press Again somewhere else and run /thaumicconcilium qa finale 4 for tier 4.
3. Watch the seeds in the fight and in the grove.
4. Next: A Taint Seed six blocks ahead is already being killed by the grove (twelve seconds, the roots break the ground within three). Watch from where you stand; press Again to replay it, and fly out to about 32 blocks before pressing Again to watch it from far away.
5. For the real thing, finish a rite with three or four Verdant Capitals and wait at the crater until the grove has finished spreading (see the Teaser check).

**Expect**

- [ ] Seeds are strangled at about 0/25/50/75/100 percent by capital count; at tier 4 every seed in the grove is rooted. At most 3 sequences at once nearby.
- [ ] Eight roots break the ground in a ring and arch over the seed within three seconds; the seed lashes five times, faster each time, with its own tentacle sound, and the roots flinch and tighten; six clusters of leaves burst out one after another; the seed dies, a column of green-gold motes rises, and the whole mound sinks into the ground.
- [ ] In the real ending the seed cannot be killed early, its column turns to grove and the mana pond appears within a second of the mound sinking.
- [ ] From 32 blocks the roots and the mote column can be made out. Say if this should read more strongly at a distance.
- [ ] The timing feels right: not rushed, not dragging; the seed's own death flash under the leaves is not distracting.
- [ ] With BSL and with Bliss (QA only, no harness): roots and leaves are lit and shadowed, the motes show.

<sub>Already covered by automated pack tests: `root_chance_by_capitals_and_the_overlap_rule`, `tier4_roots_every_seed_in_the_grove`, `tier3_roots_about_three_in_four`, `no_more_than_the_cap_play_at_once_near_each_other`, `grove_kills_the_seed_over_twelve_seconds_then_paints_its_column`, `seed_death_skips_a_missing_seed_and_resumes_after_load`, `doomed_seed_dies_when_the_last_ring_closes`</sub>

## 88. The mana pond: surface, mound and mana draw

Check id: `concilium.mana_pond`

**Steps**

1. Read its research entry ("The Glade") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Shader packs off. A sheet of mana pond is sunk into the ground in front of you (7 by 5 blocks). Look at it; for the pond of a tier 3 or 4 grove, look at it in the grove checks as well.
3. Watch it for half a minute by day, then /time set midnight.
4. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground at least 6 blocks deep: stand on open ground first). Wait a minute.
5. Look at the pool in the middle of the hollow from the rim, from the crater floor beside it and from above. Press Again two or three times in different places.
6. Next: The render harness cannot load Iris, so this is checked only here. A sheet of mana pond is sunk into the ground in front of you. Turn on BSL and look at it by day and at night; then the same under Bliss, Noble, Revelation and Solas.
7. Next: A tier 3 grove of radius 12 with its mana pond is painted where you stand (staged here, on real ground), with a Botania mana pool, a spreader and a bucket.
8. Place the mana pool or hold the spreader touching a pond block; check the water by bucket and walking in.

**Expect**

- [ ] A still, pale blue surface that reads as one sheet of water: thin veins of light wander across it and run over block borders, with paler and deeper zones several blocks wide. No pattern repeats from block to block and nothing drifts in one direction.
- [ ] It moves slowly (the whole picture comes round in 16 seconds) and never jumps.
- [ ] Sparkles are rare: two or three small stars rise from one spot, then nothing for 6 to 14 seconds. Now and then a single faint glint shows on a vein.
- [ ] It glows at night (light level 12).
- [ ] Say what you would turn up or down: the zones, the veins and the sparkle events are separate dials.
- [ ] 13 blocks of mana at one height in a basin of Botania livingrock: a low outcrop one block above the crater floor, the water level with its top, no side of the water open.
- [ ] The pool is round-ish and varies from crater to crater (the roundest shape is the commonest, a third of them, the others a little longer); the rock rim is wider and uneven, mostly 2 to 3 blocks, with slabs and stairs weathering its outline.
- [ ] Moss and cracks creep up from the grass: mossy and cracked livingrock bricks, moss carpet, moss blocks and tongues of turf are densest where the stone meets the grass and thin out toward the water; none touch the water. Small plants grow on the lower slope and beside the stone.
- [ ] No sapling or tree stands on the mound.
- [ ] Say if it reads too tidy or too mossy: rim width, the shares of stairs, slabs, bricks and moss are separate dials.
- [ ] The surface shows on all 13 blocks, pale blue and translucent: not black, not invisible, no missing tile, not replaced by the pack's own water.
- [ ] The veins still run across block borders (no grid) and still move (the texture animates); nothing flickers from 30 blocks away.
- [ ] It glows at night and lights the ground round it; the rising sparkles show.
- [ ] Name any pack where one of these fails.
- [ ] The water does not flow, cannot be bucketed, does not push.
- [ ] At tier 4 the pond starts with 1,000 mana per point of the rite's burden (about 0.34 to 0.6 M) from the moment it stands; tier 3 by its chunks and nodes.
- [ ] A touching pool or held spreader draws mana; past the residual it drains vis from grove nodes, then breaks the weakest node into a rift that spreads taint and pushes the grove back. Only a held spreader draws; nothing otherwise.

<sub>Already covered by automated pack tests: `pond_is_placed_at_tier_3_and_4_and_not_without_botania`, `pond_shape_is_a_rough_circle_of_13`, `pond_is_level_in_a_livingrock_mound`, `pond_mound_rule_ring_rim_and_edge_stones`, `fluid_does_not_flow_and_cannot_be_bucketed`, `residual_is_sized_by_chunks_and_nodes`, `draws_past_the_residual_drain_node_vis_fullest_first`, `overdraw_breaks_the_weakest_node_into_a_rift_each_step`, `rift_size_scales_with_node_capacity_within_the_clamp`, `spreader_beside_the_pond_fills_from_the_ledger`, `pool_beside_the_pond_gets_nothing`, `nothing_runs_without_draws`, `a_tier_four_pond_is_sized_by_the_burden`</sub>

## 89. The grove: biome, flora, ripple and airships

Check id: `concilium.grove_world`

**Steps**

1. Read its research entry ("The Glade") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A tier 4 grove of radius 70 is being painted where you stand (staged here, on real ground: stand on open ground first). Watch for a few minutes, then press Again elsewhere and run /thaumicconcilium qa grove 3 12; or watch a real ending.
3. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground: stand on open ground first).
4. Walk the grove after painting; look in shade for mushrooms.
5. Next: You are staged where you stand (open ground) and the tier 4 ending has been started: you are moved to the crater's lip. Open F3 and look at the server tick time while it grows, then watch it again from about 60 blocks out (press Again for a second run).
6. Once, go far away (past your view distance) while it grows, and come back.
7. Next: A tier 4 grove of radius 70 is being painted where you stand (staged here, on real ground).
8. Fly a Sable airship over the grove and crater while it paints (the airship is not staged).

**Expect**

- [ ] The grove biome shows (sky, colours, magical forest spawns); radius 70 to 120 at tier 4 (by the rite's burden), about the crater plus 2 at tier 3.
- [ ] Taint does not restore over it; nodes inside do not drift to the taint.
- [ ] Botania flowers, double flowers, mushrooms in shade, meadow flowers, grass and fern, Thaumaturge flora and mana pods; about one node a chunk at most.
- [ ] Without Dynamic Trees or Botania: no breakage, the pure ending.
- [ ] The meadow spreads outward at one steady speed (a ring every 4 s); the trees rise a little behind it in small steps, never popping in whole; the whole forest stands about 2 to 3 minutes after sight returns.
- [ ] Leaves never drop and regrow while trees grow (no 'seasons').
- [ ] No lasting stutter. One short hitch the first time a node or hero is placed in a session is known (a one-time warm-up).
- [ ] Trees nobody could see are simply grown when you come back.
- [ ] The airship is unharmed by the painter; no hitch while the grove paints; idle cost nil afterwards.

<sub>Already covered by automated pack tests: `tier3_paints_grove_hollow_and_bare_pond`, `tier4_soil_and_step_timing`, `tainted_column_decays_then_paints_and_restore_returns_grove`, `pure_node_leaves_grove_as_grove`, `flora_rules_plan_and_job_record`, `tier4_flora_counts_saplings_landmarks_and_bare_pond`, `tier3_without_botania_has_landmark_and_two_plus_one_saplings`, `saplings_are_thaumaturge_blocks_without_dynamic_trees`, `shade_mushrooms_under_a_roof_and_nodes_at_most_one_per_chunk`, `a_full_size_grove_paints_its_hill`, `an_unloaded_waiting_chunk_never_blocks_a_loaded_one`, `a_finale_tree_grows_in_small_steps_then_on_to_its_cap`, `plot_chunks_are_skipped_and_a_plot_hex_gets_no_job`, `finished_jobs_and_empty_levels_cost_nothing`</sub>

## 90. The grove's trees: growth, seeds and decay

Check id: `concilium.grove_trees`

**Steps**

1. Read its research entry ("The Glade") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground: stand on open ground first), with an axe in your hand slot.
3. Stay in the finished grove for a game day; chop a landmark and let it fall; /thaumicconcilium qa landmark false 0 0 ~ ~ ~4 shows a variant.
4. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground). You carry two greatwood saplings.
5. In the finished grove, /tick sprint 72000 (three game days), then look again.
6. Plant a greatwood seed in the grove and one outside it; /tick sprint 72000 again.
7. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground).
8. Break leaves of a grove tree until seeds drop; leave some on the ground for a few minutes; pick others up.
9. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with an axe and two spreaders.
10. Watch the grove's trees over a game day (/tick sprint 24000): leaves, twigs.
11. Chop one tree down; then drain the pond completely (spreaders) and watch another day.
12. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with an axe.
13. Look at a grove tree's bark, leaves and sapling up close; point Jade at them.
14. Chop one: check the drops. With Sable Trees, watch it fall. Fly away until Voxy draws the grove as far terrain.
15. Next: A tier 3 grove of radius 12 is painted where you stand (staged here, on real ground), with wheat seeds and saplings.
16. Plant wheat and saplings inside and outside the grove; wait.

**Expect**

- [ ] Landmarks grow in visible stages, dense apex at the centre, small saplings at the edge; young landmarks mature a stage a game day.
- [ ] All 8 greatwoods and 10 silverwoods look right, fall and drop like ordinary Dynamic Trees; silverwood trunks fatten toward 3.
- [ ] Heroes keep growing toward 40; the hill's trees grow to their caps (26 beside the heroes, never under 19 at the edge), on the same shapes, never off them.
- [ ] The seed planted in the grove grows into a grove greatwood that stops at 19; the one outside is an ordinary Thaumaturge greatwood.
- [ ] Seeds left lying plant themselves and grow as grove trees (the hill's caps).
- [ ] Picked-up seeds are plain Thaumaturge seeds: they stack with ordinary ones and grow ordinary trees outside a grove.
- [ ] With mana in the pond, no leaf drops and no twig rots in the grove.
- [ ] A chopped tree's leaves still clear. Once the pond is empty and no node is left, leaves and twigs decay as anywhere else.
- [ ] Bark, rings, leaves and saplings look like Thaumaturge's greatwood and silverwood (leaves take the grove's magical forest tint, as Thaumaturge's own do there).
- [ ] Jade names them Greatwood/Silverwood Tree, Leaves, Sapling. Drops are Thaumaturge's logs, sticks and seeds.
- [ ] Falling with Sable Trees and far rendering with Voxy behave as for other Dynamic Trees trees.
- [ ] Crops and trees inside outgrow those outside by about a quarter.

<sub>Already covered by automated pack tests: `every_landmark_variant_grows_in_stages_to_the_one_shot_tree`, `landmark_entries_follow_the_falloff_the_gates_and_the_day`, `saplings_become_trees_by_bounded_pulses`, `every_landmark_variant_is_a_valid_living_tree`, `twig_leaves_survive_random_ticks_and_growth_oak`, `natural_growth_follows_the_template_to_the_cap`, `a_finale_tree_grows_in_small_steps_then_on_to_its_cap`, `thaumaturge_saplings_in_a_grove_become_glade_trees`, `natural_growth_of_each_species_reaches_its_class_height`, `a_finale_trees_own_seeds_plant_its_lineage`, `a_living_grove_keeps_its_leaves_and_twigs`, `the_grove_families_and_species_exist_with_the_deeper_signal`, `template_sets_are_whole_parent_closed_and_in_the_signal_depth`, `crops_in_the_grove_grow_a_quarter_faster`, `trees_in_the_grove_get_the_extra_step_by_mixin`</sub>

## 91. The Gem of Rifts: use, casts and held look

Check id: `concilium.rift_gem`

**Steps**

1. Read its research entry ("Rift Gem") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand on open ground with the plain QA wand in slot 1 and the Gem of Rifts in slot 2.
3. Hold the Gem of Rifts and hold the use key (right-click) with no other rift within 16 blocks.
4. Keep holding to see the fast spin, then release. Try it again with the wand taken out of the hotbar.
5. Next: You stand in front of a crafting table with the plain QA wand, the Gem of Rifts, two Terra-cast Gems and an inert one; a block of dirt is on your right.
6. Use a Terra-cast Gem on the dirt to bind it to this dimension (bind one in another dimension if you can reach one).
7. In the crafting grid, put the Gem of Rifts and the bound Terra-cast Gem.
8. Repeat with an empty terra gem and with a second gem after 16 casts.
9. Next: All four gems and an item frame are in your hotbar.
10. Hold each gem in the main hand, then in the off hand. Press F5 and look at them in third person, in sun and in shade; drop one and put one in an item frame.
11. Compare the Terra-cast Gem's glass in third person with the Gem of Rifts.

**Expect**

- [ ] The gem spins up while held; after the first charge an interdimensional rift appears and the wand pays perditio 10 and aer 10. Without vis in the hotbar nothing opens.
- [ ] A second use within 16 blocks of the first rift does nothing. The rift grows from size 5 to 50 over a few seconds, shows lightning and teleports nothing by itself.
- [ ] Left alone, it collapses by shrinking and vanishes without taint, fibres or warp, and hurts nobody.
- [ ] The result is the Rift Gem with the terra gem's dimension added as a cast; the terra gem is used up.
- [ ] An unbound (full or inert) terra gem matches nothing, and 16 casts is the limit.
- [ ] In first person the active gems hover in the hand with a slow spin (fast while using) and the arm sways; the off hand is the mirror image, and the cast stone shows inside the Rift Gem when a cast is selected.
- [ ] Third person shows the gem held at the hand and lit like the rest of the body; dropped gems stand upright about half a block wide, the frame shows the pyramid.
- [ ] Known uncertainty: the Terra-cast Gem's glass reads orange-brown in third person where the original read green. Judge whether it is acceptable.

<sub>Already covered by automated pack tests: `gem_recipes`, `interdimensional_rift_life`, `terra_gem_crafting`</sub>

## 92. Terra cast gem

Check id: `concilium.terra_gem`

**Steps**

1. Read its research entry ("Terra Cast Gem") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a row of dirt, stone, sand, gravel and a chest, with the plain QA wand in slot 1 and the Terra-cast Gem in slot 2.
3. Hold the gem and use it on each block, including the chest (a block you may not edit, such as spawn protection, you must find yourself).
4. Hold the gem and check its tooltip.

**Expect**

- [ ] Each earthy block is removed with no drop; the gem becomes bound to the current dimension and costs terra 10 and aer 10 of vis.
- [ ] A chest (or any block with contents) is refused and not deleted; protected blocks are refused.

<sub>Already covered by automated pack tests: `terra_gem_absorbs`</sub>

## 93. The Causal Bouillon: crossing in and out

Check id: `concilium.subspace`

**Steps**

1. Read its research entry ("Rift Gem") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand on open ground with the plain QA wand, the Gem of Rifts and a white bed.
3. Note your x and z (F3). Open a rift with the gem and, holding the gem, step into it.
4. Look at the sky and fog, then look down. Try placing the white bed and sleeping, and walk about.
5. Next: You stand on open ground with the plain QA wand, the Gem of Rifts, two Terra-cast Gems and a few netherrack, a crafting table to your right.
6. Open a rift and step in holding the gem (you arrive in the Bouillon), then walk to about x 100 z 100, open a rift with the gem and step in: you return to the overworld.
7. Repeat, but first shift + swing (left-click while sneaking) with the gem to flip it to deflates, then step out.
8. Craft a cast onto the Rift Gem with a Terra-cast Gem bound in the Nether (use the gem on a Nether block there), cycle casts with shift + use, select the Nether and step out again.

**Expect**

- [ ] You arrive in the Causal Bouillon at the same x and z, on the surface (y 4) of a flat Void Reality floor with air below it at y 0 (a safe landing, no suffocating).
- [ ] The sky is a fixed noon with no sun or moon and no weather, the fog and ambient ash read as a void, and the world has no day cycle.
- [ ] Beds cannot be used and set no spawn; the dimension is otherwise empty.
- [ ] Default (inflates space): you arrive at x and z times 10, on a safe surface (not inside rock) in the overworld.
- [ ] Deflates: you arrive at x and z divided by 10.
- [ ] With a Nether cast selected you arrive in the Nether in a safe air pocket below the roof, at the scaled x and z. The gem's tooltip shows the mode and the selected cast.

<sub>Already covered by automated pack tests: `bouillon_data`, `subspace_landing`, `subspace_crossing`, `subspace_maths`</sub>

## 94. The Brightest One

Check id: `concilium.brightest_one`

**Steps**

1. Read its research entry ("Brightest One", "Primordial Life") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You stand in front of a built chained rift (an ancient stone ring with a jar node above it), with two wisps hovering nearby and the QA wand (wisp launcher focus) in your hand. You have the Brightest One research.
3. Channel at a wisp to reel it in, then release near the rift so the charged wisp flies into the chained rift.
4. Repeat with a player who lacks the research if you can.
5. Next: The Brightest One (ignis) hangs ten blocks ahead of you; you have the QA wand (wisp launcher), a shield and survival mode.
6. Fight it from range and from the shield. Each charged wisp that reaches it changes its aspect (ignis, aer, vacuos, tenebrae): watch the halo colour and its attacks in each state.
7. Next: The Brightest One hangs ten blocks ahead of you; you have the QA wand (wisp launcher), a sword, a bow and survival mode.
8. Hit it with weapons, arrows and spells.
9. Launch charged wisps into it (channel the wisp launcher at wisps near you, it summons some, and let go aimed at the boss).
10. Next: The Brightest One hangs still ten blocks ahead of you.
11. Look at the sky and the top of the screen; go far away (leave the pad through the glass if you wish); kill it.
12. Next: A Brightest One at 1 health hangs ten blocks ahead of you (one charged wisp kills it) and a second still one hangs ten blocks behind; you have the QA wand (wisp launcher).
13. Kill the first with a short circuit and collect the drops, once. Then set difficulty to peaceful (/difficulty peaceful) with the second one alive.
14. Open the Primordial Life research in the Thaumic Concilium tab.

**Expect**

- [ ] The rift turns interdimensional and starts to collapse; at the end the Brightest One appears at size 0 and grows to full size.
- [ ] Without the research the charged wisp does nothing to the chained rift.
- [ ] Ignis: fire (embers) thrown at you. Aer: lightning and wind. Vacuos: pulls and crushes. Tenebrae: shadowbeams (hitscan) and darkness.
- [ ] Each attack set is readable, dodgeable and not overwhelming for the pack's level. The halo is a soft translucent disc, full colour at the centre, half at about a third of the way out, gone by about 0.6 of its size, in the aspect's colour.
- [ ] Nothing hurts it: a hit only makes the attacker its target.
- [ ] Each charged wisp that reaches it short-circuits it: it changes aspect and loses 1 of 15 health; at 0 it dies (the sky returns to normal).
- [ ] A pink boss bar with the sky darkened (as with the Wither or Ender Dragon) while it fights, returning to normal once it is gone or you are far away.
- [ ] Drops once: 2 essentia of its aspect and a Primordial Life; the research can then be completed (the item is now obtainable).
- [ ] On peaceful the Brightest One despawns.

<sub>Already covered by automated pack tests: `brightest_chained_rift_summon`, `brightest_save_load`, `brightest_attacks_ignis`, `brightest_attacks_aer`, `brightest_attacks_vacuos`, `brightest_attacks_tenebrae`, `brightest_shadowbeam_and_ember`, `brightest_ignores_damage`, `brightest_short_circuit_and_death`, `brightest_peaceful_despawn`</sub>

## 95. Protobody: look, infusion and shattering in the void

Check id: `concilium.protobody`

**Steps**

1. Read its research entry ("Protobody") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. You have a Protobody and a Solid Void block in the hotbar.
3. Look at it in your hand (first person), then press F5 to see it in third person, drop it (Q) and look at it on the ground, then pick it up again.
4. Next: The kit has the ingredients: a Corpse Effigy, four Void Putty and four Wisp Essences (void, flesh, aura, man). Build an infusion altar with four pedestals; the effigy goes in the middle.
5. Put the putty and essences on the pedestals, alternating (putty, void, putty, flesh, putty, aura, putty, man) and run the infusion (Thaumaturge's scribbling table or the research book shows the recipe once PROTOBODY is known).
6. Without a polished draw of 64 victus from a Destabilized Crystal with the Vis Conductor, the result must be lost; with it you get a Protobody.
7. Next: Press L (or /thaumicconcilium qa ethereal on) to become ethereal, then sneak straight down through the pad until you are well below the world floor (below y -80 in the overworld).
8. Hold the Protobody in your hand and drop it (Q) there; the void does not hurt an ethereal player.
9. Also drop a second Protobody above the floor (on the pad) and wait a few seconds.

**Expect**

- [ ] A small upright figure of the end portal's starfield (a vanilla humanoid shape), not a flat icon, in every view including the hotbar slot.
- [ ] On the ground it lies as a normal item entity and can be picked up after about two seconds.
- [ ] Judge this call: size and angle in hand, whether the figure reads as a body.
- [ ] The recipe page appears under the Protobody research, instability low (4), essentia humanus 128, vacuos 256, alienis 64, auram 128.
- [ ] The unpolished infusion fails with the polishment message; the polished one gives the Protobody.
- [ ] Judge this call: the book text reads well and the recipe is findable.
- [ ] Below y -80 the item breaks into six small spinning pieces (head, two arms, body, two legs) that fly outward and then drift about.
- [ ] The one dropped above the floor stays an ordinary item and is not harmed.
- [ ] Judge this call: the burst reads as a body breaking apart, and the pieces are visible against the void.

<sub>Already covered by automated pack tests: `protobody_drop_becomes_custom_entity`, `protobody_recipe_and_polishment_load`, `infusion_recipes_match`, `protobody_item_shatters_only_below_the_void_line`</sub>

## 96. Protolimbs and Solid Void

Check id: `concilium.protolimbs`

**Steps**

1. Read its research entry ("Solid Void", "Protobody") and its recipe pages: judge clarity, typos, and whether it explains the feature.
2. Down in the void (ethereal, below y -80) with the six limbs around you: watch them for a few seconds, then walk toward one.
3. Let each limb touch you (they shy away, so corner them or stand still). Count the sounds. On the sixth, listen for a heartbeat and look in the research book.
4. While ethereal with fewer than six absorbed, do something non-wand (break a block): your max health drops by one each time. With six absorbed it stops dropping.
5. Die or log out and in (respawn): the absorbed count resets.
6. Next: The kit has already set your absorbed count to six (/thaumicconcilium qa protolimbs 6). Go below the world floor (y -80 or lower; the trick works from just under y -64) holding a wand, and right-click in the air.
7. Try it with an empty hand, with a stick, and above the floor: nothing should happen.
8. Place the block down, look at it by day and by night, then break it with your hand.

**Expect**

- [ ] The limbs drift slowly in random directions and move away when you come within about four blocks.
- [ ] A touch plays a craft-fail sound and removes the limb; the sixth also plays a heartbeat and unlocks the Solid Void research entry (round, under the Protobody).
- [ ] Absorbing a seventh or a second set does not unlock it again or repeat the heartbeat.
- [ ] With six held the flesh (health held back) no longer grows; after respawn it does again.
- [ ] Judge this call: the flee distance and speed feel right; the particles on touch are fine.
- [ ] A Solid Void block appears in your inventory with a pop sound (dropped at your feet if the inventory is full), once per click.
- [ ] The block shows the end portal's starfield on every exposed face, the same by day and by night; faces against another block are not drawn.
- [ ] It breaks at once by hand and drops itself; explosions do not break it.
- [ ] Judge this call: the look in daylight and in the dark, in the hand and as a placed wall.

<sub>Already covered by automated pack tests: `protolimb_touch_counts_and_grants_solid_void_once`, `protolimb_drifts_and_keeps_away_from_a_player`, `peaceful_does_not_remove_a_protolimb`, `protolimb_is_banned_from_creature_infusion_and_not_hostile`, `wand_trick_needs_depth_and_six_limbs`, `solid_void_block_numbers_and_drop`</sub>

## 97. Sin pylon auras: wrath, envy, lust and pride

Check id: `concilium.sin_auras_creatures`

**Steps**

1. Read the effect entries involved (Gadomancy tab: Ira, Invidia, Luxuria, Superbia, learnt by standing near a burning pylon): judge clarity, typos, and whether they match what happens.
2. Next: Feed the formed column an ira crystal. Spawn three zombies and a skeleton within 8 blocks of it and watch for half a minute.
3. Feed it an invidia crystal instead. Spawn a zombie holding a sword (/summon zombie ~ ~ ~3 {HandItems:[{id:"iron_sword",count:1},{}]}) and stand in range yourself holding an item.
4. Feed it a luxuria crystal. Breed two cows with wheat, then try to breed them again right away while they stand in range.
5. Feed it a superbia crystal. Spawn a few zombies 10 to 20 blocks from the column, then walk away from it and spawn one 40 blocks out.

**Expect**

- [ ] Ira: the monsters turn on each other (and on any other mob nearby) instead of you, a new grudge every few seconds.
- [ ] Invidia: the zombie drops its sword on the ground within a few seconds and keeps dropping whatever it picks up; nothing leaves your own hands.
- [ ] Luxuria: the cows can be bred again within two seconds instead of five minutes; calves are not grown up by it.
- [ ] Superbia: every few ticks the monsters within 32 blocks are thrown at about a block a tick, all in roughly the same direction: toward the world's 0,0, as the original's code does (near 0,0 they scatter outward from the column). The one 40 blocks out is left alone.
- [ ] Judge this call: the strength and rhythm of the throw feel right.

<sub>Already covered by automated pack tests: `sin_table_binds_and_research_loads`, `ira_gives_a_zombie_a_target`, `invidia_disarms_mobs_not_players`, `luxuria_resets_cooldown_not_babies`, `superbia_pushes_as_the_original_within_32`</sub>

## 98. Sin pylon auras: gluttony, sloth and the Nether's heat

Check id: `concilium.sin_auras_players`

**Steps**

1. Read the effect entries involved (Gula, Desidia, Infernum in the Gadomancy tab): judge clarity, typos, and whether they match what happens.
2. Next: Make yourself hungry (/effect give @s hunger 10 100), then feed the formed column a gula crystal and stand within 8 blocks of it.
3. Feed it a desidia crystal. Drink a potion of swiftness (or /effect give @s speed 30), stand in range for a minute and watch the timer; then give yourself an infinite effect (/effect give @s night_vision infinite) and stay in range.
4. Feed it an infernum crystal. Throw a stack of raw iron, a stack of cobblestone, a log and a diamond on the ground within 8 blocks.

**Expect**

- [ ] Gula: the hunger bar fills by half a shank every second while you stand in range, saturation with it.
- [ ] Desidia: the swiftness timer barely moves (it gains a second every few ticks) and runs down normally once you step out; the infinite effect stays infinite.
- [ ] Infernum: within a moment the raw iron becomes iron ingots, the cobblestone stone, the log charcoal, each stack keeping its count; the diamond is untouched.

<sub>Already covered by automated pack tests: `gula_feeds_players`, `desidia_prolongs_but_keeps_infinite`, `smelt_keeps_the_count`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `concilium`).
