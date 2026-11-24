# QA: Crimson Forces (5a)

Chapter id `phase_5a`, 19 checks. In game this is the FTB Quests chapter **QA: Crimson Forces (5a)**; each check there has a green "Set up this check" line that builds its test site.

**Chapter kit:** `minecraft:shield`, `minecraft:bow`

## 1. Primal arrows from a bow, a crossbow and a dispenser

Check id: `phase_5a.arrows_fire`

**Steps**

1. You stand with a bow, a crossbow, arrows and 16 of each primal arrow in your hotbar. A pig stands 9 blocks ahead; an armoured zombie is to its right; a dispenser (loaded with all six kinds, 4 each) faces a second pig to your left, with a lever beside it.
2. Fire each of the six primal arrows (aer, aqua, ignis, ordo, perditio, terra) from the bow at the pig and at the ground, then from the crossbow, then power the dispenser with the lever.
3. Try a primal arrow against the armoured zombie. A Power-enchanted bow or piercing crossbow is up to you.

**Expect**

- [ ] Every type flies, lands and does damage from all three launchers, and each shows its own effect (aer, aqua, ignis fire or water interplay, ordo, perditio, terra).
- [ ] Primal damage ignores or reduces armour less than a plain arrow; the effect reads clearly and is not overwhelming.
- [ ] The dispenser fires them in a straight line like vanilla arrows.

<sub>Already covered by automated pack tests: `primal_arrows_effects`, `primal_arrows_damage_types`, `primal_arrows_items_recipes_nbt`, `crimson_archer_fires_primal_arrow`</sub>

## 2. Terra knockback

Check id: `phase_5a.arrows_terra`

**Steps**

1. You stand with a bow, plain arrows and terra arrows. Two zombies that cannot walk stand 8 blocks ahead, one each side, at the same distance. Shoot a terra arrow at one and a plain arrow at the other.

**Expect**

- [ ] The terra arrow throws the mob back clearly further than a plain arrow does, without launching it absurdly far.

<sub>Already covered by automated pack tests: `primal_arrows_effects`</sub>

## 3. The glow on primal arrows

Check id: `phase_5a.arrows_glow`

**Steps**

1. It is night and you hold a bow with all six primal arrows; a stone wall stands 9 blocks ahead. Fire each type at the wall and watch the arrow in flight and stuck in the stone; look at the items in the inventory too.

**Expect**

- [ ] Each arrow glows in its primal's colour in flight and while stuck, readable in the dark and distinct per type; no lag or flicker.

## 4. Paladin, Archer and Ranger fights

Check id: `phase_5a.mobs_fight`

**Steps**

1. You are in survival with iron armour, a shield, a diamond sword, a bow and golden apples; the three spawn eggs are in your hotbar. Use each spawn egg on the ground, one at a time, and fight it. Fight the Archer from open ground and (dig down or build a roof) in the dark; fight the Ranger at range and up close.
2. Check what they drop on death.

**Expect**

- [ ] Paladin: keeps its distance, casts at you from 8+ blocks away (orb or shackles) and melees when close. Archer: strafes and shoots primal arrows, Power and Flame from its bow pass on. Ranger: sprays shard powder.
- [ ] All three are fair for the pack's level, do not stand still or jitter, and drop gear and loot sensibly.
- [ ] The Archer and Ranger have no bow-draw pose yet (known).

<sub>Already covered by automated pack tests: `crimson_stats_and_gear`, `crimson_drops`, `crimson_paladin_spells`, `crimson_archer_fires_primal_arrow`, `crimson_ranger_sprays_shard_powder`, `archer_damage_multiplier`</sub>

## 5. The looks of Paladin, Archer and Ranger

Check id: `phase_5a.mobs_looks`

**Steps**

1. You are in creative in daylight, facing a Paladin, an Archer and a Ranger standing still in a row 6 blocks ahead. Look at each from the front, back and side (fly around them) and compare with the harness shots; at dusk (/time set night) look again.

**Expect**

- [ ] Red-robed bodies with Thaumaturge armour, readable at range. The Paladin's hood and staff show; nothing is magenta, invisible or stretched.
- [ ] Known: the original wore black plate where ours wears red robes; judge whether the look is acceptable.

## 6. Knight replacement and Ranger natural spawns

Check id: `phase_5a.mobs_wild`

**Steps**

1. This check needs real terrain, so you are not moved. You are armed and it is night. Explore, or spend a night in a spot where Thaumaturge knights spawn, and watch what appears. Also look for a Ranger on its own in the open and in lit areas.

**Expect**

- [ ] Some fresh Thaumaturge knight spawns are replaced by Crimson Paladins at a modest rate (never every one).
- [ ] Rangers turn up naturally now and then, not in swarms and not in lit caves.
- [ ] Portal minions are not turned into Paladins.

