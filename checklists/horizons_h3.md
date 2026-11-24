# QA: Horizons H3: species mobs

Chapter id `horizons_h3`, 9 checks. In game this is the FTB Quests chapter **QA: Horizons H3: species mobs**; each check there has a green "Set up this check" line that builds its test site.

## 1. Chocolate Cow, Chromatic and Self-shearing Sheep

Check id: `horizons_h3.cow_and_sheep`

**Steps**

1. A Chocolate Cow, a Chromatic Sheep and a Self-shearing Sheep stand ahead; you are weakened and carry buckets and a milk bucket.
2. Milk the cow with a bucket and drink the other milk to cure effects; watch the Chromatic Sheep for two minutes and the Self-shearing Sheep for one.

**Expect**

- [ ] The cow gives a chocolate milk bucket (a bucket item only, by decision) that cures effects like milk; the Chromatic Sheep cycles colours smoothly; the Self-shearing Sheep drops wool by itself and regrows it.
- [ ] The mobs look right and read as their originals; calves are not milked and lambs not self-shearing (accepted).

<sub>Already covered by automated pack tests: `chocolate_cow_milks_chocolate_and_the_bucket_cures`, `chromatic_sheep_cycles_and_self_shearing_sheep_shears`</sub>

## 2. Sheeder

Check id: `horizons_h3.sheeder`

**Steps**

1. A Sheeder stands ahead in front of a wall; shears are on your hotbar.
2. Shear it, climb near it and hit it.

**Expect**

- [ ] It is a spider that yields wool, regrows it and climbs walls; it fights back when hit (a deliberate quirk kept from the original).

<sub>Already covered by automated pack tests: `sheeder_shears_regrows_climbs_and_fights_back`</sub>

## 3. Gold Chicken and Scholar Chicken

Check id: `horizons_h3.chickens`

**Steps**

1. A Gold Chicken and a Scholar Chicken stand ahead.
2. Wait for eggs; collect what they lay.

**Expect**

- [ ] The Gold Chicken lays gold nuggets or eggs with a sparkle; the Scholar Chicken lays knowledge items; sparkle rate feels fine (the gold sparkle is per tick: accepted).

<sub>Already covered by automated pack tests: `chickens_lay_their_own_products`</sub>

## 4. Ore Boar and Taintfeeder

Check id: `horizons_h3.boar_taint`

**Steps**

1. An Ore Boar stands to the left, a Taintfeeder to the right beside a few blocks of taint rock; iron ore is on your hotbar.
2. Throw iron ore on the ground near the Ore Boar; watch the Taintfeeder eat the taint.

**Expect**

- [ ] The boar eats ores from up to 16 blocks away and drops purified extras; the Taintfeeder eats taint and restores the clean biome, and the taint effects do not hurt it.
- [ ] The glow strips are redrawn art: judge the look.

<sub>Already covered by automated pack tests: `ore_boar_table_eating_and_loot`, `taintfeeder_ignores_the_taint_effects`, `taintfeeder_eats_taint`</sub>

## 5. Guardian Panther and Gravekeeper

Check id: `horizons_h3.panther_keeper`

**Steps**

1. A Guardian Panther, a Gravekeeper and a zombie stand ahead (night, easy difficulty); raw fish is on your hotbar.
2. Feed the panther and let the zombie approach; stand near the Gravekeeper with the undead around.

**Expect**

- [ ] The panther guards you and attacks threats; the Gravekeeper bites and its aura affects undead.
- [ ] Known look fix queued: the panther uses a black cat texture for now.

<sub>Already covered by automated pack tests: `guardian_panther_numbers_goals_and_food`, `gravekeeper_goal_fix_bite_and_aura`</sub>

## 6. Familiar, Lunar Wolf and wand charging

Check id: `horizons_h3.wolves`

**Steps**

1. A Familiar and a Lunar Wolf stand ahead; an empty wand is on your hotbar.
2. Wait beside the creatures.

**Expect**

- [ ] The wand slowly gains vis from the creatures nearby; the mobs look right.

<sub>Already covered by automated pack tests: `familiar_and_lunar_wolf_charge_wands`</sub>

## 7. Seawolf and Nether Hound

Check id: `horizons_h3.sea_hound`

**Steps**

1. A Seawolf swims in a pool to the left and a Nether Hound stands on land to the right.
2. Make the hound angry.

**Expect**

- [ ] The Seawolf swims and never drowns; the Nether Hound breathes fire at intervals and leaves embers only when it attacks.

<sub>Already covered by automated pack tests: `seawolf_swims_and_never_drowns`, `nether_hound_breathes_fire_on_ticks`</sub>

## 8. Endersteed and Nightmare

Check id: `horizons_h3.horses`

**Steps**

1. A tame Endersteed and a tame Nightmare stand ahead, a lava pool lies to the right; saddles are on your hotbar.
2. Ride the Endersteed and use its blink; ride the Nightmare over the lava and use its plane shift (with and without a rider).

**Expect**

- [ ] Endersteed blinks, has sane health; the Nightmare walks on lava and carries its rider through the plane shift.
- [ ] Horses are vanilla black plus a glow (documented). Feel: jump height, blink distance, balance.

<sub>Already covered by automated pack tests: `endersteed_bonuses_and_blink`, `nightmare_body_lava_and_jump_rules`, `nightmare_plane_shift_carries_the_horse_and_any_rider`, `zombie_and_skeletal_horses_keep_their_bonuses`, `a_plain_horse_cannot_be_infused_to_a_nightmare`</sub>

## 9. Species infusions in the vat

Check id: `horizons_h3.recipes`

**Steps**

1. A raw vat with the Modified Runic Matrix on its lid stands ahead, with a cow, a sheep, a chicken and a pig beside it. The wand and the Thaumonomicon are on your hotbar.
2. Open the Thaumonomicon, find the species entries and craft two of them in the vat (see the research page).

**Expect**

- [ ] Every species recipe converts its creature and keeps its data (name, age, equipment).

<sub>Already covered by automated pack tests: `species_data_numbers_and_registry`, `every_species_recipe_converts_and_keeps_data`, `species_start_rules`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h3`).
