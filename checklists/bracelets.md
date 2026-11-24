# QA: Casting Bracelets

Chapter id `bracelets`, 8 checks. In game this is the FTB Quests chapter **QA: Casting Bracelets**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:shield`, `minecraft:iron_sword`, `thaumaturge:arcane_workbench`

## 1. Worn: band on the left wrist

Check id: `bracelets.worn_wrist`

**Steps**

1. You are already wearing the void bracelet (Signal) in the Curios bracelet slot.
2. Look at yourself in F5 (front and back) and ask a friend to look.

**Expect**

- [ ] A band of void metal with purple rims and a glowing gem on the back of your left wrist (right wrist if you play left-handed).
- [ ] Hidden if you turn the slot's visibility off.

## 2. Worn: cast with V

Check id: `bracelets.worn_cast`

**Steps**

1. You are already wearing the void bracelet (Signal) in the Curios bracelet slot and hold an iron sword. Press V to cast Signal from the bracelet.
2. Watch in first person, then F5.

**Expect**

- [ ] The left arm stretches out ahead and a little up, hand towards the middle of the view ('Moses reaching for the sea'), band and gem visible.
- [ ] A burst of particles in the spell's colour at the hand.
- [ ] Vis drops by about two thirds of a wand's cast; the cooldown is half.

<sub>Already covered by automated pack tests: `bracelet_casting`</sub>

## 3. Worn + shield: no casting (shield foci only)

Check id: `bracelets.shield_cast`

**Steps**

1. You are already wearing the void bracelet, and a shield is in your hotbar. Put the shield in your off hand and press V.

**Expect**

- [ ] Nothing is cast; the action bar says your shield arm is busy (only shield foci, coming after phase 4, cast past a shield).
- [ ] Take the shield out: V casts again. A bracelet held in either hand still right-clicks normally.

<sub>Already covered by automated pack tests: `bracelet_casting`</sub>

## 4. Shield slot: bracelet casts

Check id: `bracelets.offhand`

**Steps**

1. You hold the void bracelet. Put it in your off hand (not a curio slot) and press V.

**Expect**

- [ ] Band on the left wrist; V casts from it.

<sub>Already covered by automated pack tests: `bracelet_casting`</sub>

## 5. Main hand: a wand

Check id: `bracelets.hand_wand`

**Steps**

1. You hold the eldritch bracelet in your main hand, in front of an Arcane Workbench. Right-click to cast Impulse.
2. Use it in the Arcane Workbench's wand slot. (Tapping an aura node needs a real node: find one if you want that part.)

**Expect**

- [ ] Band on the right wrist, the right forearm rises when casting.
- [ ] Casts at bracelet prices (2/3 vis, half cooldown).
- [ ] Taps nodes and works in the Arcane Workbench like a wand.

<sub>Already covered by automated pack tests: `bracelet_casting`, `bracelet_parts`</sub>

## 6. Channelled spell from a worn bracelet

Check id: `bracelets.channel`

**Steps**

1. You are already wearing the infernal bracelet (Cooling focus) in the Curios bracelet slot. Hold V for a few seconds, then let go.

**Expect**

- [ ] Snowballs while held; the arm stays up and motes swirl at the wrist; it lowers on release.

## 7. F radial for the worn bracelet

Check id: `bracelets.focus_radial`

**Steps**

1. You are already wearing a void bracelet with no focus (no wand in hand); a Positive Burst focus is in your hotbar. Hold F and pick the focus from the radial.

**Expect**

- [ ] A radial of your foci; the chosen focus socketed in the bracelet; the HUD next to the hotbar shows it and the vis bars.

## 8. Terrasteel volley

Check id: `bracelets.volley`

**Steps**

1. You are already wearing the terrasteel bracelet in the Curios bracelet slot. Press V once.

**Expect**

- [ ] Ten Signal casts at once; a long cooldown; a big vis bill (each cast at the original's 3.0 cost modifier).

<sub>Already covered by automated pack tests: `bracelet_volley`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `bracelets`).
