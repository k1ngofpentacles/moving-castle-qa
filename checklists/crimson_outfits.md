# QA: Crimson outfits (0.16.0)

Chapter id `crimson_outfits`, 4 checks. In game this is the FTB Quests chapter **QA: Crimson outfits (0.16.0)**; each check there has a green "Set up this check" line that builds its test site.

## 1. Eggs give a mix of host and Armor Series outfits

Check id: `crimson_outfits.outfit_variety_eggs`

**Steps**

1. You stand facing five rows of frozen mobs: 8 Crimson Paladins, 8 Archers, 8 Rangers, then 4 host Cultist Knights and 4 Clerics (summoned, not from eggs; eggs are on your hotbar if you want to spawn more). Look at each from the front and the back.

**Expect**

- [ ] Each of our three mobs comes in several looks: roughly half in Thaumaturge crimson armour, half in Armor Series gear (Paladin: gilded helm, praetor, knight, paladin helm; Archer: cleric robes or crossbowman; Ranger: ranger set or madcap). All wear the host cultist face. The Archer carries a quiver on its back and a bow; the Paladin a wand.
- [ ] The host knights and clerics look exactly as before (Thaumaturge armour only, none of the Armor Series gear).

<sub>Already covered by automated pack tests: `outfit_tables_resolve_and_split`, `our_cult_mobs_wear_table_outfits`, `host_cultists_and_pontifex_unchanged`</sub>

## 2. Outfits in a tower and in a raid

Check id: `crimson_outfits.outfit_tower_and_raid`

**Steps**

1. You stand in front of a Crimson Avanpost tower with its three guard archers on top (frozen). Look at their outfits.
2. Behind you a Lesser Crimson Portal is open: look at the cultists that arrive.

**Expect**

- [ ] The tower guards do not all look alike: they wear outfits from the Archer table (cleric robes or crossbowman).
- [ ] Raid and portal Paladins, Archers and Rangers show the same mix; knights and clerics from the portal stay host-looking.

<sub>Already covered by automated pack tests: `our_cult_mobs_wear_table_outfits`</sub>

## 3. Armour drops and the Pontifex

Check id: `crimson_outfits.outfit_drops_pontifex`

**Steps**

1. You stand in front of 18 frozen crimson mobs (six each of Paladin, Archer and Ranger) and a frozen Crimson Pontifex, with a diamond sword. Kill the grunts and watch their armour drops, then look at the Pontifex.

**Expect**

- [ ] Armour drops are rare (about one piece in twenty per slot, the host cultist rate), and Armor Series pieces can drop.
- [ ] The Pontifex still wears its own robe and nothing from Armor Series.

<sub>Already covered by automated pack tests: `host_cultists_and_pontifex_unchanged`</sub>

## 4. Nether Membrane icon

Check id: `crimson_outfits.nether_membrane_tint`

**Steps**

1. You hold a Nether Membrane next to a vanilla phantom membrane. Look at them in the inventory.

**Expect**

- [ ] It is the phantom membrane shape tinted crimson (dark red-pink). Say if it should be lighter.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `crimson_outfits`).