<sub>Already covered by automated pack tests: `crimson_knight_replacement_rate`, `crimson_ranger_spawn_modifier`</sub>

## 7. Ethereal Shackles (feel only, no visual yet)

Check id: `phase_5a.shackles_feel`

**Steps**

1. You are in survival with armour, a shield and stone. A Crimson Paladin stands 11 blocks ahead and will cast at you. Let it hit you with its shackles. While chained, try to place and break blocks, use items, swing at it and open doors. Wait it out (about 5 seconds).

**Expect**

- [ ] You cannot use, place, break, interact or attack for about 100 ticks, then it lifts cleanly. Movement is still free.
- [ ] Other mobs hit by it are slowed instead.
- [ ] There is no visual effect for the chain (known gap): judge whether it is readable that you are chained at all.

<sub>Already covered by automated pack tests: `crimson_paladin_spells`</sub>

## 8. Lesser Crimson Portal: opening and minion waves

Check id: `phase_5a.portal_open`

**Steps**

1. A Lesser Crimson Portal has just been placed 7 blocks ahead of you, and you are armed in survival. Stand back and watch it for a few minutes without killing the minions at first, then fight them.
2. Hit the portal to see it flicker.

**Expect**

- [ ] The portal opens from a slit to a full oval over a short time (ours is slower and red; the reference was violet), then sends Crimson minions in waves with growing intervals.
- [ ] Waves arrive at a pace you can handle and the portal does not spam.
- [ ] Hits visibly register on the portal.

<sub>Already covered by automated pack tests: `portal_stage_functions`, `portal_stats_and_spawn`</sub>

## 9. The boss at stage 13, through the Crimson Rites rift route

Check id: `phase_5a.portal_boss`

**Steps**

1. A chained rift over a hex stands 5 blocks ahead, the research is granted and you hold two Crimson Rites. Throw one Crimson Rites into the rift by hand (Q while facing it).
2. Let the collapse finish and see what appears. Then let the resulting portal run to stage 13, or use /thaumicconcilium qa portal ~ ~ ~7 boss to skip ahead.

**Expect**

- [ ] The rift eats the Rites, turns interdimensional and collapses at once, and a Lesser Crimson Portal opens where it was. Without the research nothing happens.
- [ ] At stage 13 the portal kills itself and the Crimson Pontifex arrives.

<sub>Already covered by automated pack tests: `rift_route_sets_boss_flag`, `portal_boss_at_stage_13`</sub>

## 10. Pontifex: boss bar and darkened sky

Check id: `phase_5a.pontifex_bar`

**Steps**

1. The Crimson Pontifex stands 10 blocks ahead and you are armed in survival. Look at the top of the screen and the sky while near it. Back away to the edge of the pad. Kill it.

**Expect**

- [ ] A boss bar shows with the sky darkened while it fights, and returns to normal when it is dead or you are far away.

<sub>Already covered by automated pack tests: `pontifex_stats_bar_and_loot`</sub>

## 11. Pontifex: the enslave walk

Check id: `phase_5a.pontifex_enslave`

**Steps**

1. The Crimson Pontifex stands 10 blocks ahead and you are armed in survival. Fight it until it enslaves you. Try to resist, look around, and see how long it lasts and whether you can break out.

**Expect**

- [ ] You are walked toward it against your will; the pull is clear and readable but not nauseating, the camera stays usable and it ends predictably.
- [ ] In multiplayer (LAN) other players see the walk smoothly.

<sub>Already covered by automated pack tests: `enslave_flag`</sub>

## 12. Pontifex: the damage split and attack feel

Check id: `phase_5a.pontifex_damage`

**Steps**

1. The Crimson Pontifex stands 10 blocks ahead; you hold a sword, bow, arrows, primal arrows and a wand with the Signal focus. Hit it with the sword, arrows, the wand and primal arrows; take its attacks.

**Expect**

- [ ] Damage is split as designed (a share lands as normal damage, the rest is reduced) so it takes a while but is killable in a fair fight.
- [ ] Its attacks are readable and dodgeable and not overwhelming.

<sub>Already covered by automated pack tests: `pontifex_damage_split`, `pontifex_attack_rolls`, `pontifex_stats_bar_and_loot`</sub>

## 13. Pontifex: death drops and the loot bag

Check id: `phase_5a.pontifex_loot`

**Steps**

1. You are in creative with a diamond sword and the Pontifex stands 10 blocks ahead. Kill it and collect the drops. Open the loot bag. Press Again to kill a few more and see the spread.

**Expect**

- [ ] It drops a Thaumaturge rare loot bag and, by chance, its own gear. The bag opens with its contents.
- [ ] Research hint notes appear for the right players.

<sub>Already covered by automated pack tests: `pontifex_drop_odds`, `pontifex_wears_his_gear`, `notes_unlock_research`</sub>

## 14. Crimson Annales: use and finding it in chests

