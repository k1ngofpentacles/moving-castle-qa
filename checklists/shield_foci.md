# QA: Shield Foci

Chapter id `shield_foci`, 20 checks. In game this is the FTB Quests chapter **QA: Shield Foci**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:shield`, `thaumaturge:thaumium_shield`, `thaumaturge:focal_manipulator`, `thaumaturge:focus_3`, `minecraft:bow`, `minecraft:arrow`, `minecraft:iron_sword`

## 1. Build Riposte and Aegis in the Focal Manipulator

Check id: `shield_foci.build_foci`

**Steps**

1. You stand next to a Focal Manipulator with three blank foci in your hotbar. Build three foci: Self > Aegis; Riposte > Frost (or any effect); Aura > Aegis.
2. Read the part tooltips and the research entries Riposte focus and Aegis focus, and the new paragraph on the guard stance in Casting Bracelets.

**Expect**

- [ ] Riposte and Aegis appear as spell parts once researched; the research entries read clearly and the guard stance paragraph says what a shield blocks.
- [ ] Settings (window 5 to 20 s, duration 5 to 20 s) change the complexity and vis cost sensibly.
- [ ] Judge this call: Riposte window steps of 5 s (default 10 s) with +1 complexity per step; Aegis aspect praemunio, complexity 6, vis 3, double cooldown.

<sub>Already covered by automated pack tests: `guard_gate_walk`</sub>

## 2. Guard stance refuses aimed spells

Check id: `shield_foci.guard_refuses_aimed`

**Steps**

1. You are already wearing a void bracelet with the Signal focus socketed (a projectile), and a plain shield is already in your off hand. Press V.
2. Swap to the Self > Aegis focus in your hotbar and press V. Try Self > Signal as well, and the Aura > Frost drum focus.
3. Take the shield out of the off hand and press V with Signal.

**Expect**

- [ ] Signal is refused with the action-bar message 'You cannot aim past your shield', no vis spent, no cooldown, a fail sound.
- [ ] Self, Aura, Touch, Wall, Cloud and Riposte spells cast; Self > Signal is refused (it would aim).
- [ ] Without a shield in the off hand everything casts as before.

<sub>Already covered by automated pack tests: `guard_gate_walk`, `guard_gate_press`</sub>

## 3. Shield in the main hand is ungated

Check id: `shield_foci.main_hand_shield`

**Steps**

1. You hold the shield in the main hand (off hand empty) and the void bracelet with Signal is already worn. Press V.

**Expect**

- [ ] It casts: only an off-hand shield triggers the guard stance (design decision 8).

<sub>Already covered by automated pack tests: `guard_gate_press`</sub>

## 4. Riposte refuses without a shield

Check id: `shield_foci.riposte_needs_shield`

**Steps**

1. You are already wearing a void bracelet with Riposte > Frost socketed and have no shield in the off hand. Press V.

**Expect**

- [ ] Refused with 'Riposte needs a shield in your off hand' before any vis is spent. Judge this call: the refusal before paying.

<sub>Already covered by automated pack tests: `riposte_needs_shield_and_cleanup`</sub>

## 5. Riposte: a real cast arms it

Check id: `shield_foci.riposte_arm_cast`

**Steps**

1. You have a shield in the off hand and are already wearing a bracelet with Riposte > Frost. Press V.
2. Watch the shield in first person and in F5, and listen.

**Expect**

- [ ] Vis is paid and the spell's normal cooldown starts. The shield gets a runic amber ward shell and a rim halo; a charge sound plays.
- [ ] The glow reads as 'armed', is not blinding in first person, and does not hide the shield.
- [ ] Judge this call: the look (accepted after round 4: runic amber wards).

<sub>Already covered by automated pack tests: `riposte_arm_release_parry`, `guard_look_messages`</sub>

## 6. Riposte: parry a melee hit

Check id: `shield_foci.riposte_melee`

**Steps**

1. A zombie waits in a glass box six blocks ahead, and you are already wearing the Riposte bracelet. Press V to arm Riposte (you have 10 seconds), then break the glass and let the zombie reach you.
2. Armed, lower the shield. Raise it (hold right-click) just before it hits, so the hit lands within half a second of raising.
3. Repeat, but hold the shield up for several seconds first and only then take a hit (press V again to re-arm).

**Expect**

- [ ] Parry: the blow is blocked, the attacker takes the spell (Frost) at 1.5x power, a white-amber burst and crackle play, the shield loses 1 extra durability.
- [ ] Held past the window (10 ticks by default): the shield just blocks, the charge stays and the ward stays.
- [ ] Judge this call: the parry window feel. Is half a second fair or too tight? Is the burst short enough? (config riposte.parryTicks)

<sub>Already covered by automated pack tests: `riposte_arm_release_parry`, `riposte_past_window_and_same_raise`</sub>

## 7. Riposte: real hurt path (not covered by tests)

Check id: `shield_foci.riposte_real_hurt`

**Steps**

1. You are in survival at night with a zombie and a skeleton each in their own glass box ahead, and you are already wearing the Riposte bracelet. Arm Riposte (V), break a box open and do the melee parry against the real mob, then the skeleton.

**Expect**

- [ ] It fires on a genuine blocked hit. The GameTests post the shield-block event directly, so this is the first real check of the damage pipeline.

<sub>Already covered by automated pack tests: `riposte_arm_release_parry`</sub>

## 8. Riposte: archers within and beyond 8 blocks

Check id: `shield_foci.riposte_archer`

**Steps**

1. You are already wearing the Riposte bracelet. Two skeletons wait in glass boxes: one about 6 blocks away on your left, one about 11 blocks away on your right. Arm Riposte (V), break the near box and raise the shield just before the arrow lands.
2. Repeat from the far skeleton (about 11 blocks).

**Expect**

- [ ] Within 8 blocks: the arrow's owner takes the spell.
- [ ] Beyond 8 blocks: the arrow is only blocked and the charge stays armed (config riposte.range).
- [ ] Judge this call: 8 blocks as the reach.

<sub>Already covered by automated pack tests: `riposte_archer_range`</sub>

## 9. Riposte: one release per raise

Check id: `shield_foci.riposte_same_raise`

**Steps**

1. You are already wearing the terrasteel bracelet (Riposte > Frost, several charges) and a shield in the off hand; two zombies wait in a glass box ahead. Press V, break the glass and take two quick hits within one raise.

**Expect**

- [ ] Only the first hit releases; the second is just blocked. Judge this call: one release per raise.

<sub>Already covered by automated pack tests: `riposte_past_window_and_same_raise`</sub>

## 10. Riposte: the terrasteel volley gives ten charges

Check id: `shield_foci.riposte_volley`

**Steps**

1. Only with Botania installed. You are already wearing the terrasteel bracelet with Riposte > Frost and have a shield in the off hand; zombies wait in a glass box ahead. Press V once (the volley is ten casts).
2. Break the glass, lower and raise the shield and take ten separate parried hits, one per raise.

**Expect**

- [ ] One cast arms ten charges (the ward grows brighter and adds shells with charges), at the usual long volley cooldown.
- [ ] Each parried hit spends one charge; after ten the ward is gone.

<sub>Already covered by automated pack tests: `riposte_past_window_and_same_raise`</sub>

## 11. Riposte: expiry loses the vis

Check id: `shield_foci.riposte_expiry`

**Steps**

1. You are already wearing the Riposte bracelet and have a shield in the off hand. Arm Riposte with the default 10 s window, do nothing, and wait. Also arm and then die (/kill) or log out.

**Expect**

- [ ] After the window the ward fades and nothing fires; the vis is not refunded.
- [ ] Logging out or dying clears it. Judge this call: the window runs from the last arming or release, 5 to 20 s.

<sub>Already covered by automated pack tests: `riposte_expiry`, `riposte_needs_shield_and_cleanup`</sub>

## 12. Aegis: cast it and see the ward

Check id: `shield_foci.aegis_cast`

**Steps**

1. You have a shield in the off hand and are already wearing a bracelet with Self > Aegis. Press V, then raise the shield. Check the effect icon in the HUD.

**Expect**

- [ ] A beneficial Aegis effect icon appears; a rune ring on a ward wall shows while you block.
- [ ] Judge this call: the effect icon and the look.

<sub>Already covered by automated pack tests: `aegis_blocks`, `guard_look_messages`</sub>

## 13. Aegis: blocks from behind and the sides, and magic

Check id: `shield_foci.aegis_arc`

**Steps**

1. Zombies wait in glass boxes behind you and on your right, and a witch on your left. The Aegis bracelet is already worn: press V for Aegis and raise the shield.
2. Break a box open and let the mob hit you from behind and from the side; let the witch throw potions at you.
3. Compare with the thaumium shield (it is in your hotbar; put it in the off hand).

**Expect**

- [ ] Hits from any direction are blocked with the forced-block crackle and rune flash and the warding sound; the shield takes double durability.
- [ ] Magic is blocked; on a thaumium or void shield the magic half is there already and Aegis adds the all-round arc.

<sub>Already covered by automated pack tests: `aegis_blocks`, `aegis_forced_block_triggers_riposte`</sub>

## 14. Aegis: nothing when lowered, nothing against fall damage

Check id: `shield_foci.aegis_no_effect`

**Steps**

1. You are in survival at night wearing the Aegis bracelet. Ahead: a zombie in a glass box. On the right: a tall stone tower with a ladder (jump off the top). Further right: a fire on netherrack. On the left: a water shaft in a glass block.
2. With Aegis on (V), lower the shield, break the zombie box open and get hit.
3. With the shield raised, fall from the tower, stand in the fire, and drown in the shaft.

**Expect**

- [ ] Lowered: the hit lands normally.
- [ ] Raised: fall, fire, drowning and starvation damage is never blocked.

<sub>Already covered by automated pack tests: `aegis_blocks`</sub>

## 15. Aegis block triggers Riposte

Check id: `shield_foci.aegis_riposte`

**Steps**

1. You are already wearing two bracelets: a void one with Riposte > Frost and an infernal one with Self > Aegis, and have a shield in the off hand; a zombie waits in a glass box behind you. Press V for each, raise the shield, break the box open and take a hit from behind within half a second.

**Expect**

- [ ] The block Aegis forces counts for Riposte: the attacker takes the spell. Judge this call: Aegis counting for Riposte.

<sub>Already covered by automated pack tests: `aegis_forced_block_triggers_riposte`</sub>

## 16. Aegis expires

Check id: `shield_foci.aegis_expiry`

**Steps**

1. You are already wearing the Aegis bracelet and have a shield in the off hand. Cast Aegis and wait out its duration (default 10 s) while holding the shield up.

**Expect**

- [ ] The icon and ward disappear on time and blocks return to normal.

<sub>Already covered by automated pack tests: `aegis_blocks`</sub>

## 17. Aegis through an aura, with a friend in LAN

Check id: `shield_foci.aegis_aura_lan`

**Steps**

1. You are already wearing a bracelet with Aura > Aegis and have a shield in the off hand; a zombie waits in a glass box behind you. Open the world to LAN, a friend joins and stands next to you. Press V.
2. The friend raises their own shield; break the box open so the zombie hits them from behind. Then the friend, shield lowered, takes a hit.

**Expect**

- [ ] Both of you get the Aegis effect; the friend must still hold their own raised shield for it to block.
- [ ] Judge this call: sharing the effect to allies through an aura.

<sub>Already covered by automated pack tests: `aegis_aura_shares`</sub>

## 18. A second client sees the cues

Check id: `shield_foci.second_client`

**Steps**

1. You are already wearing the Riposte and Aegis bracelets and have a shield in the off hand; a zombie waits in a glass box behind you. In LAN, the friend watches you arm Riposte, parry a hit, and block with Aegis.
2. The friend then walks into view of you after you armed (catch-up), and logs in while you are armed.

**Expect**

- [ ] They see the amber shell, the release burst, the Aegis ring and the forced-block crackle on you, with the same sounds nearby.
- [ ] A player who starts tracking you later still sees the current ward state.

<sub>Already covered by automated pack tests: `guard_look_messages`</sub>

## 19. Iris and other off-hand mods

Check id: `shield_foci.iris_shaders`

**Steps**

1. You are already wearing the Riposte and Aegis bracelets and have a shield in the off hand. With Iris installed and a shaderpack on, arm Riposte and cast Aegis; look in first and third person.
2. Check with any mod that also draws the off hand.

**Expect**

- [ ] The shield is drawn normally with the ward on top; no missing shield, double hand or flicker in first person.
- [ ] Third person: the shells draw after the shield with no broken batches.
- [ ] Known untested: the first-person off-hand render takeover and the third-person batch end.

## 20. Judge this call: the look and the spell parts' colours

Check id: `shield_foci.look_judge`

**Steps**

1. A Focal Manipulator stands in front of you, and you are already wearing both bracelets and have a shield. Look at the part icons and the Aegis effect icon in the Focal Manipulator and the HUD, and at the wards in play.

**Expect**

- [ ] Both wards are runic amber on purpose; the spell parts keep their own colours: steel for the swordsman's Riposte, blue for the guardian's Aegis.
- [ ] Judge this call: that split (ward amber, parts steel and blue).

<sub>Already covered by automated pack tests: `guard_look_messages`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `shield_foci`).
