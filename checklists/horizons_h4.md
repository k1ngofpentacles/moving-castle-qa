# QA: Horizons H4: self-infusion

Chapter id `horizons_h4`, 5 checks. In game this is the FTB Quests chapter **QA: Horizons H4: self-infusion**; each check there has a green "Set up this check" line that builds its test site.

## 1. Keys M, C and X

Check id: `horizons_h4.keys`

**Steps**

1. Open the Controls screen, category Thaumic Horizons: M, C and X are bound by default (the original shipped them unbound).
2. Press each key with no infusion.

**Expect**

- [ ] Nothing happens without the matching infusion and nothing is sent.

<sub>Already covered by automated pack tests: `key_payloads_are_refused_without_the_infusion`</sub>

## 2. Self-infusion ritual and standby

Check id: `horizons_h4.standby`

**Steps**

1. A raw vat with the Modified Runic Matrix on its lid stands ahead; the wand is on your hotbar.
2. Wand-click the vat, prepare a self-infusion as the research page says; enter standby with yourself as the subject.

**Expect**

- [ ] The ritual stores the infusion in standby (it does not apply yet); the matrix and vat look right.

<sub>Already covered by automated pack tests: `ritual_stores_the_infusion_in_standby`, `data_round_trips_through_save_and_sync`</sub>

## 3. Death rule (as the original)

Check id: `horizons_h4.death_rule`

**Steps**

1. A raw vat stands ahead; the wand and a Soul Beacon are on your hotbar.
2. Form the vat, put it in standby and bind the beacon, die with /kill, wake in the vat.
3. Next, die again with no beacon.

**Expect**

- [ ] The first death applies the infusions through the rebirth; an ordinary death clears them and returns the Warped Tumor's warp.

<sub>Already covered by automated pack tests: `rebirth_applies_and_an_ordinary_death_clears`, `warped_tumor_absorbs_and_returns_warp`</sub>

## 4. What the infusions do

Check id: `horizons_h4.effects`

**Steps**

1. A stone-brick wall and a deep pool stand ahead; rotten flesh is on your hotbar.
2. Once you have the infusions: with Spider Climb walk into the wall and press C; with Amphibious swim; with Silverwood Heart eat the rotten flesh; with a potion infusion check your effects.

**Expect**

- [ ] Spider Climb sticks to walls and toggles with C; Amphibious breathes water; the heart filters toxins and taint; the potion infusions hold their effect.
- [ ] Feel: climbing speed, swim speed, the message text.

<sub>Already covered by automated pack tests: `spider_climb`, `amphibious_and_synthskin`, `silverwood_heart_filters_toxins_and_taint`, `potion_infusions`</sub>

## 5. Morphic Fingers

Check id: `horizons_h4.fingers`

**Steps**

1. Planks and sticks are on your hotbar.
2. With Morphic Fingers press M, put items in the small crafting grid and craft.

**Expect**

- [ ] A workbench-like menu opens; it crafts and keeps nothing when closed.

<sub>Already covered by automated pack tests: `morphic_fingers_crafts_and_keeps_nothing`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h4`).