Check id: `phase_5a.annales_use`

**Steps**

1. You hold the Crimson Annales and have no research. Use it now: you should get the unclear message. Then press this quest's "Crimson Rites research" reward button (or grant yourself thaumaturge:crimson_rites) and use it again; use it a second time.
2. Five chests of the dungeon, mineshaft, desert pyramid, jungle temple and stronghold loot tables stand 4 blocks ahead: open them, and press Again to re-roll them a few times.

**Expect**

- [ ] Without the research you get a dark purple 'meaning remains unclear' message and nothing is consumed. With it the research completes with the learn sound; a second use does nothing new.
- [ ] The Annales turns up rarely in those chests (about as rare as a loot-bag drop, not common).

<sub>Already covered by automated pack tests: `annales_use`, `annales_loot_entries`</sub>

## 15. Pontifex Hammer: life steal and held pose

Check id: `phase_5a.hammer_use`

**Steps**

1. You are hurt a little and hold the Pontifex Hammer, with cows and a pig near you. Hold the hammer (right-click) near them and hit them. Look at it held in first and third person, off hand too.

**Expect**

- [ ] Life drains from nearby mobs to you while held, with particles flowing to you, and you are healed.
- [ ] The hammer pose is a block-style hold. Known: third person is smaller and tilted compared to the original; judge acceptability.

<sub>Already covered by automated pack tests: `hammer_life_steal`</sub>

## 16. Pontifex Robe: the dye, the L toggle, cultist aggro

Check id: `phase_5a.robe_use`

**Steps**

1. You stand beside a crafting table with the four robe pieces and dyes in your hotbar; Thaumaturge cultists wait 11 blocks ahead. Dye the four robe pieces in a crafting grid. Wear the full set, press L, then let the cultists see you with it on and off.
2. Wear only part of the set and press L.

**Expect**

- [ ] The robe takes dye on its base layer with the overlay unchanged; the dyed inventory icon matches.
- [ ] L toggles the form with a clear indication; while on, cultists and Crimson mobs drop aggro on you, while off they attack as normal. A partial set does nothing.
- [ ] The cloth flaps while walking, the helm reveals nodes like goggles, and the look matches the reference.

<sub>Already covered by automated pack tests: `robe_dye_result`, `robe_toggle_state`, `robe_drops_cultist_aggro`</sub>

## 17. Arcane Levitator: lift feel, stacking, redstone, sneaking

Check id: `phase_5a.levitator_lift`

**Steps**

1. A single levitator stands ahead to the left and a column of six ahead to the right, with a lever beside it; you hold more levitators, stone, levers and redstone blocks. Stand on the single one: judge the lift, jitter at the top, and whether the item and the pig rise too.
2. Stand on the column of six and see the height. Switch it with the lever (or a redstone block), then back. Sneak while falling onto it from height.
3. Place a stone block in the column and check the lift stops and starts as it changes.

**Expect**

- [ ] You rise smoothly with no jerk or jitter at the top; items and mobs lift too. Boats and minecarts are not lifted (known).
- [ ] Each stacked levitator lengthens the column. Redstone power turns it off and it resumes when unpowered.
- [ ] Sneaking dampens your fall onto it.
- [ ] Under a ceiling you hover below it rather than clipping in.

<sub>Already covered by automated pack tests: `levitator_lifts_and_stops`, `levitator_stack_height`, `levitator_redstone_off`, `levitator_sneak_damps_fall`, `levitator_recipe_output`, `levitator_cache_follows_neighbours`</sub>

## 18. Cultist tower in the wild

Check id: `phase_5a.tower_wild`

**Steps**

1. This check needs real terrain, so you are not moved. You are armed in survival. Explore a new world area (or a fresh seed) until you find a Crimson cultist tower; look at it from outside and inside. Check its banners, fight the guards and open the chest.

**Expect**

- [ ] The tower is found now and then, not too often, sits flat on the ground and faces sensibly.
- [ ] Banners show as intended (hanging on the walls, not broken or invisible); archers stand guard and do not despawn.
- [ ] The chest holds fair loot.

<sub>Already covered by automated pack tests: `tower_template_contents`, `tower_ground_rule`, `tower_loot_table`, `tower_placement_spawns_persistent_archers`</sub>

## 19. Gilded Crimson Helm worn by a player

Check id: `phase_5a.helm_worn`

**Steps**

1. You are in creative already wearing the Gilded Crimson Helm, with a Paladin standing 4 blocks ahead to compare its helm. Look at yourself in third person (F5, front and back), in first person with the head visible.

**Expect**

- [ ] The helm and its fin sit properly on the head, with no clipping into the face or body.
- [ ] Fine in first person, and the Paladin's gilded helm variant matches.

<sub>Already covered by automated pack tests: `crimson_paladin_gilded_helm`</sub>

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `phase_5a`).
